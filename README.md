<h1 align="center">pico-ducky</h1>

## Hızlı Başlangıç ​​Kılavuzu
USB Rubber Ducky'nizi 5 dakikadan daha kısa sürede kurun ve çalışmasını sağlayın.

1. En son sürümü [Sürümler](https://github.com/dbisu/pico-ducky/releases) sayfasından indirin.

2. Önyükleme düğmesini basılı tutarak cihazı bir USB bağlantı noktasına takın. RPI-RP2 adında çıkarılabilir bir medya cihazı olarak görünecektir.

3. CircutlPython'u Pico'ya yükleyin

Pico kartı kullanıyorsanız:

Adafruit-circuitpython-raspberry_pi_pico-en_US-8.0.0.uf2 dosyasını Pico'nun (RPI-RP2) köküne kopyalayın. Cihaz yeniden başlatılacak ve bir saniye kadar sonra CIRCUITPY olarak yeniden bağlanacaktır.

Pico W kartı kullanıyorsanız:

Adafruit-circuitpython-raspberry_pi_pico_w-en_US-8.0.0.uf2 dosyasını Pico'nun (RPI-RP2) köküne kopyalayın. Cihaz yeniden başlatılacak ve bir saniye kadar sonra CIRCUITPY olarak yeniden bağlanacaktır.

4. lib klasörünü CIRCUITPY'nin köküne kopyalayın

5. *.py'yi DEVRE'nin köküne kopyalayın

6. Kurulum moduna girmek için README.md'deki talimatları izleyin.

7. Payload'ınızı payload.dd olarak CIRCUITPY'nin köküne kopyalayın

8. Aygıtı USB bağlantı noktasından çıkarın ve kurulum atlama kablosunu çıkarın.

Pico-Ducky'nizin tadını çıkarın.

## Kurulum modu

Yükü düzenlemek için, pin 1'i ('GP0') pin 3'e ('GND') bağlayarak kurulum moduna girin; bu, pico-ducky'nin yükü kendi makinenize enjekte etmesini durduracaktır.
Bunu yapmanın en kolay yolu aşağıda görüldüğü gibi bu pinlerin arasına bir jumper teli kullanmaktır.

![Atlatma kablosuyla kurulum modu](images/setup-mode.png)

## USB etkinleştirme/devre dışı bırakma modu

Pico-ducky'nin gizlilik amacıyla bir USB yığın depolama aygıtı olarak görünmemesini istiyorsanız bu talimatları izleyin.
- Kurulum moduna girin.
- Payload komut dosyanızı pico-ducky'ye kopyalayın.
- Pico'yu ana bilgisayarınızdan ayırın.
- Pim 18 ("GND") ile pim 20 ("GPIO15") arasına bir aktarma kablosu bağlayın.
Bu, pico-ducky'nin hedef bilgisayara takıldığında bir USB sürücü olarak görünmesini önleyecektir.
- Jumper'ı çıkarın ve yeniden programlamak için bilgisayarınıza yeniden bağlayın.

Pico: Varsayılan mod, USB yığın depolamanın etkin olduğu moddur.
Pico W: Varsayılan mod USB yığın depolamadır **devre dışı**

![USB etkinleştirme/devre dışı bırakma modu](images/usb-boot-mode.png)


-----

# Tam Kurulum Talimatları

USB Rubber Ducky'nizi 5 dakikadan daha kısa sürede kurun ve çalışmasını sağlayın.

1. Dosyaların yerel bir kopyasını almak için repoyu klonlayın. 'git klonu https://github.com/dbisu/pico-ducky.git'

2. [Raspberry Pi Pico için CircuitPython'u](https://circuitpython.org/board/raspberry_pi_pico/) indirin. *8.0.0'a güncellendi

3. Önyükleme düğmesini basılı tutarak cihazı bir USB bağlantı noktasına takın. 'RPI-RP2' adında çıkarılabilir bir medya cihazı olarak görünecektir.

4. İndirilen `.uf2` dosyasını Pico'nun köküne (`RPI-RP2`) kopyalayın. Cihaz yeniden başlatılacak ve bir saniye kadar sonra 'CIRCUITPY' olarak yeniden bağlanacaktır.

5. `adafruit-circuitpython-bundle-8.x-mpy-YYYYMMDD.zip` dosyasını [buradan](https://github.com/adafruit/Adafruit_CircuitPython_Bundle/releases/latest) indirin ve cihazın dışına çıkarın.

6. Yakın zamanda çıkarılan klasörde `lib`e gidin ve `adafruit_hid`i Raspberry Pi Pico'nuzdaki `lib` klasörüne kopyalayın.

7. `adafruit_debouncer.mpy` ve `adafruit_ticks.mpy`yi Raspberry Pi Pico'nuzdaki `lib` klasörüne kopyalayın.

8. 'asyncio'yu Pico'nuzdaki 'lib' klasörüne kopyalayın.

9. 'adafruit_wsgi'yi Pico'nuzdaki 'lib' klasörüne kopyalayın.

10. Klonunuzdan "boot.py" dosyasını Pico'nuzun kök dizinine kopyalayın.

11. `duckyinpython.py`, `code.py`, `webapp.py`, `wsgiserver.py`yi Pico'nun kök klasörüne kopyalayın.

12. [Buradan](https://github.com/hak5/usbrubberducky-payloads) bir komut dosyası bulun veya [Ducky Komut Dosyasını kullanarak kendi komut dosyanızı oluşturun](https://docs.hak5.org/hak5-usb-rubber-ducky/ducy-script-basics/hello-world) ve onu Pico'da `payload.dd` olarak kaydedin. Şu anda pico-ducky 3.0'ı değil yalnızca DuckyScript 1.0'ı desteklemektedir.

13. Dikkatli olun, eğer cihazınız kurulum modunda değilse cihaz yeniden başlatılacak ve yarım saniye sonra komut dosyası çalışacaktır.



## USB etkinleştirme/devre dışı bırakma modu

Pico-ducky'nin gizlilik amacıyla bir USB yığın depolama aygıtı olarak görünmemesini istiyorsanız bu talimatları izleyin.
- Kurulum moduna girin.
- Payload komut dosyanızı pico-ducky'ye kopyalayın.
- Pico'yu ana bilgisayarınızdan ayırın.
- Pim 18 ("GND") ile pim 20 ("GPIO15") arasına bir aktarma kablosu bağlayın.
Bu, pico-ducky'nin hedef bilgisayara takıldığında bir USB sürücü olarak görünmesini önleyecektir.
- Jumper'ı çıkarın ve yeniden programlamak için bilgisayarınıza yeniden bağlayın.

Pico: Varsayılan mod, USB yığın depolamanın etkin olduğu moddur.
Pico W: Varsayılan mod USB yığın depolamadır **devre dışı**


## Klaveye Dilini Değiştirme

**En son sürüm sayfasına [gidin](https://github.com/Neradoc/Circuitpython_Keyboard_Layouts/releases/latest) ve dilinizin listede olup olmadığına bakın.**

#### Diliniz pakette yer alıyorsa

'circuitpython-keyboard-layouts-py-XXXXXXXX.zip' adlı 'py' zip dosyasını indirin

**NOT: Cihazdaki Circuitpython sürümünü hedefleyen mpy sürümünü kullanabilirsiniz, ancak Raspberry Pi Pico'da buna ihtiyacınız yoktur - bunlar yalnızca yükte dosya boyutunu ve bellek kullanımını azaltır; bu da pico'da bol miktarda bulunur. .**

#### Artık bir zip dosyanız var

#### Dilinizi/düzeninizi lib dizininde bulun

Bir 'LANG' dili için, aşağıdaki dosyaları zip'in 'lib' klasöründen panonun 'lib' dizinine kopyalayın.
**adafruit_hid dizinini DEĞİŞTİRMEYİN**. Dosyalarınız doğrudan 'lib'e gider.
**Dosyaların adlarını veya uzantılarını DEĞİŞTİRMEYİN**. Sadece doğru olanları seçin.
'LANG'ı seçtiğiniz dilin harfleriyle değiştirin.

- `keyboard_layout_win_LANG.py`
- `keycode_win_LANG.py`

Almayı unutma [the adafruit_hid library](https://github.com/adafruit/Adafruit_CircuitPython_HID/releases/latest).

**Örneğin diliniz Fransızca ise** bu şekilde görünmesi gerekir.

![CIRCUITPY drive screenshot](https://github.com/Neradoc/Circuitpython_Keyboard_Layouts/raw/main/docs/drive_pico_ducky.png)

#### Dil dosyanızı kullanmak için pico-ducky kodunu değiştirin:

Dosyanın başında şu satırları yorumlayın:

```py
from adafruit_hid.keyboard_layout_us import KeyboardLayoutUS as KeyboardLayout
from adafruit_hid.keycode import Keycode
```

Bu satırların yorumunu kaldırın:
*Replace `LANG` with the letters for your language of choice. The name must match the file (without the py or mpy extension).*
```py
from keyboard_layout_win_LANG import KeyboardLayout
from keycode_win_LANG import Keycode
```

##### Örnek: Almanca Klavyeye Ayarla (WIN_DE)

```py
from keyboard_layout_win_de import KeyboardLayout
from keycode_win_de import Keycode
```

Keyboard_layout_win_de.mpy ve keycode_win_de.mpy dosyalarını Pico panosundaki /lib klasörüne kopyalayın
```
adafruit_hid/
keyboard_layout_win_de.mpy
keycode_win_de.mpy
```


## Yararlanılan Proje

[Defcon31-ducky](https://github.com/iot-pwn/defcon31-ducky)  
There are still a few of these available to purchase, US only.

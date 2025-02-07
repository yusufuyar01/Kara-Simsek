# Kara Simsek

Bu proje, Arduino kullanarak 4 adet LED'i sırayla yakıp söndürmeyi amaçlar. LED'ler, Arduino'nun dijital pinlerine bağlanır ve belirli bir döngü içinde sırayla yanıp söner.

## Malzemeler

*   Arduino Uno
*   4 adet LED
*   4 adet 220 ohm direnç
*   Jumper kablolar
*   Breadboard (isteğe bağlı)

## Bağlantı Şeması

1.  LED'lerin uzun bacaklarını (anot) dirençlere bağlayın.
2.  Dirençlerin diğer uçlarını Arduino'nun dijital pinlerine (0, 1, 2 ve 3) bağlayın.
3.  LED'lerin kısa bacaklarını (katot) Arduino'nun GND pinine bağlayın.  
  ![Image](https://github.com/user-attachments/assets/b2f23dc9-f820-48ba-a3d2-39965389d902)

## Kod

```c++
int led1 = 0; // 1. LED'i tanımladık ve 0. pine bağladık.
int led2 = 1; // 2. LED'i tanımladık ve 1. pine bağladık.
int led3 = 2; // 3. LED'i tanımladık ve 2. pine bağladık.
int led4 = 3; // 4. LED'i tanımladık ve 3. pine bağladık.
int i; // Pin numarasını belirten i değişkenini atadık.

void setup() {
  pinMode(led1, OUTPUT); // 0. pinden çıkış verdik.
  pinMode(led2, OUTPUT); // 1. pinden çıkış verdik.
  pinMode(led3, OUTPUT); // 2. pinden çıkış verdik.
  pinMode(led4, OUTPUT); // 3. pinden çıkış verdik.
}

void loop() {
  for (i = 0; i <= 3; i++) { // i değeri ilk 0, son 3 değerini alır. Bu değerler pin numarasını belirtir.
    digitalWrite(i, HIGH); // i değişkenine atanan pin numarasına bağlı LED'i yaktık.
    delay(1000); // 1 saniye yanık bekledik.
    digitalWrite(i, LOW); // i değişkenine atanan pin numarasına bağlı LED'i söndürdük.
    delay(1000); // 1 saniye sönük bekledik.
  }
  for (i = 3; i >= 0; i--) { // i değeri ilk 3 (önceki döngünün son değeri), son 0 değerini alır. Bu değerler pin numarasını belirtir.
    digitalWrite(i, HIGH); // i değişkenine atanan pin numarasına bağlı LED'i yaktık.
    delay(1000); // 1 saniye yanık bekledik.
    digitalWrite(i, LOW); // i değişkenine atanan pin numarasına bağlı LED'i söndürdük.
    delay(1000); // 1 saniye sönük bekledik.
  }
}
```  
## Kullanım
Arduino IDE'yi açın ve kodu kopyalayıp yapıştırın.
Arduino kartınızı bilgisayara bağlayın.
Doğru portu seçin ve kodu yükleyin.
LED'lerin sırayla yanıp söndüğünü göreceksiniz.
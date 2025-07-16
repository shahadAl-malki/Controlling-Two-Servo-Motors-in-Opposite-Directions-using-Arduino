#include <Servo.h> 

Servo servo1; // للسيرفو الأول
Servo servo2; // للسيرفو الثاني

void setup() {
  servo1.attach(7); // ربط السيرفو الأول بالبن 7
  servo2.attach(8); // ربط السيرفو الثاني بالبن 8
}

void loop() {
  for (int angle = 0; angle <= 180; angle++) {
    servo1.write(angle);           // السيرفو الأول يتحرك للأمام
    servo2.write(180 - angle);     // السيرفو الثاني يتحرك بالعكس
    delay(15);                     // تأخير بسيط لحركة ناعمة
  }

  delay(500); // انتظار بسيط في النهاية

  for (int angle = 180; angle >= 0; angle--) {
    servo1.write(angle);
    servo2.write(180 - angle);
    delay(15);
  }

  delay(500);
}

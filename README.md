# ARDUINO-NO10
這次的題目是<p>
按左邊的按鈕<p>
字串會往左動一格<p>
按右邊的按鈕<p>
字串會往左動一格<p>
程式如下<p>
 c++```
#include <LiquidCrystal.h>
const int rs = 12, en = 11, d4 = 5, d5 = 4, d6 = 3, d7 = 2;
LiquidCrystal lcd(rs, en, d4, d5, d6, d7);

void setup() {
  lcd.begin(16, 2);
  lcd.print("hello, world!");
   delay(1000);
  lcd.clear();
  for(int i=8;i<10;i++)
  {
    pinMode(i,INPUT);
    digitalWrite(i,1);
  }
  pinMode(7,OUTPUT);
  digitalWrite(7,0);
  
}
void loop() {
      lcd.setCursor(0,1);
      lcd.write("surprise");
   if(digitalRead(9)==0)
   {
      while(digitalRead(9)==0);{delay(10);}
      lcd.scrollDisplayLeft();
   }
   if(digitalRead(8)==0)
   {  
      while(digitalRead(8)==0);{delay(10);}
      lcd.scrollDisplayRight();
   }
   ```
}

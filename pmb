#include "BluetoothSerial.h"
#include <virtuabotixRTC.h>                             

#if !defined(CONFIG_BT_ENABLED) || !defined(CONFIG_BLUEDROID_ENABLED)
#error Bluetooth is not enabled! Please run `make menuconfig` to and enable it
#endif

int CLK_PIN = 16;                                       
int DAT_PIN = 17;                                        
int RST_PIN = 26; 

virtuabotixRTC myRTC(CLK_PIN, DAT_PIN, RST_PIN); 

BluetoothSerial SerialBT;

String message="";
String pazartesi = "";
String sali = "";
String carsamba = "";
String persembe = "";
String cuma = "";
String cumartesi = "";
String pazar = "";

int a=0, b=0, c=0, d=0, e=0, f=0;
char n, y, u1, o1, p1, m1, u2, o2, p2, m2, u3, o3, p3, m3, u4, o4, p4, m4, u5, o5, p5, m5, u6, o6, p6, m6, u7, o7, p7, m7; 

String str1;
String str2;
String str3;
String str4;

void setup() 
{
  pinMode(25, OUTPUT);
  pinMode(27, OUTPUT);
  pinMode(32, OUTPUT);
  pinMode(33, OUTPUT);
  pinMode(5, OUTPUT);
  pinMode(21, OUTPUT);
  pinMode(18, OUTPUT);
  pinMode(19, OUTPUT);
  
 Serial.begin(115200);
  //myRTC.setDS1302Time(10, 22,01, 7, 4, 10, 2020);
  SerialBT.begin("PROMEDBOX");
  Serial.println("The device started, now you can pair it with bluetooth!");
}

void loop() 
{myRTC.updateTime();

  a=myRTC.hours;
    b=myRTC.minutes;
    c=a/10;
    d=a-(c*10);
    e=b/10;
    f=b-(e*10);
  
    char donusum1[2];
    str1=String(c);
    str1.toCharArray(donusum1,2);
    Serial.print("str1=");
    Serial.println(str1);
    
    char donusum2[2];
    str2=String(d);
    str2.toCharArray(donusum2,2);
    Serial.print("str2=");
    Serial.println(str2);

    char donusum3[2];
    str3=String(e);
    str3.toCharArray(donusum3,2);
    Serial.print("str3=");
    Serial.println(str3);

    char donusum4[2];
    str4=String(f);
    str4.toCharArray(donusum4,2);
    Serial.print("str4=");
    Serial.println(str4);
    delay(50);

  if(SerialBT.available()){
     message=SerialBT.readString();
     Serial.print("mesaj=");  
    Serial.print(message);
     Serial.print("  ");
   
   if(message.charAt(4)!='B'){
 switch(message.charAt(11)){
      case '1':
      pazartesi=message;
      break;
      case '2':
      sali=message;
      break;
      case '3':
      carsamba=message;
      break;
      case '4':
      persembe=message;
      break;
      case '5':
      cuma=message;
      break;
      case '6':
      cumartesi=message;
      break;
      case '7':
      pazar=message;
      break;
      default:
      Serial.print("yanlış gün girişi");
      break;
 }}
   
   else if(message.charAt(4)=='B'){
    switch(message.charAt(10)){
      case '1':
      pazartesi=message;
      break;
      case '2':
      sali=message;
      break;
      case '3':
      carsamba=message;
      break;
      case '4':
      persembe=message;
      break;
      case '5':
      cuma=message;
      break;
      case '6':
      cumartesi=message;
      break;
      case '7':
      pazar=message;
      break;
      default:
      Serial.print("yanlış gün girişi");
      break;
   }}
  }
    Serial.print("pazartesi=");
    Serial.println(pazartesi);
    Serial.print("salı=");
    Serial.println(sali);
    Serial.print("çarşamba=");
    Serial.println(carsamba);
    Serial.print("perşembe=");
    Serial.println(persembe);
    Serial.print("cuma=");
    Serial.println(cuma);
    Serial.print("cumartesi=");
    Serial.println(cumartesi);
    Serial.print("pazar=");
    Serial.println(pazar);
 if(a==0){
    u1=str1.charAt(0);
    o1=str2.charAt(0);
    p1=pazartesi.charAt(0);
    m1=pazartesi.charAt(1);
    
    u2=str1.charAt(0);
    o2=str2.charAt(0);
    p2=sali.charAt(0);
    m2=sali.charAt(1); 

    u3=str1.charAt(0);
    o3=str2.charAt(0);
    p3=carsamba.charAt(0);
    m3=carsamba.charAt(1);

    u4=str1.charAt(0);
    o4=str2.charAt(0);
    p4=persembe.charAt(0);
    m4=persembe.charAt(1);

    u5=str1.charAt(0);
    o5=str2.charAt(0);
    p5=cuma.charAt(0);
    m5=cuma.charAt(1);

    u6=str1.charAt(0);
    o6=str2.charAt(0);
    p6=cumartesi.charAt(0);
    m6=cumartesi.charAt(1);

    u7=str1.charAt(0);
    o7=str2.charAt(0);
    p7=pazar.charAt(0);
    m7=pazar.charAt(1);
 }
 else if(b==0){
    u1=pazartesi.charAt(0);
    o1=pazartesi.charAt(1);
    p1=str3.charAt(0);
    m1=str4.charAt(0);
    
    u2=sali.charAt(0);
    o2=sali.charAt(1);
    p2=str3.charAt(0);
    m2=str4.charAt(0); 

    u3=carsamba.charAt(0);
    o3=carsamba.charAt(1);
    p3=str3.charAt(0);
    m3=str4.charAt(0);

    u4=persembe.charAt(0);
    o4=persembe.charAt(1);
    p4=str3.charAt(0);
    m4=str4.charAt(0);

    u5=cuma.charAt(0);
    o5=cuma.charAt(1);
    p5=str3.charAt(0);
    m5=str4.charAt(0);

    u6=cumartesi.charAt(1);
    o6=cumartesi.charAt(0);
    p6=str3.charAt(0);
    m6=str4.charAt(0);

    u7=pazar.charAt(0);
    o7=pazar.charAt(1);
    p7=str3.charAt(0);
    m7=str4.charAt(0);
  }
  else if(a<10 && b<10){
    u1=str1.charAt(0);
    o1=pazartesi.charAt(0);
    p1=str3.charAt(0);
    m1=pazartesi.charAt(1);
    
    u2=str1.charAt(0);
    o2=sali.charAt(0);
    p2=str3.charAt(0);
    m2=sali.charAt(1); 

    u3=str1.charAt(0);
    o3=carsamba.charAt(0);
    p3=str3.charAt(0);
    m3=carsamba.charAt(1);

    u4=str1.charAt(0);
    o4=persembe.charAt(0);
    p4=str3.charAt(0);
    m4=persembe.charAt(1);

    u5=str1.charAt(0);
    o5=cuma.charAt(0);
    p5=str3.charAt(0);
    m5=cuma.charAt(1);

    u6=str1.charAt(0);
    o6=cumartesi.charAt(0);
    p6=str3.charAt(0);
    m6=cumartesi.charAt(2);

    u7=str1.charAt(0);
    o7=pazar.charAt(0);
    p7=str3.charAt(0);
    m7=pazar.charAt(1);
  }
  else if(a<10)
   {
    u1=str1.charAt(0);
    o1=pazartesi.charAt(0);
    p1=pazartesi.charAt(1);
    m1=pazartesi.charAt(2);
    
    u2=str1.charAt(0);
    o2=sali.charAt(0);
    p2=sali.charAt(1);
    m2=sali.charAt(2); 

    u3=str1.charAt(0);
    o3=carsamba.charAt(0);
    p3=carsamba.charAt(1);
    m3=carsamba.charAt(2);

    u4=str1.charAt(0);
    o4=persembe.charAt(0);
    p4=persembe.charAt(1);
    m4=persembe.charAt(2);

    u5=str1.charAt(0);
    o5=cuma.charAt(0);
    p5=cuma.charAt(1);
    m5=cuma.charAt(2);

    u6=str1.charAt(0);
    o6=cumartesi.charAt(0);
    p6=cumartesi.charAt(1);
    m6=cumartesi.charAt(2);

    u7=str1.charAt(0);
    o7=pazar.charAt(0);
    p7=pazar.charAt(1);
    m7=pazar.charAt(2);
   }
   
 else if(b<10)
   {
    p1=str3.charAt(0);
    u1=pazartesi.charAt(0);
    o1=pazartesi.charAt(1);
    m1=pazartesi.charAt(2);
    
    p2=str3.charAt(0);
    u2=sali.charAt(0);
    o2=sali.charAt(1);
    m2=sali.charAt(2); 

    p3=str3.charAt(0);
    u3=carsamba.charAt(0);
    o3=carsamba.charAt(1);
    m3=carsamba.charAt(2);

    p4=str3.charAt(0);
    u4=persembe.charAt(0);
    o4=persembe.charAt(1);
    m4=persembe.charAt(2);

    p5=str3.charAt(0);
    u5=cuma.charAt(0);
    o5=cuma.charAt(1);
    m5=cuma.charAt(2);

    p6=str3.charAt(0);
    u6=cumartesi.charAt(0);
    o6=cumartesi.charAt(1);
    m6=cumartesi.charAt(2);

    p7=str3.charAt(0);
    u7=pazar.charAt(0);
    o7=pazar.charAt(1);
    m7=pazar.charAt(2);
   }
   
   else{
    u1=pazartesi.charAt(0);
    o1=pazartesi.charAt(1);
    p1=pazartesi.charAt(2);
    m1=pazartesi.charAt(3);

    u2=sali.charAt(0);
    o2=sali.charAt(1);
    p2=sali.charAt(2);
    m2=sali.charAt(3);

    u3=carsamba.charAt(0);
    o3=carsamba.charAt(1);
    p3=carsamba.charAt(2);
    m3=carsamba.charAt(3);

    u4=persembe.charAt(0);
    o4=persembe.charAt(1);
    p4=persembe.charAt(2);
    m4=persembe.charAt(3);

    u5=cuma.charAt(0);
    o5=cuma.charAt(1);
    p5=cuma.charAt(2);
    m5=cuma.charAt(3);

    u6=cumartesi.charAt(0);
    o6=cumartesi.charAt(1);
    p6=cumartesi.charAt(2);
    m6=cumartesi.charAt(3);

    u7=pazar.charAt(0);
    o7=pazar.charAt(1);
    p7=pazar.charAt(2);
    m7=pazar.charAt(3);
   }
   
    Serial.println("ATOOOOOOO");
    Serial.print(u2);
    Serial.print(o2);
    Serial.print(":");
    Serial.print(p2);
    Serial.print(m2);
    Serial.println("  ");
    
       
      if(myRTC.dayofweek==7)//-------------------------------------------------> gün karşılaştırması*/
         {  if(pazartesi.charAt(10)=='1')
            { if(str1.charAt(0)==u1 && str2.charAt(0)==o1)
                { if(str3.charAt(0)==p1 && str4.charAt(0)==m1)
                  digitalWrite(25, HIGH);//------------------------------------------------->saat karşılaştırması
                }
            }
          else if(pazartesi.charAt(10)=='2')
          { if(str1.charAt(0)==u1 && str2.charAt(0)==o1)
                { if(str3.charAt(0)==p1 && str4.charAt(0)==m1)
                  digitalWrite(27, HIGH);//------------------------------------------------->saat karşılaştırması
                }
            }
          else if(pazartesi.charAt(10)=='3')
          { if(str1.charAt(0)==u1 && str2.charAt(0)==o1)
                { if(str3.charAt(0)==p1 && str4.charAt(0)==m1)
                  digitalWrite(32, HIGH);//------------------------------------------------->saat karşılaştırması
                }
            }
          else if(pazartesi.charAt(10)=='4')
          {  if(str1.charAt(0)==u1 && str2.charAt(0)==o1)
                { if(str3.charAt(0)==p1 && str4.charAt(0)==m1)
                  digitalWrite(33, HIGH);//-------------------------------------------------> saat karşılaştırması
                }
          }
        }
        if(myRTC.dayofweek==1)//-------------------------------------------------> gün karşılaştırması
         {  //if(sali.charAt(10)=='1')
            { if(str1.charAt(0)==u2 && str2.charAt(0)==o2)
                { if(str3.charAt(0)==p2 && str4.charAt(0)==m2)
                  digitalWrite(25, HIGH);//------------------------------------------------->saat karşılaştırması
                }
            }
          //else if(sali.charAt(10)=='2')
          { if(str1.charAt(0)==u2 && str2.charAt(0)==o2)
                { if(str3.charAt(0)==p2 && str4.charAt(0)==m2)
                  digitalWrite(27, HIGH);//------------------------------------------------->saat karşılaştırması
                }
            }
          //else if(sali.charAt(10)=='3')
          { if(str1.charAt(0)==u2 && str2.charAt(0)==o2)
                { if(str3.charAt(0)==p2 && str4.charAt(0)==m2)
                  digitalWrite(32, HIGH);//------------------------------------------------->saat karşılaştırması
                }
            }
         // else if(sali.charAt(10)=='4')
          {  if(str1.charAt(0)==u2 && str2.charAt(0)==o2)
                { if(str3.charAt(0)==p2 && str4.charAt(0)==m2)
                  digitalWrite(33, HIGH);//-------------------------------------------------> saat karşılaştırması
                }
          }
        }
        if(myRTC.dayofweek==2)//-------------------------------------------------> gün karşılaştırması
         {  if(carsamba.charAt(10)=='1')
            { if(str1.charAt(0)==u3 && str2.charAt(0)==o3)
                { if(str3.charAt(0)==p3 && str4.charAt(0)==m3)
                  digitalWrite(25, HIGH);//------------------------------------------------->saat karşılaştırması
                }
            }
          else if(carsamba.charAt(10)=='2')
          { if(str1.charAt(0)==u3 && str2.charAt(0)==o3)
                { if(str3.charAt(0)==p3 && str4.charAt(0)==m3)
                  digitalWrite(27, HIGH);//------------------------------------------------->saat karşılaştırması
                }
            }
          else if(carsamba.charAt(10)=='3')
          { if(str1.charAt(0)==u3 && str2.charAt(0)==o3)
                { if(str3.charAt(0)==p3 && str4.charAt(0)==m3)
                  digitalWrite(32, HIGH);//------------------------------------------------->saat karşılaştırması
                }
            }
          else if(carsamba.charAt(10)=='4')
          {  if(str1.charAt(0)==u3 && str2.charAt(0)==o3)
                { if(str3.charAt(0)==p3 && str4.charAt(0)==m3)
                  digitalWrite(33, HIGH);//-------------------------------------------------> saat karşılaştırması
                }
          }
        }
        if(myRTC.dayofweek==3)//-------------------------------------------------> gün karşılaştırması
         {  if(persembe.charAt(10)=='1')
            { if(str1.charAt(0)==u4 && str2.charAt(0)==o4)
                { if(str3.charAt(0)==p4 && str4.charAt(0)==m4)
                  digitalWrite(25, HIGH);//------------------------------------------------->saat karşılaştırması
                }
            }
          else if(persembe.charAt(10)=='2')
          { if(str1.charAt(0)==u4 && str2.charAt(0)==o4)
                { if(str3.charAt(0)==p4 && str4.charAt(0)==m4)
                  digitalWrite(27, HIGH);//------------------------------------------------->saat karşılaştırması
                }
            }
          else if(persembe.charAt(10)=='3')
          { if(str1.charAt(0)==u4 && str2.charAt(0)==o4)
                { if(str3.charAt(0)==p4 && str4.charAt(0)==m4)
                  digitalWrite(32, HIGH);//------------------------------------------------->saat karşılaştırması
                }
            }
          else if(persembe.charAt(10)=='4')
          {  if(str1.charAt(0)==u4 && str2.charAt(0)==o4)
                { if(str3.charAt(0)==p4 && str4.charAt(0)==m4)
                  digitalWrite(33, HIGH);//-------------------------------------------------> saat karşılaştırması
                }
          }
        }
        if(myRTC.dayofweek==4)//-------------------------------------------------> gün karşılaştırması
         {  if(cuma.charAt(10)=='1')
            { if(str1.charAt(0)==u5 && str2.charAt(0)==o5)
                { if(str3.charAt(0)==p5 && str4.charAt(0)==m5)
                  digitalWrite(25, HIGH);//------------------------------------------------->saat karşılaştırması
                }
            }
          else if(cuma.charAt(10)=='2')
          { if(str1.charAt(0)==u5 && str2.charAt(0)==o5)
                { if(str3.charAt(0)==p5 && str4.charAt(0)==m5)
                  digitalWrite(27, HIGH);//------------------------------------------------->saat karşılaştırması
                }
            }
          else if(cuma.charAt(10)=='3')
          { if(str1.charAt(0)==u5 && str2.charAt(0)==o5)
                { if(str3.charAt(0)==p5 && str4.charAt(0)==m5)
                  digitalWrite(32, HIGH);//------------------------------------------------->saat karşılaştırması
                }
            }
          else if(cuma.charAt(10)=='4')
          {  if(str1.charAt(0)==u5 && str2.charAt(0)==o5)
                { if(str3.charAt(0)==p5 && str4.charAt(0)==m5)
                  digitalWrite(33, HIGH);//-------------------------------------------------> saat karşılaştırması
                }
          }
        }
        if(myRTC.dayofweek==5)//-------------------------------------------------> gün karşılaştırması
         {  if(cumartesi.charAt(10)=='1')
            { if(str1.charAt(0)==u6 && str2.charAt(0)==o6)
                { if(str3.charAt(0)==p6 && str4.charAt(0)==m6)
                  digitalWrite(25, HIGH);//------------------------------------------------->saat karşılaştırması
                }
            }
          else if(cumartesi.charAt(10)=='2')
          { if(str1.charAt(0)==u6 && str2.charAt(0)==o6)
                { if(str3.charAt(0)==p6 && str4.charAt(0)==m6)
                  digitalWrite(27, HIGH);//------------------------------------------------->saat karşılaştırması
                }
            }
          else if(cumartesi.charAt(10)=='3')
          { if(str1.charAt(0)==u6 && str2.charAt(0)==o6)
                { if(str3.charAt(0)==p6 && str4.charAt(0)==m6)
                  digitalWrite(32, HIGH);//------------------------------------------------->saat karşılaştırması
                }
            }
          else if(cumartesi.charAt(10)=='4')
          {  if(str1.charAt(0)==u6 && str2.charAt(0)==o6)
                { if(str3.charAt(0)==p6 && str4.charAt(0)==m6)
                  digitalWrite(33, HIGH);//-------------------------------------------------> saat karşılaştırması
                }
          }
        }
        if(myRTC.dayofweek==6)//-------------------------------------------------> gün karşılaştırması
         {  if(pazar.charAt(10)=='1')
            { if(str1.charAt(0)==u7 && str2.charAt(0)==o7)
                { if(str3.charAt(0)==p7 && str4.charAt(0)==m7)
                  digitalWrite(25, HIGH);//------------------------------------------------->saat karşılaştırması
                }
            }
          else if(pazar.charAt(10)=='2')
          { if(str1.charAt(0)==u7 && str2.charAt(0)==o7)
                { if(str3.charAt(0)==p7 && str4.charAt(0)==m7)
                  digitalWrite(27, HIGH);//------------------------------------------------->saat karşılaştırması
                }
            }
          else if(pazar.charAt(10)=='3')
          { if(str1.charAt(0)==u7 && str2.charAt(0)==o7)
                { if(str3.charAt(0)==p7 && str4.charAt(0)==m7)
                  digitalWrite(32, HIGH);//------------------------------------------------->saat karşılaştırması
                }
            }
          else if(pazar.charAt(10)=='4')
          {  if(str1.charAt(0)==u7 && str2.charAt(0)==o7)
                { if(str3.charAt(0)==p7 && str4.charAt(0)==m7)
                  digitalWrite(33, HIGH);//-------------------------------------------------> saat karşılaştırması
                }
          }
        }
  
   delay(1000);
      
      
  
 }

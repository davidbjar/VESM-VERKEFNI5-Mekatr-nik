# Skýrsla

# Mekatróník - VESM Verkefni 5
### Hópmeðlimir: Bjarni, Davíð, Jakúb, Ægir


## Verkefna áætlun
Fyrir þetta verkefni vorum við að búa til Mekatróník sem gerir ákveðna hreyfingu þegar hreyfiskynjari kveikjist á. Hreyfinginn er þannig að hann stendur beint upp með bakið sitt beint og þegar honum er svo kveikt á mun hann 'detta'/beygja sig framm og svo að lok hreyfinguna fer aftur til baka í stöðuna sem hann byrjaði í. Hausinn mun titra/snúa til hægri og vinstri hratt þegar hann er niðri/kveiktur á. Hendurnar, sem eru venjulega bendandi fram, snúast og benda upp þegar hann er kveiktur á. Kjalkinn á hausnum er hægt að færa til að 'opna' og 'loka' muninn. Ljós í augun munu líka kveikjast á þegar mekatróníkinn er kveiktur á. Þetta er allt gert með servóum og mótorum.

## Framvinna
Þetta verkefni var mjög tæpt og við náðum ekki að klára verkefna áætluna að fullu. Við vorum að mestu leiti þrír vegna fjarvíst einn hópmeðlima okkar. Mótor og servóarnir fyrir aðal hreyfinguna, hendurnar og kjálkann voru tilbúnir og þyrftu bara kóða/inntak til að virka. Við næstum því náðum að tengja hausinn við aðal mekatrónikinn en tenginginn sem var sett á annaðhvort var ekki rétt eða við notuðum ekki nógum mikinn kraft til að festa hann við servóann. Við náðum að festa led-in í hausnum sem eiga að líta eins og augu. Við náðuð að 'festa' (með límbandi) hátalara en náðum ekki að prófa eða tengja hann. Við gerðum kóðan að nokkru leiti en vegna vandamál þá náðum við ekki að láta aðal-hreyfinguna virka (það var hægt að snúa mótorinn en ekki með Arduino-inn). Við náðum að láta hendurnar snúast og, þótt að við höfðum ekki tíma til að tengja skynjarann þá vorum við búinn að finna út hvernig hann virkar og hvernig við myndum tengja hann.

## Mynd og Myndband
![Mekatrónik](https://user-images.githubusercontent.com/111849477/195637328-f2a0bc2f-4d18-4d5e-a2c0-84448e94be54.png)

[https://www.youtube.com/watch?v=x_cv7uOKOZo](https://youtu.be/zl7V6ZbtFFY)

## Kóði
```c++
#include <Servo.h>

int armPin = 11;
int mainPin = 13;

servo armServo;

void mainStart() {
  analogWrite(mainPin, 255);
}

void mainStop() {
  analogWrite(mainPin, 0);
}

void armUp() {
  armServo.write(180);
}

void armDown() {
  armServo.write(0);
}

void setup() {
  armServo.attach(armPin);
  pinMode(mainPin, OUTPUT);
}

void loop() {
  delay(4000);
  armUp();
  delay(2000);
  armDown();
}
```
## Þakkir til Gauta kennara okkar
Fyrir að hjálpa okkur og aðra mikið í þessu verkefni

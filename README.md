<h3> Втора Лабораториска Вежба по Софтверско Инжењерство </h3>

Милица Јанчевска 153106


1.Дијаграмот Control Flow Graph го нацртав со помош на  алатката  https://app.diagrams.net/ .

Слика ![153106_cfd](https://user-images.githubusercontent.com/81309766/133253487-0f1d2a7f-f693-4ab5-9b80-5f271570db01.png)

2.Следниот дијаграм го изградив според кодот од функцијата  
public List<Integer> function(List<Time>timesList) во класата SILab2.java
  
  Слика ![153106_cfd2](https://user-images.githubusercontent.com/81309766/133253847-07e46655-806c-4720-98b8-d5438784fe24.png)

3.Цикломатската комплексност може да ја добиеме на следниов начин
Преку формулата E-V+2=31-25+2=6+2=8;
E=број на ребра;
V=број на темиња;
Добиваме дека комплексноста е 8.

4.Тест случаи според критериумот Multiple condition и објаснување.
  
Се анализираат само сложените услови if, else if, а такви се вкупно 4.
  
if (hr < 0 || hr > 24)
if (min < 0 || min > 59)
if (sec >= 0 && sec <= 59) 
else if (hr == 24 && min == 0 && sec == 0)

Следно правиме true/false комбинации.
                         

if (hr < 0 || hr > 24) 

T||X : (-4,11,21)
F||T : (25,11,20)
F||F : (14,12,21)

if (min < 0 || min > 59) 

T||X : (13,-13,25)
F||T : (13,85,-3)
F||F : (14,12,21)
           
if (sec >= 0 && sec <= 59)

T&&T : (14,12,21) 
F&&X : (14,20,-33)
T&&F : (14,23,99)

if (hr == 24 && min == 0 && sec == 0)

T&&F&&X : (24,12,0)
T&&T&&F : (24,0,13)
T&&T&&T : (24, 0, 0)

5. Тест случаи според критериумот Every branch и објаснување.
                         
Слика ![153106_eb](https://user-images.githubusercontent.com/81309766/133255871-b0714a1a-5168-4ce0-ba83-6de3d8e9d061.jpg)
                         
Овој критериум ги поминува сите ребра во графот и секое ребро треба да помине барем еднаш за успешно да се изврши тестот.

Првиот тест "shouldThrowExceptionIfHoursSmallerThanMinimum" е за негативен саат.

Вториот тест "shouldThrowExceptionIfHoursAreGreaterThanOneDayMax" е за саати повеќе од 24.

Третиот тест "shouldThrowExceptionIfMinutesAreInvalid" е за негативни минути и за минути повеќе од 59.

Четвртиот тест "shouldSetTheValuesProperlyIfInputDataIsValid" е за ако се е исполнето.

Петиот тест "ShouldThrowExceptionIfSecondsAreNotValid" е за негативни секунди и за секунди повеќе од 59.

Шестиот тест "oneFullDayWithoutAnyExtraMinuteOrSecondsShouldBeValid" е за 24:00:00.

Седмиот тест "shouldThrowExceptionIfDataExceedsOneFullDay" е комбинации за времиња кои се со 24 часот, а со рандом минути и секунди.

Осмиот тест "IfNoTimeSetItShouldBeEqualToZero" е за null вредности.

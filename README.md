# kybjulebordIcalGenerator
Creates an ical-file using the "kybjuleborddatoalgoritmen"

Getting started.
0. Install python3 (python.org)
1. git clone https://github.com/cbratli/kybjulebordIcalGenerator.git 
2. pip3 install -r requirements.txt
3. edit settings.py, insert your email address


Rule: The christmas party will always end on the last sunday in November.

Algorithm that can be used to find the start date in November:

Y = year for Christmas Party

1) Y - 2014
2) Y - 2012. Divide the answer by 4 and round down.
3) Take  answer from 1) + 2)
4) If the answer in 3 is larger than 6, subtract 7 until the number is between 0 og 6.
5) 28 - answer from 4) gives the Friday in November the Christmas party will begin.

The algorithm is valid until year 2099. Because in 2099, there will be no leap year.

The algorithm above can be written as:
KybjulebordStartDateInNovember= 28-mod(year-2010 + floor((year-2000)/4),7)

Example using year 2019
1) 2019 - 2014 = 5
2) 2019-2012 = 7, delt på 4 gir 1.75 som rundet ned gir 1.
3) 1) + 2) = 5 + 1 = 6
4) 6 er ikke større enn 6, så beholder 6.
5) 28-6 = 22. Altså starter kybjulebordet i 2019 på fredag 22. november.

Eksempel for år 2050
1) 2050-2014 = 36
2) (2050-2012)/4= 38/4=9.xxx rundet ned gir det 9.
3) 1)+2) = 36+9=45
4) 45-7*6 = 45-42 = 3 (Her trakk jeg fra tallet 7 hele 6 ganger fr å lande mellom 0 og 6)
5) 28 - 3 =25. Altså i år 2050 starter kybjulebordet fredag 25. november.



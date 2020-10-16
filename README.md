## Genetic Algorithm

``` 
git status
git add
git commit
```

**Population** = (Number of)Possible Solutions
For Knapsack Problem it is combination of items in our backpack

Each possible combination can be encoded with binary
If an item exist in backpack it is represented with 1 
If an item does not exist in backpack it is represented with 0
``` 
>For example:

>All possible items = Laptop, Sunglasses, Mug, Cellphone, Mouse, Keyboard

>Possible Solution 1
>Laptop, Sunglasses -> [1,1,0,0,0,0]

>Possible Solution 2
>Laptop, Mug, Mouse, Keyboard -> [1,0,1,0,1,1]

>Possible Solution 3 
>Laptop, Sunglasses, Mug, Cellphone, Mouse -> [1,1,1,1,1,0]
```
Every (item) 1 and 0 is gene.

0 -> **gene**.

1 -> **gene**.


[0,0,1] -> **chromosome**.

The set of all current solutions are called <b>Generation</b>.

## Natural Selection

We use a **Fitness Function** to determine how good a given solution is.
In our case the fitness function returns *Sum of the weight of items* (as long as it fits the weight limit rule)
If weight limit is exceeded, then fitness function returns 0

We are selecting the parents of next solutions
We take two parents and cut their genomes at random spot and switch the endings
This is called single point crossover function and it generates two new solutions for next generation
>Example:
Parent 1 -> 1 0 0 1
>Parent 2 -> 0 1 1 0

Random point -> * * * [*]
Parent 1 and Parent 2 switches
Parent 1 -> 1 0 0 [1]
Parent 2 -> 0 1 1 [0]

new Parent 1 -> 1 0 0 0
new Parent 2 -> 0 1 1 1

Example 2:
Parent 1 -> 0 0 0 1 1 1
Parent 2 -> 1 1 1 0 0 0

Random point -> * * * [*] * *
Parent 1 and Parent 2 switches
Parent 1 -> 0 0 0 [1 1 1]
Parent 2 -> 1 1 1 [0 0 0]

new Parent 1 -> 0 0 0 0 0 0
new Parent 2 -> 1 1 1 1 1 1

We repeat the process until we have enough solutions(Population(Integer))

Because of randomness there is no guarentee that we dont destroy our best solutions.
That is where elitism comes in. Elitism means we will copy our best n (for example 2) solutions to the next generations untouched.

Using the same gene pool limits our discovery of better solutions.To discover better solutions we use mutations.
During the mutation phase we randomly switch a bit in our binary representations.

Example:

0 0 0 1

  |
  
Randomly selected spot

0 0 0 1 becomes
0 1 0 1

This loop continues until;
1) No possible solution is found
*or*
2) For maximum number of generations

Parts needed for genetic algorithms
1) Genetic representation of a solution
2) A function to generate new solutions
3) Fitness Function
4) Selection Function (to select the solutions for next generation)
5) Crossover Function
6) Mutation Function

# Türkçe - Turkish

## Genetik Algoritma

Popülasyon = Olası Çözümler('in sayısı)
Sırt Çantası Problemi için, sırt çantamızdaki öğelerin kombinasyonudur

Olası her kombinasyon binary olarak kodlanabilir
Sırt çantasında bir eşya varsa, 1 ile temsil edilir
Sırt çantasında bir eşya yoksa 0 ile temsil edilir

Örneğin:

Olası tüm öğeler = Dizüstü Bilgisayar, Güneş Gözlüğü, Kupa, Cep Telefonu, Fare, Klavye

Olası Çözüm 1
Dizüstü bilgisayar, Güneş gözlüğü -> [1,1,0,0,0,0]

Olası Çözüm 2
Dizüstü Bilgisayar, Kupa, Fare, Klavye -> [1,0,1,0,1,1]

Olası Çözüm 3
Dizüstü Bilgisayar, Güneş Gözlüğü, Kupa, Cep Telefonu, Fare -> [1,1,1,1,1,0]

Her (öğe) 1 veya 0 gendir.
0 -> gen
1 -> gen
[0,0,1] -> kromozom

Mevcut tüm çözümler kümesine <b> Nesil </b> denir

Doğal seçilim

Belirli bir çözümün ne kadar iyi olduğunu belirlemek için bir Fitness Fonksiyonu kullanırız.
Bizim durumumuzda uygunluk işlevi, öğelerin ağırlıklarının Toplamını döndürür (ağırlık sınırı kuralına uyduğu sürece)
Ağırlık sınırı aşılırsa uygunluk işlevi 0 değerini döndürür

Sonraki çözümlerin ana unsurlarını seçiyoruz
İki ebeveyni alıyoruz ve genomlarını rastgele bir noktada kesiyoruz ve sonları değiştiriyoruz
Buna tek nokta geçiş işlevi denir ve yeni nesil için iki yeni çözüm üretir
Misal:
Ebeveyn 1 -> 1 0 0 1
Ebeveyn 2 -> 0 1 1 0

Rastgele nokta -> * * * [*]
Ebeveyn 1 ve Ebeveyn 2 anahtarları
Ebeveyn 1 -> 1 0 0 [1]
Ebeveyn 2 -> 0 1 1 [0]

yeni Ebeveyn 1 -> 1 0 0 0
yeni Ebeveyn 2 -> 0 1 1 1

Örnek 2:
Ebeveyn 1 -> 0 0 0 1 1 1
Ebeveyn 2 -> 1 1 1 0 0 0

Rastgele nokta -> * * * [*] * *
Ebeveyn 1 ve Ebeveyn 2 anahtarları
Ebeveyn 1 -> 0 0 0 [1 1 1]
Ebeveyn 2 -> 1 1 1 [0 0 0]

yeni Ebeveyn 1 -> 0 0 0 0 0 0
yeni Ebeveyn 2 -> 1 1 1 1 1 1

Yeterli çözüm bulana kadar süreci tekrar ederiz (Nüfus (Tamsayı))

Rastgelelik nedeniyle, en iyi çözümlerimizi yok etmeyeceğimizin garantisi yoktur.
Elitizm burada devreye girer. Elitizm, en iyi n (örneğin 2) çözümlerimizi el değmeden gelecek nesillere kopyalayacağımız anlamına gelir.

Aynı gen havuzunu kullanmak, daha iyi çözümler keşfetmemizi sınırlar.Daha iyi çözümler keşfetmek için mutasyonları kullanırız.
Mutasyon aşamasında, ikili temsillerimizde rastgele bir şekilde bir bit değiştiriyoruz.
Misal:
0 0 0 1
  |
Rastgele seçilen nokta

0 0 0 1 olur
0 1 0 1

Bu döngü;
1) Olası bir çözüm bulunamadı
veya
2) Maksimum nesil sayısı için

Genetik algoritmalar için gerekli parçalar
1) Bir çözümün genetik temsili
2) Yeni çözümler üretme işlevi
3) Fitness Fonksiyonu
4) Seçim İşlevi (gelecek nesil için çözümleri seçmek için)
5) Crossover İşlevi
6) Mutasyon Fonksiyonu

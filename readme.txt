Traffic Flow
Bu readme.txt dosyasý, Project2 koduna aittir.
Bu paket, kod ile ayný dizin içerisinde bulunacaktýr.

1-PAKETÝN ÝÇERÝÐÝ:
----------
170202017.txt - Traffic Flow'un kaynak kodu.
readme.txt - Bu dosya.


----------
2-SÝSTEM GEREKSÝNÝMLERÝ:
-------------------
Visual Studio 2015, Visual Studio 2015 C++ 
-------------------

3-KURULUM:
-------------------
Visual Studio 2015 C++ kurulmalýdýr.

Allegro 5 kütüphanesi Visual Studio'ya eklenmelidir

https://wiki.allegro.cc/index.php?title=Windows,_Visual_Studio_2015_and_Nuget_Allegro_5

Bu kod, bir adet Windows10 kurulu makinede çalýþtýrýldý

------------------

4-KODU DERLEMEK:
------------------
Visual Studio 2015 ortamýnda C++ kodu derlenirken scanf'in çalýþmasý için bazý ayarlar yapmak gerekebilir.

https://stackoverflow.com/questions/16883037/remove-secure-warnings-crt-secure-no-warnings-from-projects-by-default-in-vis

-------------------
5- PARAMETRELER
---------------------------
Kodun çalýþmasý için baþlangýçta herhangi bir parametre gerekmiyor.
------------------

6- PROGRAMIN KULLANIMI
-----------------------------
Program öncelikle kullanýcýya sunulan iki haritadan birisini seçmesini isteyecek. Seçilen haritada kullanýcý x,y,z,t yollarýndan giriþ ve çýkýþlarý belirleyecek. Giriþ ve çýkýþ olarak belirlenen yollar, daha sonra denklemleri kurarken kontrol edilmek amacýyla girisler[] ve cikislar[] isimli dizilerde kayýt edilir. 
Kullanýcýdan yol yoðunluklarý alýnýr, bilinmeyen yola ‘-1’ deðerini girmesi istenir.
Kullanýcýdan giriþ çýkýþ olmayan yollarýn yönleri alýnýr. Çözümün doðru olabilmesi için yönler ile giriþ çýkýþ olan yollar tutarlý olmalýdýr. Alýnan yönler ve deðerlere göre denklemler kurularak matrise aktarýlýr.
Kurulan matris Gauss Jordan yöntemine göre elementer iþlemler ile birim matris hale getirilerek çözülür.




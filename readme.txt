Traffic Flow
Bu readme.txt dosyas�, Project2 koduna aittir.
Bu paket, kod ile ayn� dizin i�erisinde bulunacakt�r.

1-PAKET�N ��ER���:
----------
170202017.txt - Traffic Flow'un kaynak kodu.
readme.txt - Bu dosya.


----------
2-S�STEM GEREKS�N�MLER�:
-------------------
Visual Studio 2015, Visual Studio 2015 C++ 
-------------------

3-KURULUM:
-------------------
Visual Studio 2015 C++ kurulmal�d�r.

Allegro 5 k�t�phanesi Visual Studio'ya eklenmelidir

https://wiki.allegro.cc/index.php?title=Windows,_Visual_Studio_2015_and_Nuget_Allegro_5

Bu kod, bir adet Windows10 kurulu makinede �al��t�r�ld�

------------------

4-KODU DERLEMEK:
------------------
Visual Studio 2015 ortam�nda C++ kodu derlenirken scanf'in �al��mas� i�in baz� ayarlar yapmak gerekebilir.

https://stackoverflow.com/questions/16883037/remove-secure-warnings-crt-secure-no-warnings-from-projects-by-default-in-vis

-------------------
5- PARAMETRELER
---------------------------
Kodun �al��mas� i�in ba�lang��ta herhangi bir parametre gerekmiyor.
------------------

6- PROGRAMIN KULLANIMI
-----------------------------
Program �ncelikle kullan�c�ya sunulan iki haritadan birisini se�mesini isteyecek. Se�ilen haritada kullan�c� x,y,z,t yollar�ndan giri� ve ��k��lar� belirleyecek. Giri� ve ��k�� olarak belirlenen yollar, daha sonra denklemleri kurarken kontrol edilmek amac�yla girisler[] ve cikislar[] isimli dizilerde kay�t edilir. 
Kullan�c�dan yol yo�unluklar� al�n�r, bilinmeyen yola �-1� de�erini girmesi istenir.
Kullan�c�dan giri� ��k�� olmayan yollar�n y�nleri al�n�r. ��z�m�n do�ru olabilmesi i�in y�nler ile giri� ��k�� olan yollar tutarl� olmal�d�r. Al�nan y�nler ve de�erlere g�re denklemler kurularak matrise aktar�l�r.
Kurulan matris Gauss Jordan y�ntemine g�re elementer i�lemler ile birim matris hale getirilerek ��z�l�r.




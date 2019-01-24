#include <iostream>
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include "allegro5/allegro.h"
#include "allegro5/allegro_image.h"
#include "allegro5/allegro_native_dialog.h"



int main(int argc, char **argv) {



	int haritasecimi;
	ALLEGRO_DISPLAY *display = NULL;
	ALLEGRO_BITMAP  *harita1 = NULL;
	ALLEGRO_BITMAP  *harita2 = NULL;
	ALLEGRO_BITMAP  *ok1 = NULL; float ok1d = 0; float ok1d2 = 0; float ok1d3 = 0;
	ALLEGRO_BITMAP  *ok2 = NULL; float ok2d = 0; float ok2d2 = 0; float ok2d3 = 0;
	ALLEGRO_BITMAP  *ok3 = NULL; float ok3d = 0; float ok3d2 = 0; float ok3d3 = 0;
	ALLEGRO_BITMAP  *ok4 = NULL; float ok4d = 0; float ok4d2 = 0; float ok4d3 = 0;
	ALLEGRO_BITMAP  *ok5 = NULL; float ok5d = 0; float ok5d2 = 0; float ok5d3 = 0;
	ALLEGRO_BITMAP  *ok6 = NULL; float ok6d = 0; float ok6d2 = 0; float ok6d3 = 0;
	ALLEGRO_BITMAP  *ok7 = NULL; float ok7d = 0; float ok7d2 = 0; float ok7d3 = 0;
	ALLEGRO_BITMAP  *ok8 = NULL; float ok8d = 0; float ok8d2 = 0; float ok8d3 = 0;
	ALLEGRO_BITMAP  *ok9 = NULL; float ok9d = 0; float ok9d2 = 0; float ok9d3 = 0;
	ALLEGRO_BITMAP  *ok10 = NULL; float ok10d = 0; float ok10d2 = 0; float ok10d3 = 0;






	//girisler
	char girisler[2];
	char cikislar[2];



	if (!al_init()) {

		return -1;
	}

	if (!al_init_image_addon()) {

		return -1;
	}

	display = al_create_display(1250, 740);

	if (!display) {

		return -1;
	}

	//haritalarýn yüklenmesi iþlemi
	harita1 = al_load_bitmap("harita1.png");
	harita2 = al_load_bitmap("harita2.png");

	//ok görüntülerinin yüklenmesi iþlemi(1.harita)
	//****************************************************************************************************************

	ok1 = al_load_bitmap("ok1.png");
	ok2 = al_load_bitmap("ok2.png");
	ok3 = al_load_bitmap("ok3.png");
	ok4 = al_load_bitmap("ok4.png");
	ok5 = al_load_bitmap("ok5.png");
	ok6 = al_load_bitmap("ok6.png");
	ok7 = al_load_bitmap("ok7.png");
	ok8 = al_load_bitmap("ok8.png");
	ok9 = al_load_bitmap("ok9.png");
	ok10 = al_load_bitmap("ok10.png");
	//****************************************************************************************************************


	if (!harita1 || !harita2) {

		al_destroy_display(display);
		return -1;
	}
	al_draw_bitmap(harita1, 10, 7, 0);
	al_flip_display();
	al_draw_bitmap(harita2, 640, 7, 0);
	al_flip_display();

	//--------------Harita seçim iþlemi-----------------------------

	printf("sececeginiz haritanin numarasini giriniz ");
	scanf("%d", &haritasecimi);

	if (haritasecimi == 1)
	{
		int yollar[8];// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		/* *****bunu araþtýr***** */char yollarhepsi[9] = "xyztabcd";

		al_destroy_display(display);
		display = al_create_display(625, 740);
		al_draw_bitmap(harita1, 10, 7, 0);
		al_flip_display();

		//Giriþ çýkýþ iþlemi için kullanýlan deðiþkenler

		int i = 0;
		int sayac1 = 0;
		int sayac2 = 0;
		int sayac3 = 0;

		//Yönlerin belirlenmesi için kullanýlan deðiþkenler

		char arayollar[] = "abcd";
		char kontrol2[50];
		char kontrol3[50];
		int j = 0;
		int k = 0;
		int v = 0;
		int u = 0;
		//--------------------Giriþ ve çýkýþlarýn belirlenmesi iþlemi----------------------------------

		printf("\n x, y, z, t  ana yollarindan giris ve cikis olanlari seciniz. \n");

		while (1)
		{
			char anayollar[] = "xyzt";
			char kontrol1[5];
			printf("%c:", anayollar[i]);
			scanf("%s", kontrol1);


			if ((strcmp(kontrol1, "giris")) == 0)
			{
				sayac1++;
				sayac3++;

				girisler[u] = anayollar[i];

				if (girisler[u] == anayollar[i])
				{
					i++;
					u++;
				}

				printf("%d\n", sayac1);
				if (sayac1>2)
				{
					i = 0;
					printf("hata!! 2 tane giris veya cikis degeri giriniz.\n");
					sayac1 = 0;
					sayac2 = 0;
					sayac3 = 0;
					u = 0;
				}





			}

			if ((strcmp(kontrol1, "cikis")) == 0)
			{
				sayac2++;
				sayac3++;
				cikislar[v] = anayollar[i];

				if (cikislar[v] == anayollar[i])
				{

					i++;
					v++;
				}

				printf("%d\n", sayac2);
				if (sayac2>2)
				{

					printf("hata!! 2 tane giris veya cikis degeri giriniz.\n");
					sayac1 = 0;
					sayac2 = 0;
					sayac3 = 0;
					i = 0;
					v = 0;
				}




			}

			if ((strcmp(kontrol1, "giris")) != 0 && (strcmp(kontrol1, "cikis")) != 0) {

				printf("\n hata!!! sadece giris veya cikis yaziniz \n");
				int i = 0;
				int sayac1 = 0;
				int sayac2 = 0;
				int sayac3 = 0;
				int u = 0;
			}

			if (sayac3 == 4)
			{
				i = 0;

				break;

			}



		}
		//-----------------------------------------------------------------------------------------------------------------------------------------------
		//kullanýcýdan yoldan geçen ortalama araç deðerlerinin alýnmasý*****************************************************************


		int matrisboyut = 0;

		printf("\n Yollardan gecen ortalama arac sayisini giriniz \n");
		printf("\n Bilinmeyen yol icin -1 giriniz.. \n ");
		for (int k = 0; k <= 7; k++)
		{
			printf("%c yolundan saatte gecen arac sayýsý : ", yollarhepsi[k]);
			scanf("%d", &yollar[k]);
			if (yollar[k] == -1)
			{
				matrisboyut++;
			}

		}




		//-----------------------------------------------------------------------------------------------------------------------------------------------


		// a,b,c,d yollarýnýn yönlerinin kullanýcýdan alýnmasý iþlemi
		while (1)
		{

			// a yolu için yönün belirlenmesi------------------------- 
			if (j == 0)
			{
			m:
				printf("%c yolunun baslangic noktasini giriniz  : ", arayollar[j]);
				rewind(stdin);
				scanf("%c", &kontrol2[0]);
				rewind(stdin);
				if (kontrol2[0] == 'x')
				{
					printf("baslangic noktasi x girilmistir.\n");


				}

				if (kontrol2[0] == 't')
				{
					printf("baslangic noktasi t girilmistir.\n");


				}
				if (kontrol2[0] != 't' && kontrol2[0] != 'x')
				{
					printf(" Hatali baslangic noktasi girdiniz !! x veya t giriniz..\n");
					goto m;
				}

			n:	 rewind(stdin);
				printf("\n%c yolunun yon noktasini giriniz:", arayollar[j]);
				scanf("%c", &kontrol3[0]);
				rewind(stdin);
				if (kontrol3[0] == 'x')
				{

					printf("yon noktasi x girilmistir.\n");



				}

				if (kontrol3[0] == 't')
				{
					printf("yon noktasi t girilmistir.\n");


				}

				if (kontrol3[0] != 't' && kontrol3[0] != 'x')
				{
					printf("\n Hatali yon noktasi girdiniz !! x veya t giriniz..\n");
					goto n;
				}

				if (kontrol2[0] == kontrol3[0])
				{
					printf("\n hata!!! yon noktasi ile baslangic noktasi ayni olamaz.\n");

					goto m;
				}

				//baslangic noktasi t bitis noktasi x
				if (kontrol2[0] == 't' && kontrol3[0] == 'x')
				{
					ok1d2 = 185;
					for (ok1d = 117; ok1d <= 165; ok1d++)
					{
						al_draw_bitmap(harita1, 0, 0, 0);
						al_flip_display();
						al_draw_bitmap(ok1, ok1d, ok1d2, 0);
						al_flip_display();
						al_rest(0.02);
						ok1d2 -= 1.15;

					}


				}

				//baslangic noktasi x bitis noktasi t
				if (kontrol2[0] == 'x' && kontrol3[0] == 't')
				{
					ok2d2 = 110;

					//ok2d arttýkça saða dogru gidiyor
					//ok2d2 arttýkça aþaðý doðru gidiyor
					for (ok2d = 185; ok2d >= 140; ok2d--)
					{
						al_draw_bitmap(harita1, 0, 0, 0);
						al_flip_display();
						al_draw_bitmap(ok2, ok2d, ok2d2, 0);
						al_flip_display();
						al_rest(0.02);
						ok2d2 += 1.15;

					}


				}

			}
			j++; //*******
			break;
		}



		// b yolu için yönün belirlenmesi-------------------------
		while (1)
		{

			if (j == 1)
			{
			ve:
				printf("%c yolunun baslangic noktasini giriniz  : ", arayollar[j]);
				rewind(stdin);
				scanf("%c", &kontrol2[1]);
				rewind(stdin);
				if (kontrol2[1] == 'x')
				{
					printf("baslangic noktasi x girilmistir.\n");

				}

				if (kontrol2[1] == 'y')
				{
					printf("baslangic noktasi y girilmistir.\n");

				}
				if (kontrol2[1] != 'y' && kontrol2[1] != 'x')
				{
					printf(" Hatali baslangic noktasi girdiniz !! x veya y giriniz..\n");
					goto ve;
				}

			vb:   rewind(stdin);
				printf("\n%c yolunun yon noktasini giriniz:", arayollar[j]);
				scanf("%c", &kontrol3[1]);
				rewind(stdin);
				if (kontrol3[1] == 'x')
				{
					printf("yon noktasi x girilmistir.\n");

				}

				if (kontrol3[1] == 'y')
				{
					printf("yon noktasi y girilmistir.\n");
				}

				if (kontrol3[1] != 'y' && kontrol3[1] != 'x')
				{
					printf("\n Hatali yon noktasi girdiniz !! x veya y giriniz..\n");
					goto vb;
				}

				if (kontrol2[1] == kontrol3[1])
				{
					printf("\n hata!!! yon noktasi ile baslangic noktasi ayni olamaz.\n");

					goto ve;
				}


			}
			//**********************************************************************************************************
			//baslangic noktasinin x bitis noktasi y
			if (kontrol2[1] == 'x' && kontrol3[1] == 'y')
			{
				ok3d2 = 130;

				//ok2d arttýkça saða dogru gidiyor
				//ok2d2 arttýkça aþaðý doðru gidiyor
				for (ok3d = 328; ok3d <= 365; ok3d++)
				{
					al_draw_bitmap(harita1, 0, 0, 0);
					al_flip_display();
					al_draw_bitmap(ok3, ok3d, ok3d2, 0);
					al_flip_display();
					al_rest(0.02);
					ok3d2 += 1.15;

				}


			}
			//baslangic noktasi y bitis noktasi x

			if (kontrol2[1] == 'y' && kontrol3[1] == 'x')
			{
				ok4d2 = 190;

				//ok2d arttýkça saða dogru gidiyor
				//ok2d2 arttýkça aþaðý doðru gidiyor
				for (ok4d = 367; ok4d >= 320; ok4d--)
				{
					al_draw_bitmap(harita1, 0, 0, 0);
					al_flip_display();
					al_draw_bitmap(ok4, ok4d, ok4d2, 0);
					al_flip_display();
					al_rest(0.02);
					ok4d2 -= 1.15;

				}


			}


			j++;
			break;
		}



		// c yolunun belirlenmesi---------------------------------------


		while (1)
		{

			if (j == 2)
			{
			vef:
				printf("%c yolunun baslangic noktasini giriniz  : ", arayollar[j]);
				rewind(stdin);
				scanf("%c", &kontrol2[2]);
				rewind(stdin);
				if (kontrol2[2] == 't')
				{
					printf("baslangic noktasi t girilmistir.\n");

				}

				if (kontrol2[2] == 'z')
				{
					printf("baslangic noktasi z girilmistir.\n");

				}
				if (kontrol2[2] != 't' && kontrol2[2] != 'z')
				{
					printf(" Hatali baslangic noktasi girdiniz !! t veya z giriniz..\n");
					goto vef;
				}

			vbc:  rewind(stdin);
				printf("\n%c yolunun yon noktasini giriniz:", arayollar[j]);

				scanf("%c", &kontrol3[2]);
				rewind(stdin);
				if (kontrol3[2] == 't')
				{
					printf("yon noktasi t girilmistir.\n");

				}

				if (kontrol3[2] == 'z')
				{
					printf("yon noktasi z girilmistir.\n");
				}

				if (kontrol3[2] != 't' && kontrol3[2] != 'z')
				{
					printf("\n Hatali yon noktasi girdiniz !! t veya z giriniz..\n");
					goto vbc;
				}

				if (kontrol2[2] == kontrol3[2])
				{
					printf("\n hata!!! yon noktasi ile baslangic noktasi ayni olamaz.\n");

					goto vef;
				}
			}


			//******************************************************************************************************************************************************
			//******************************************************************************************************************************************************
			//baslangic noktasinin t girilmesi durumu

			if (kontrol2[2] == 't' && kontrol3[2] == 'z')
			{
				ok5d2 = 330;

				//ok4d arttýkça saða dogru gidiyor
				//ok4d2 arttýkça aþaðý doðru gidiyor
				for (ok5d = 132; ok5d <= 172; ok5d++)
				{
					al_draw_bitmap(harita1, 0, 0, 0);
					al_flip_display();
					al_draw_bitmap(ok5, ok5d, ok5d2, 0);
					al_flip_display();
					al_rest(0.02);
					ok5d2 += 1.15;

				}


			}

			if (kontrol2[2] == 'z' && kontrol3[2] == 't')
			{
				ok6d2 = 359;

				//ok4d arttýkça saða dogru gidiyor
				//ok4d2 arttýkça aþaðý doðru gidiyor
				for (ok6d = 172; ok6d >= 132; ok6d--)
				{
					al_draw_bitmap(harita1, 0, 0, 0);
					al_flip_display();
					al_draw_bitmap(ok6, ok6d, ok6d2, 0);
					al_flip_display();
					al_rest(0.02);
					ok6d2 -= 1.15;

				}


			}


			j++;
			break;
		}

		// d yolunun belirlenmesi---------------------------

		while (1)
		{

			if (j == 3)
			{
			vefc:
				printf("%c yolunun baslangic noktasini giriniz  : ", arayollar[j]);
				rewind(stdin);
				scanf("%c", &kontrol2[3]);
				rewind(stdin);
				if (kontrol2[3] == 'y')
				{
					printf("baslangic noktasi y girilmistir.\n");

				}

				if (kontrol2[3] == 'z')
				{
					printf("baslangic noktasi z girilmistir.\n");

				}
				if (kontrol2[3] != 'y' && kontrol2[3] != 'z')
				{
					printf(" Hatali baslangic noktasi girdiniz !! y veya z giriniz..\n");
					goto vefc;
				}

			vbcd:  rewind(stdin);
				printf("\n%c yolunun yon noktasini giriniz:", arayollar[j]);

				scanf("%c", &kontrol3[3]);
				rewind(stdin);
				if (kontrol3[3] == 'y')
				{
					printf("yon noktasi y girilmistir.\n");

				}

				if (kontrol3[3] == 'z')
				{
					printf("yon noktasi z girilmistir.\n");
				}

				if (kontrol3[3] != 'y' && kontrol3[3] != 'z')
				{
					printf("\n Hatali yon noktasi girdiniz !! y veya z giriniz..\n");
					goto vbcd;
				}

				if (kontrol2[3] == kontrol3[3])
				{
					printf("\n hata!!! yon noktasi ile baslangic noktasi ayni olamaz.\n");

					goto vefc;
				}
			}


			if (kontrol2[3] == 'z' && kontrol3[3] == 'y')
			{
				ok7d2 = 379;

				//ok4d arttýkça saða dogru gidiyor
				//ok4d2 arttýkça aþaðý doðru gidiyor
				for (ok7d = 308; ok7d < 354; ok7d++)
				{
					al_draw_bitmap(harita1, 0, 0, 0);
					al_flip_display();
					al_draw_bitmap(ok7, ok7d, ok7d2, 0);
					al_flip_display();
					al_rest(0.02);
					ok7d2 -= 1.15;

				}


			}


			if (kontrol2[3] == 'y' && kontrol3[3] == 'z')
			{
				ok8d2 = 325;

				//ok4d arttýkça saða dogru gidiyor
				//ok4d2 arttýkça aþaðý doðru gidiyor
				for (ok8d = 356; ok8d > 309; ok8d--)
				{
					al_draw_bitmap(harita1, 0, 0, 0);
					al_flip_display();
					al_draw_bitmap(ok8, ok8d, ok8d2, 0);
					al_flip_display();
					al_rest(0.02);
					ok8d2 += 1.15;

				}


			}

			break;
		}


		//iþlem kýsmý-----------------------*-*-*-*-*-*-*-*-*-*-*-**-*-*-*-*-*-*-*-*-*-*-*-*------------------------------------
		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//baslangic noktasi x bitis noktasi t

		int *cozummatrisi;

		cozummatrisi = new int[4];
		for (int i = 0; i < 4; i++)
		{
			cozummatrisi[i] = 0;
		}

		int yollarklon[10][11];
		int giristoplam = 0;
		int cikistoplam = 0;

		for (int p = 0; p <= 8; p++)
		{
			for (int k = 0; k <= 9; k++)
			{
				yollarklon[p][k] = 0;
			}

		}


		if (girisler[0] == 'x' || girisler[1] == 'x')
		{
			giristoplam += yollar[0];
			if (yollar[0] == -1)
			{
				yollarklon[0][0] = yollar[0];
				yollarklon[0][0];
				giristoplam++;
			}
		}

		if (girisler[0] == 'y' || girisler[1] == 'y')
		{
			giristoplam += yollar[1];
			if (yollar[1] == -1)
			{
				yollarklon[0][1] = yollar[1];
				yollarklon[0][1];
				giristoplam++;
			}
		}

		if (girisler[0] == 'z' || girisler[1] == 'z')
		{
			giristoplam += yollar[2];
			if (yollar[2] == -1)
			{
				yollarklon[0][2] = yollar[2];
				yollarklon[0][2];
				giristoplam++;
			}
		}
		if (girisler[0] == 't' || girisler[1] == 't')
		{
			giristoplam += yollar[3];
			if (yollar[3] == -1)
			{
				yollarklon[0][3] = yollar[3];
				yollarklon[0][3];
				giristoplam++;
			}
		}


		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d


		if (cikislar[0] == 'x' || cikislar[1] == 'x')
		{
			cikistoplam += yollar[0];
			if (yollar[0] == -1)
			{
				yollarklon[0][0] = yollar[0];
				yollarklon[0][0] = (-yollarklon[0][0]);
				cikistoplam++;;
			}
		}

		if (cikislar[0] == 'y' || cikislar[1] == 'y')
		{
			cikistoplam += yollar[1];
			if (yollar[1] == -1)
			{
				yollarklon[0][1] = yollar[1];
				yollarklon[0][1] = (-yollarklon[0][1]);
				cikistoplam++;
			}
		}
		if (cikislar[0] == 'z' || cikislar[1] == 'z')
		{
			cikistoplam += yollar[2];
			if (yollar[2] == -1)
			{
				yollarklon[0][2] = yollar[2];
				yollarklon[0][2] = (-yollarklon[0][2]);

				cikistoplam++;
			}
		}
		if (cikislar[0] == 't' || cikislar[1] == 't')
		{
			cikistoplam += yollar[3];
			if (yollar[3] == -1)
			{
				yollarklon[0][3] = yollar[3];
				yollarklon[0][3] = (-yollarklon[0][3]);
				cikistoplam++;
			}
		}




		cozummatrisi[0] = giristoplam - cikistoplam;

		yollarklon[0][9] = cozummatrisi[0];





		int** matris = new int*[matrisboyut];
		for (int i = 0; i <= matrisboyut; i++)
		{
			matris[i] = new int[matrisboyut];
		}

		//bilinmeyen sayýsý boyutu kadar matris oluþturulmuþtur
		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//***************************BÝLÝNMEYENLERÝ MATRÝSE ATAMA ÝÞLEMÝ YAPILACAK*******************************************






		//baslangic noktasi t bitis noktasi x

		//-------------------------------------------------------------------------------------------
		if (kontrol2[0] == 't' && kontrol3[0] == 'x' && kontrol2[1] == 'y' && kontrol3[1] == 'x')
		{
			// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d

			if (girisler[0] == 'x' || girisler[1] == 'x')
			{

				//MATRÝS ÇÖZÜMSÜZDÜR!!!!********************************************** GOTO KULLAN.. AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA
				cozummatrisi[1] = -yollar[4] - yollar[5] + yollar[0];

				if (yollar[4] == -1)
				{
					yollarklon[1][4] = yollar[4];
					yollarklon[1][4];
					cozummatrisi[1]--;
				}
				if (yollar[5] == -1)
				{
					yollarklon[1][5] = yollar[5];
					yollarklon[1][5];
					cozummatrisi[1]--;
				}

				if (yollar[0] == -1)
				{
					yollarklon[1][0] = yollar[0];
					yollarklon[1][0] = (-yollarklon[1][0]);
					cozummatrisi[1]++;
				}

				//MATRÝS ÇÖZÜMSÜZDÜR!!!!********************************************** GOTO KULLAN..****************************
			}
			// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
			if (cikislar[0] == 'x' || cikislar[1] == 'x')
			{
				cozummatrisi[1] = yollar[4] + yollar[5] - yollar[0];


				if (yollar[4] == -1)
				{
					yollarklon[1][4] = yollar[4];
					yollarklon[1][4];
					cozummatrisi[1]++;
				}
				if (yollar[5] == -1)
				{
					yollarklon[1][5] = yollar[5];
					yollarklon[1][5];
					cozummatrisi[1]++;
				}

				if (yollar[0] == -1)
				{
					//**
					yollarklon[1][0] = yollar[0];
					yollarklon[1][0] = (-yollarklon[1][0]);
					cozummatrisi[1]--;
				}


			}

		}

		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		if (kontrol2[0] == 't' && kontrol3[0] == 'x' && kontrol2[1] == 'x' && kontrol3[1] == 'y')
		{

			if (girisler[0] == 'x' || girisler[1] == 'x')
			{

				cozummatrisi[1] = -yollar[4] + yollar[5] - yollar[0];


				if (yollar[4] == -1)
				{
					yollarklon[1][4] = yollar[4];
					yollarklon[1][4] = (-yollarklon[1][4]);
					cozummatrisi[1]--;
				}
				if (yollar[5] == -1)
				{
					yollarklon[1][5] = yollar[5];
					yollarklon[1][5];
					cozummatrisi[1]++;
				}

				if (yollar[0] == -1)
				{
					yollarklon[1][0] = yollar[0];
					yollarklon[1][0] = (-yollarklon[1][0]);
					cozummatrisi[1]--;
				}

			}


			if (cikislar[0] == 'x' || cikislar[1] == 'x')
			{
				cozummatrisi[1] = yollar[4] - yollar[5] - yollar[0];
				if (yollar[4] == -1)
				{
					yollarklon[1][4] = yollar[4];
					yollarklon[1][4];
					cozummatrisi[1]++;
				}
				if (yollar[5] == -1)
				{
					yollarklon[1][5] = yollar[5];
					yollarklon[1][5] = (-yollarklon[1][5]);
					cozummatrisi[1]--;
				}

				if (yollar[0] == -1)
				{
					yollarklon[1][0] = yollar[0];
					yollarklon[1][0] = (-yollarklon[1][0]);
					cozummatrisi[1]--;
				}
			}

		}




		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		if (kontrol2[0] == 'x' && kontrol3[0] == 't' && kontrol2[1] == 'x' && kontrol3[1] == 'y')
		{

			if (girisler[0] == 'x' || girisler[1] == 'x')
			{

				cozummatrisi[1] = -yollar[4] - yollar[5] + yollar[0];


				if (yollar[4] == -1)
				{
					yollarklon[1][4] = yollar[4];
					yollarklon[1][4] = (-yollarklon[1][4]);
					cozummatrisi[1]--;
				}
				if (yollar[5] == -1)
				{
					yollarklon[1][5] = yollar[5];
					yollarklon[1][5] = (-yollarklon[1][5]);
					cozummatrisi[1]--;
				}

				if (yollar[0] == -1)
				{
					yollarklon[1][0] = yollar[0];
					yollarklon[1][0];
					cozummatrisi[1]++;
				}

			}


			if (cikislar[0] == 'x' || cikislar[1] == 'x')
			{

				//**MAtris cozulemez............********************************AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA

				cozummatrisi[1] = -yollar[4] - yollar[5] + yollar[0];

				if (yollar[4] == -1)
				{
					yollarklon[1][4] = yollar[4];
					yollarklon[1][4];
					cozummatrisi[1]--;
				}
				if (yollar[5] == -1)
				{
					yollarklon[1][5] = yollar[5];
					yollarklon[1][5];
					cozummatrisi[1]--;
				}

				if (yollar[0] == -1)
				{
					yollarklon[1][0] = yollar[0];
					yollarklon[1][0] = (-yollarklon[1][0]);
					cozummatrisi[1]++;
				}
			}


		}


		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		if (kontrol2[0] == 'x' && kontrol3[0] == 't' && kontrol2[1] == 'y' && kontrol3[1] == 'x')
		{

			if (girisler[0] == 'x' || girisler[1] == 'x')
			{

				cozummatrisi[1] = yollar[4] - yollar[5] - yollar[0];


				if (yollar[4] == -1)
				{
					yollarklon[1][4] = yollar[4];
					yollarklon[1][4];
					cozummatrisi[1]++;
				}
				if (yollar[5] == -1)
				{
					yollarklon[1][5] = yollar[5];
					yollarklon[1][5] = (-yollarklon[1][5]);
					cozummatrisi[1]--;
				}

				if (yollar[0] == -1)
				{
					yollarklon[1][0] = yollar[0];
					yollarklon[1][0] = (-yollarklon[1][0]);
					cozummatrisi[1]--;
				}

			}


			if (cikislar[0] == 'x' || cikislar[1] == 'x')
			{
				cozummatrisi[1] = -yollar[4] + yollar[5] - yollar[0];

				if (yollar[4] == -1)
				{
					yollarklon[1][4] = yollar[4];
					yollarklon[1][4] = (-yollarklon[1][4]);
					cozummatrisi[1]--;
				}
				if (yollar[5] == -1)
				{
					yollarklon[1][5] = yollar[5];
					yollarklon[1][5];
					cozummatrisi[1]++;
				}

				if (yollar[0] == -1)
				{
					yollarklon[1][0] = yollar[0];
					yollarklon[1][0] = (-yollarklon[1][0]);
					cozummatrisi[1]--;
				}
			}
			yollarklon[1][9] = cozummatrisi[1];

		}
		yollarklon[1][9] = cozummatrisi[1];


		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		// b ve d yollarýnýn kontrolü---------------------------------------------------------------------

		if (kontrol2[1] == 'x' && kontrol3[1] == 'y' && kontrol2[3] == 'z' && kontrol3[3] == 'y')
		{

			if (girisler[0] == 'y' || girisler[1] == 'y')
			{

				cozummatrisi[2] = -yollar[5] - yollar[7] - yollar[1];

				//COZUMSUZ MATRÝS OLUR GOTO KULLAN !!!!!!!!!!!!!!!!!!!!!!!!!!!!***********************************************AAAAAAAAAAAAAAAAA

				if (yollar[7] == -1)
				{
					yollarklon[2][7] = yollar[7];
					yollarklon[2][7];
					cozummatrisi[2]--;
				}
				if (yollar[5] == -1)
				{
					yollarklon[2][5] = yollar[5];
					yollarklon[2][5];
					cozummatrisi[2]--;
				}

				if (yollar[1] == -1)
				{
					yollarklon[2][1] = yollar[1];
					yollarklon[2][1];
					cozummatrisi[2]--;
				}

			}


			if (cikislar[0] == 'y' || cikislar[1] == 'y')
			{
				cozummatrisi[2] = yollar[5] + yollar[7] - yollar[1];

				if (yollar[7] == -1)
				{
					yollarklon[2][7] = yollar[7];
					yollarklon[2][7];
					cozummatrisi[2]++;
				}
				if (yollar[5] == -1)
				{
					yollarklon[2][5] = yollar[5];
					yollarklon[2][5];
					cozummatrisi[2]++;
				}

				if (yollar[1] == -1)
				{
					yollarklon[2][1] = yollar[1];
					yollarklon[2][1] = (-yollarklon[2][1]);
					cozummatrisi[2]--;
				}
			}


		}


		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		// b ve d yollarýnýn kontrolü---------------------------------------------------------------------

		if (kontrol2[1] == 'x' && kontrol3[1] == 'y' && kontrol2[3] == 'y' && kontrol3[3] == 'z')
		{

			if (girisler[0] == 'y' || girisler[1] == 'y')
			{

				cozummatrisi[2] = -yollar[5] + yollar[7] - yollar[1];


				if (yollar[7] == -1)
				{
					yollarklon[2][7] = yollar[7];
					yollarklon[2][7];
					cozummatrisi[2]++;
				}
				if (yollar[5] == -1)
				{
					yollarklon[2][5] = yollar[5];
					yollarklon[2][5] = (-yollarklon[2][5]);
					cozummatrisi[2]--;
				}

				if (yollar[1] == -1)
				{
					yollarklon[2][1] = yollar[1];
					yollarklon[2][1] = (-yollarklon[2][1]);
					cozummatrisi[2]--;
				}

			}

			// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
			if (cikislar[0] == 'y' || cikislar[1] == 'y')
			{
				cozummatrisi[2] = yollar[5] - yollar[7] - yollar[1];

				if (yollar[7] == -1)
				{
					yollarklon[2][7] = yollar[7];
					yollarklon[2][7] = (-yollarklon[2][7]);
					cozummatrisi[2]--;
				}
				if (yollar[5] == -1)
				{
					yollarklon[2][5] = yollar[5];
					yollarklon[2][5];
					cozummatrisi[2]++;
				}

				if (yollar[1] == -1)
				{
					yollarklon[2][1] = yollar[1];
					yollarklon[2][1] = (-yollarklon[2][1]);
					cozummatrisi[2]--;
				}
			}


		}




		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		// b ve d yollarýnýn kontrolü---------------------------------------------------------------------

		if (kontrol2[1] == 'y' && kontrol3[1] == 'x' && kontrol2[3] == 'y' && kontrol3[3] == 'z')
		{

			if (girisler[0] == 'y' || girisler[1] == 'y')
			{

				cozummatrisi[2] = -yollar[5] - yollar[7] + yollar[1];


				if (yollar[7] == -1)
				{
					yollarklon[2][7] = yollar[7];
					yollarklon[2][7] = (-yollarklon[2][7]);
					cozummatrisi[2]--;
				}
				if (yollar[5] == -1)
				{
					yollarklon[2][5] = yollar[5];
					yollarklon[2][5] = (-yollarklon[2][5]);
					cozummatrisi[2]--;
				}

				if (yollar[1] == -1)
				{
					yollarklon[2][1] = yollar[1];
					yollarklon[2][1];
					cozummatrisi[2]++;
				}

			}


			if (cikislar[0] == 'y' || cikislar[1] == 'y')
			{
				//**MAtris cozulemez............********************************AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAApasASDASD

				cozummatrisi[2] = -yollar[5] - yollar[7] + yollar[1];

				if (yollar[7] == -1)
				{
					yollarklon[2][7] = yollar[7];
					yollarklon[2][7];
					cozummatrisi[2]--;
				}
				if (yollar[5] == -1)
				{
					yollarklon[2][5] = yollar[5];
					yollarklon[2][5];
					cozummatrisi[2]--;
				}

				if (yollar[1] == -1)
				{
					yollarklon[2][1] = yollar[1];
					yollarklon[2][1] = (-yollarklon[2][1]);
					cozummatrisi[2]++;
				}
			}


		}


		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		// b ve d yollarýnýn kontrolü---------------------------------------------------------------------

		if (kontrol2[1] == 'y' && kontrol3[1] == 'x' && kontrol2[3] == 'z' && kontrol3[3] == 'y')
		{

			if (girisler[0] == 'y' || girisler[1] == 'y')
			{

				cozummatrisi[2] = yollar[5] - yollar[7] - yollar[1];


				if (yollar[7] == -1)
				{
					yollarklon[2][7] = yollar[7];
					yollarklon[2][7] = (-yollarklon[2][7]);
					cozummatrisi[2]--;
				}
				if (yollar[5] == -1)
				{
					yollarklon[2][5] = yollar[5];
					yollarklon[2][5];
					cozummatrisi[2]++;
				}

				if (yollar[1] == -1)
				{
					yollarklon[2][1] = yollar[1];
					yollarklon[2][1] = (-yollarklon[2][1]);
					cozummatrisi[2]--;
				}

			}


			if (cikislar[0] == 'y' || cikislar[1] == 'y')
			{
				cozummatrisi[2] = -yollar[5] + yollar[7] - yollar[1];

				if (yollar[7] == -1)
				{
					yollarklon[2][7] = yollar[7];
					yollarklon[2][7];
					cozummatrisi[2]++;
				}
				if (yollar[5] == -1)
				{
					yollarklon[2][5] = yollar[5];
					yollarklon[2][5] = (-yollarklon[2][5]);
					cozummatrisi[2]--;
				}

				if (yollar[1] == -1)
				{
					yollarklon[2][1] = yollar[1];
					yollarklon[2][1] = (-yollarklon[2][1]);
					cozummatrisi[2]--;
				}
			}
			yollarklon[2][9] = cozummatrisi[2];

		}

		yollarklon[2][9] = cozummatrisi[2];

		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		// c ve d yollarýnýn kontrolü---------------------------------------------------------------------

		if (kontrol2[2] == 't' && kontrol3[2] == 'z' && kontrol2[3] == 'y' && kontrol3[3] == 'z')
		{

			if (girisler[0] == 'z' || girisler[1] == 'z')
			{
				//MATRÝS ÇÖZÜMSÜZDÜR!!!!********************************************** GOTO KULLAN.. AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA

				cozummatrisi[3] = -yollar[6] - yollar[7] - yollar[2];


				if (yollar[7] == -1)
				{
					yollarklon[3][7] = yollar[7];
					yollarklon[3][7];
					cozummatrisi[3]--;
				}
				if (yollar[6] == -1)
				{
					yollarklon[3][6] = yollar[6];
					yollarklon[3][6];
					cozummatrisi[3]--;
				}

				if (yollar[2] == -1)
				{
					yollarklon[3][2] = yollar[2];
					yollarklon[3][2];
					cozummatrisi[3]--;
				}

			}

			// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
			if (cikislar[0] == 'z' || cikislar[1] == 'z')
			{
				cozummatrisi[3] = yollar[6] + yollar[7] - yollar[2];

				if (yollar[7] == -1)
				{
					yollarklon[3][7] = yollar[7];
					yollarklon[3][7];
					cozummatrisi[3]++;
				}
				if (yollar[6] == -1)
				{
					yollarklon[3][6] = yollar[6];
					yollarklon[3][6];
					cozummatrisi[3]++;
				}

				if (yollar[2] == -1)
				{
					yollarklon[3][2] = yollar[2];
					yollarklon[3][2] = (-yollarklon[3][2]);
					cozummatrisi[3]--;
				}
			}


		}

		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		// c ve d yollarýnýn kontrolü---------------------------------------------------------------------

		if (kontrol2[2] == 't' && kontrol3[2] == 'z' && kontrol2[3] == 'z' && kontrol3[3] == 'y')
		{

			if (girisler[0] == 'z' || girisler[1] == 'z')
			{

				cozummatrisi[3] = yollar[6] - yollar[7] + yollar[2];


				if (yollar[7] == -1)
				{
					yollarklon[3][7] = yollar[7];
					yollarklon[3][7] = (-yollarklon[3][7]);
					cozummatrisi[3]--;
				}
				if (yollar[6] == -1)
				{
					yollarklon[3][6] = yollar[6];
					yollarklon[3][6];
					cozummatrisi[3]++;
				}

				if (yollar[2] == -1)
				{
					yollarklon[3][2] = yollar[2];
					yollarklon[3][2];
					cozummatrisi[3]++;
				}

			}

			// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
			if (cikislar[0] == 'z' || cikislar[1] == 'z')
			{
				cozummatrisi[3] = -yollar[6] + yollar[7] + yollar[2];

				if (yollar[7] == -1)
				{
					yollarklon[3][7] = yollar[7];
					yollarklon[3][7];
					cozummatrisi[3]++;
				}
				if (yollar[6] == -1)
				{
					yollarklon[3][6] = yollar[6];
					yollarklon[3][6] = (-yollarklon[3][6]);
					cozummatrisi[3]--;
				}

				if (yollar[2] == -1)
				{
					yollarklon[3][2] = yollar[2];
					yollarklon[3][2];
					cozummatrisi[3]++;
				}
			}


		}


		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		// c ve d yollarýnýn kontrolü---------------------------------------------------------------------

		if (kontrol2[2] == 'z' && kontrol3[2] == 't' && kontrol2[3] == 'z' && kontrol3[3] == 'y')
		{

			if (girisler[0] == 'z' || girisler[1] == 'z')
			{

				cozummatrisi[3] = -yollar[6] - yollar[7] + yollar[2];


				if (yollar[7] == -1)
				{
					yollarklon[3][7] = yollar[7];
					yollarklon[3][7] = (-yollarklon[3][7]);
					cozummatrisi[3]--;
				}
				if (yollar[6] == -1)
				{
					yollarklon[3][6] = yollar[6];
					yollarklon[3][6] = (-yollarklon[3][6]);
					cozummatrisi[3]--;
				}

				if (yollar[2] == -1)
				{
					yollarklon[3][2] = yollar[2];
					yollarklon[3][2];
					cozummatrisi[3]++;
				}

			}


			if (cikislar[0] == 'z' || cikislar[1] == 'z')
			{
				//COZUMSUZ MATRÝS !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!***************************AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA

				cozummatrisi[3] = -yollar[6] - yollar[7] + yollar[2];

				if (yollar[7] == -1)
				{
					yollarklon[3][7] = yollar[7];
					yollarklon[3][7];
					cozummatrisi[3]--;
				}
				if (yollar[6] == -1)
				{
					yollarklon[3][6] = yollar[6];
					yollarklon[3][6];
					cozummatrisi[3]--;
				}

				if (yollar[2] == -1)
				{
					yollarklon[3][2] = yollar[2];
					yollarklon[3][2] = (-yollarklon[3][2]);
					cozummatrisi[3]++;
				}
			}


		}


		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		// c ve d yollarýnýn kontrolü---------------------------------------------------------------------

		if (kontrol2[2] == 'z' && kontrol3[2] == 't' && kontrol2[3] == 'y' && kontrol3[3] == 'z')
		{

			if (girisler[0] == 'z' || girisler[1] == 'z')
			{

				cozummatrisi[3] = -yollar[6] + yollar[7] + yollar[2];


				if (yollar[7] == -1)
				{
					yollarklon[3][7] = yollar[7];
					yollarklon[3][7];
					cozummatrisi[3]++;
				}
				if (yollar[6] == -1)
				{
					yollarklon[3][6] = yollar[6];
					yollarklon[3][6] = (-yollarklon[3][6]);
					cozummatrisi[3]--;
				}

				if (yollar[2] == -1)
				{
					yollarklon[3][2] = yollar[2];
					yollarklon[3][2];
					cozummatrisi[3]++;
				}

			}

			// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
			//-------------------------------------------------------------------------------------------
			if (cikislar[0] == 'z' || cikislar[1] == 'z')
			{
				cozummatrisi[3] = +yollar[6] - yollar[7] + yollar[2];

				if (yollar[7] == -1)
				{
					yollarklon[3][7] = yollar[7];
					yollarklon[3][7] = (-yollarklon[3][7]);
					cozummatrisi[3]--;
				}
				if (yollar[6] == -1)
				{
					yollarklon[3][6] = yollar[6];
					yollarklon[3][6];
					cozummatrisi[3]++;
				}

				if (yollar[2] == -1)
				{
					yollarklon[3][2] = yollar[2];
					yollarklon[3][2];
					cozummatrisi[3]++;
				}
			}
			yollarklon[3][9] = cozummatrisi[3];


		}

		yollarklon[3][9] = cozummatrisi[3];
		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		// c ve a yollarýnýn kontrolü---------------------------------------------------------------------

		if (kontrol2[2] == 'z' && kontrol3[2] == 't' && kontrol2[0] == 'x' && kontrol3[0] == 't')
		{
			//MATRÝS ÇÖZÜMSÜZDÜR!!!!********************************************** GOTO KULLAN..

			if (girisler[0] == 't' || girisler[1] == 't')
			{

				cozummatrisi[4] = -yollar[6] - yollar[4] - yollar[3];


				if (yollar[4] == -1)
				{
					yollarklon[4][4] = yollar[4];
					yollarklon[4][4];
					cozummatrisi[4]--;
				}
				if (yollar[6] == -1)
				{
					yollarklon[4][6] = yollar[6];
					yollarklon[4][6];
					cozummatrisi[4]--;
				}

				if (yollar[3] == -1)
				{
					yollarklon[4][3] = yollar[3];
					yollarklon[4][3];
					cozummatrisi[4]--;
				}

			}


			if (cikislar[0] == 't' || cikislar[1] == 't')
			{
				cozummatrisi[4] = +yollar[6] + yollar[4] - yollar[3];

				if (yollar[4] == -1)
				{
					yollarklon[4][4] = yollar[4];
					yollarklon[4][4];
					cozummatrisi[4]++;
				}
				if (yollar[6] == -1)
				{
					yollarklon[4][6] = yollar[6];
					yollarklon[4][6];
					cozummatrisi[4]++;
				}

				if (yollar[3] == -1)
				{
					yollarklon[4][3] = yollar[3];
					yollarklon[4][3] = (-yollarklon[4][3]);
					cozummatrisi[4]--;
				}
			}


		}


		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		// c ve a yollarýnýn kontrolü---------------------------------------------------------------------

		if (kontrol2[2] == 't' && kontrol3[2] == 'z' && kontrol2[0] == 'x' && kontrol3[0] == 't')
		{


			if (girisler[0] == 't' || girisler[1] == 't')
			{

				cozummatrisi[4] = +yollar[6] - yollar[4] - yollar[3];


				if (yollar[4] == -1)
				{
					yollarklon[4][4] = yollar[4];
					yollarklon[4][4] = (-yollarklon[4][4]);
					cozummatrisi[4]--;
				}
				if (yollar[6] == -1)
				{
					yollarklon[4][6] = yollar[6];
					yollarklon[4][6];
					cozummatrisi[4]++;
				}

				if (yollar[3] == -1)
				{
					yollarklon[4][3] = yollar[3];
					yollarklon[4][3] = (-yollarklon[4][3]);
					cozummatrisi[4]--;
				}

			}


			if (cikislar[0] == 't' || cikislar[1] == 't')
			{
				cozummatrisi[4] = -yollar[6] + yollar[4] - yollar[3];

				if (yollar[4] == -1)
				{
					yollarklon[4][4] = yollar[4];
					yollarklon[4][4];
					cozummatrisi[4]++;
				}
				if (yollar[6] == -1)
				{
					yollarklon[4][6] = yollar[6];
					yollarklon[4][6] = (-yollarklon[4][6]);
					cozummatrisi[4]--;
				}

				if (yollar[3] == -1)
				{
					yollarklon[4][3] = yollar[3];
					yollarklon[4][3] = (-yollarklon[4][3]);
					cozummatrisi[4]--;
				}
			}


		}


		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		// c ve a yollarýnýn kontrolü---------------------------------------------------------------------

		if (kontrol2[2] == 't' && kontrol3[2] == 'z' && kontrol2[0] == 't' && kontrol3[0] == 'x')
		{

			if (girisler[0] == 't' || girisler[1] == 't')
			{

				cozummatrisi[4] = -yollar[6] - yollar[4] + yollar[3];


				if (yollar[4] == -1)
				{
					yollarklon[4][4] = yollar[4];
					yollarklon[4][4] = (-yollarklon[4][4]);
					cozummatrisi[4]--;
				}
				if (yollar[6] == -1)
				{
					yollarklon[4][6] = yollar[6];
					yollarklon[4][6] = (-yollarklon[4][6]);
					cozummatrisi[4]--;
				}

				if (yollar[3] == -1)
				{
					yollarklon[4][3] = yollar[3];
					yollarklon[4][3];
					cozummatrisi[4]++;
				}

			}


			if (cikislar[0] == 't' || cikislar[1] == 't')
			{
				//MATRÝS ÇÖZÜMSÜZDÜR-******************************************-------------*-*-*-*-*-*-*-*-*-*_AAAAAAAAAAAAAAAAAAAAAAAAAAAA


				cozummatrisi[4] = -yollar[6] - yollar[4] + yollar[3];

				if (yollar[4] == -1)
				{
					yollarklon[4][4] = yollar[4];
					yollarklon[4][4];
					cozummatrisi[4]--;
				}
				if (yollar[6] == -1)
				{
					yollarklon[4][6] = yollar[6];
					yollarklon[4][6];
					cozummatrisi[4]--;
				}

				if (yollar[3] == -1)
				{
					yollarklon[4][3] = yollar[3];
					yollarklon[4][3] = (-yollarklon[4][3]);
					cozummatrisi[4]++;
				}
			}


		}

		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		// c ve a yollarýnýn kontrolü---------------------------------------------------------------------

		if (kontrol2[2] == 'z' && kontrol3[2] == 't' && kontrol2[0] == 't' && kontrol3[0] == 'x')
		{

			if (girisler[0] == 't' || girisler[1] == 't')
			{

				cozummatrisi[4] = -yollar[6] + yollar[4] - yollar[3];


				if (yollar[4] == -1)
				{
					yollarklon[4][4] = yollar[4];
					yollarklon[4][4];
					cozummatrisi[4]++;
				}
				if (yollar[6] == -1)
				{
					yollarklon[4][6] = yollar[6];
					yollarklon[4][6] = (-yollarklon[4][6]);
					cozummatrisi[4]--;
				}

				if (yollar[3] == -1)
				{
					yollarklon[4][3] = yollar[3];
					yollarklon[4][3] = (-yollarklon[4][3]);
					cozummatrisi[4]--;
				}

			}


			if (cikislar[0] == 't' || cikislar[1] == 't')
			{
				cozummatrisi[4] = yollar[6] - yollar[4] - yollar[3];

				if (yollar[4] == -1)
				{
					yollarklon[4][4] = yollar[4];
					yollarklon[4][4] = (-yollarklon[4][4]);
					cozummatrisi[4]--;
				}
				if (yollar[6] == -1)
				{
					yollarklon[4][6] = yollar[6];
					yollarklon[4][6];
					cozummatrisi[4]++;
				}

				if (yollar[3] == -1)
				{
					yollarklon[4][3] = yollar[3];
					yollarklon[4][3] = (-yollarklon[4][3]);
					cozummatrisi[4]++;
				}
			}

			yollarklon[4][9] = cozummatrisi[4];

		}
		yollarklon[4][9] = cozummatrisi[4];


		int** matrisson = new int*[matrisboyut + 1];
		for (int i = 0; i <= matrisboyut + 1; i++)
		{
			matrisson[i] = new int[matrisboyut + 1];
		}
		for (int a = 0; a <= matrisboyut; a++)
		{
			for (int b = 0; b <= matrisboyut; b++)
			{
				matrisson[b][a] = 0;

			}

		}

		for (int k = 1; k <= 8; k++)
		{
			printf("x[%d] \t", k);
		}
		printf("\n");

		for (int p = 0; p <= matrisboyut; p++)
		{

			for (int k = 0; k <= 9; k++)
			{
				printf("%d \t", yollarklon[p][k]);

			}


			printf("\n \n");
		}

		int o = 0;
		int zt = 0;
		for (int g = 0; g <= 8; g++)
		{
			for (int tv = 0; tv <= matrisboyut; tv++)
			{


				if (yollarklon[tv][g] == 1 || yollarklon[tv][g] == -1)
				{
					matrisson[tv][o] = yollarklon[tv][g];
					/*matrisson[tv][o + 1] = yollarklon[tv][9];*/
					zt = 1;

				}



			}
			if (zt == 1)
			{
				o++;
				zt = 0;
			}

		}



		for (int tv = 0; tv <= matrisboyut; tv++)
		{


			matrisson[tv][o + 1] = yollarklon[tv][9];


		}





		//DENKLEM MATRÝSÝNÝ YAZDIRMAK





		printf("Denklem Matrisi : \n");
		for (int p = 0; p <= matrisboyut; p++)
		{

			for (int k = 0; k <= o + 1; k++)
			{
				printf("%d \t", matrisson[p][k]);
			}


			printf("\n \n");
		}


		printf("\n \n");
		printf("cozum matrisi : ");
		printf("\n \n");
		for (int i = 0; i <= matrisboyut; i++)
		{
			printf("%d", cozummatrisi[i]);
			printf("\n");
		}
		// GAUSS JORDAN YONTEMÝ************************************************************************************


		printf("\nGauss jordan uygulancak matris \n");
		for (int gj1 = 0; gj1 <= matrisboyut; gj1++)
		{

			for (int gj2 = 0; gj2 < o; gj2++)
			{

				printf("%d \t", matrisson[gj1][gj2]);


			}
			printf("\n \n");

		}
		int gj3 = 0; int gj4 = 0;
		int swapmatris[8][8];
		int swapcozum[8];

		for (int gj2 = 0; gj2 < o + 1; gj2++)
		{
			for (int gj1 = 1; gj1 <= matrisboyut; gj1++)
			{

				if (matrisson[gj1][gj2] == 1)
				{
					if (gj3 != gj1 || gj4 != gj2)
					{
						if (matrisson[gj3][gj4] == 1)
						{

							for (int i = 0; i <= matrisboyut; i++)
							{
								matrisson[gj1][i] -= matrisson[gj3][i];

							}
							cozummatrisi[gj1] -= cozummatrisi[gj3];
							printf("\n matrisson[%d][i]  -  matrisson[%d][i]\n  islemi yapildi", gj1, gj3);
							printf("\n\n");
							for (int gj1 = 0; gj1 <= matrisboyut; gj1++)
							{

								for (int gj2 = 0; gj2 < o; gj2++)
								{

									printf("%d \t", matrisson[gj1][gj2]);


								}
								printf("\n \n");

							}
							printf("\n");

						}
					}
					if (matrisson[gj3][gj4] == -1)
					{

						for (int i = 0; i <= matrisboyut; i++)
						{
							matrisson[gj1][i] += matrisson[gj3][i];


						}
						cozummatrisi[gj1] += cozummatrisi[gj3];
						printf("\n matrisson[%d][i]  +  matrisson[%d][i]\n  islemi yapildi", gj1, gj3);
						printf("\n\n");
						printf("\n\n");
						for (int gj1 = 0; gj1 <= matrisboyut; gj1++)
						{

							for (int gj2 = 0; gj2 < o; gj2++)
							{

								printf("%d \t", matrisson[gj1][gj2]);


							}
							printf("\n \n");

						}
						printf("\n");


					}


					if (matrisson[gj3][gj4] == 0)
					{

						for (int i = 0; i <= matrisboyut; i++)
						{
							swapmatris[gj3][i] = matrisson[gj1][i];
							matrisson[gj1][i] = matrisson[gj3][i];
							matrisson[gj3][i] = swapmatris[gj3][i];
						}
						swapcozum[gj3] = cozummatrisi[gj1];
						cozummatrisi[gj1] = cozummatrisi[gj3];
						cozummatrisi[gj3] = swapcozum[gj3];


						printf("\n \n");
						printf("\n matrisson[%d][i]  ile  matrisson[%d][i]\n  yer degistirildi", gj1, gj3);
						printf("\n\n");
						for (int gj1 = 0; gj1 <= matrisboyut; gj1++)
						{

							for (int gj2 = 0; gj2 < o; gj2++)
							{

								printf("%d \t", matrisson[gj1][gj2]);


							}
							printf("\n \n");

						}
						printf("\n");


					}

				}
				if (matrisson[gj1][gj2] == -1)
				{
					if (matrisson[gj3][gj4] == 1)
					{
						printf("\n ifin icine girdi\n");
						for (int i = 0; i <= matrisboyut; i++)
						{
							matrisson[gj1][i] += matrisson[gj3][i];


						}
						cozummatrisi[gj1] += cozummatrisi[gj3];
						printf("\n matrisson[%d][i]  +  matrisson[%d][i]\n  islemi yapildi", gj1, gj3);
						printf("\n\n");
						for (int gj1 = 0; gj1 <= matrisboyut; gj1++)
						{

							for (int gj2 = 0; gj2 < o; gj2++)
							{

								printf("%d \t", matrisson[gj1][gj2]);


							}
							printf("\n \n");

						}
						printf("\n");

					}
					if (matrisson[gj3][gj4] == -1)
					{
						if (gj3 != gj1 && gj4 != gj2)
						{
							for (int i = 0; i <= matrisboyut; i++)
							{
								matrisson[gj1][i] -= matrisson[gj3][i];


							}
							cozummatrisi[gj1] -= cozummatrisi[gj3];
							printf("\n matrisson[%d][i]  -  matrisson[%d][i]\n  islemi yapildi", gj1, gj3);
							printf("\n\n");
							for (int gj1 = 0; gj1 <= matrisboyut; gj1++)
							{

								for (int gj2 = 0; gj2 < o; gj2++)
								{

									printf("%d \t", matrisson[gj1][gj2]);


								}
								printf("\n \n");

							}
						}
					}



					if (matrisson[gj3][gj4] == 0)
					{

						for (int i = 0; i <= matrisboyut; i++)
						{
							swapmatris[gj3][i] = matrisson[gj1][i];
							matrisson[gj1][i] = matrisson[gj3][i];
							matrisson[gj3][i] = swapmatris[gj3][i];
						}
						swapcozum[gj3] = cozummatrisi[gj1];
						cozummatrisi[gj1] = cozummatrisi[gj3];
						cozummatrisi[gj3] = swapcozum[gj3];

						printf("\n \n");
						printf("\n matrisson[%d][i]  ile  matrisson[%d][i]\n  yer degistirildi", gj1, gj3);

					}
					printf("\n \n");
					for (int gj1 = 0; gj1 <= matrisboyut; gj1++)
					{

						for (int gj2 = 0; gj2 < o; gj2++)
						{

							printf("%d \t", matrisson[gj1][gj2]);


						}
						printf("\n \n");

					}

				}






			}
			gj3++; gj4++;
		}


		for (int gj1 = 0; gj1 <= matrisboyut; gj1++)
		{

			for (int gj2 = 0; gj2 < o; gj2++)
			{

				if (gj1 == gj2)
				{
					if (matrisson[gj1][gj2] == -1)
					{

						for (int i = 0; i < o; i++)
						{
							matrisson[gj1][i] = -matrisson[gj1][i];


						}
						cozummatrisi[gj1] = -cozummatrisi[gj1];
					}
				}


			}


		}


		for (int gj1 = 0; gj1 <= matrisboyut; gj1++)
		{

			for (int gj2 = 0; gj2 < o; gj2++)
			{

				printf("%d \t", matrisson[gj1][gj2]);


			}
			printf("\n \n");

		}

		for (int gj2 = 0; gj2 < o; gj2++)
		{

			printf(" %d \n", cozummatrisi[gj2]);


		}


		int gj5 = 0; int gj6 = 0;
		for (int gj1 = 0; gj1 <= matrisboyut; gj1++)
		{
			for (int gj2 = 1; gj2 < o + 1; gj2++)
			{

				if (gj1 != gj2)
				{


					if (matrisson[gj1][gj2] == -1)
					{

						for (int i = 0; i <= matrisboyut; i++)
						{
							matrisson[gj1][i] += matrisson[gj2][i];


						}
						cozummatrisi[gj1] += cozummatrisi[gj2];
					}

					if (matrisson[gj1][gj2] == +1)
					{

						for (int i = 0; i <= matrisboyut; i++)
						{
							matrisson[gj1][i] -= matrisson[gj2][i];


						}
						cozummatrisi[gj1] -= cozummatrisi[gj2];
					}
				}
			}

		}

		printf("\n\n Sonuc Matrisi : \n");

		for (int gj1 = 0; gj1 <= matrisboyut; gj1++)
		{

			for (int gj2 = 0; gj2 < o; gj2++)
			{

				printf("%d \t", matrisson[gj1][gj2]);


			}
			printf("%d", cozummatrisi[gj1]);
			printf("\n \n");

		}

		printf("\neger matris eselon hale getirilemediyse matris cozumsuzdur.. \n");




		al_rest(900);
	}

	//2. HARÝTA ***********************************************************************************************************************************
	//*********************************************************************************************************************************************
	//*********************************************************************************************************************************************
	if (haritasecimi == 2)
	{
		int yollar[9];// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d, yollar[8] = e
		char yollarhepsi[10] = "xyztabcde";

		al_destroy_display(display);
		display = al_create_display(625, 740);
		al_draw_bitmap(harita2, 10, 7, 0);
		al_flip_display();

		//Giriþ çýkýþ iþlemi için kullanýlan deðiþkenler

		int i = 0;
		int sayac1 = 0;
		int sayac2 = 0;
		int sayac3 = 0;

		//Yönlerin belirlenmesi için kullanýlan deðiþkenler

		char arayollar[] = "abcde";
		char kontrol2[50];
		char kontrol3[50];
		int j = 0;
		int k = 0;
		int v = 0;
		int u = 0;
		//--------------------Giriþ ve çýkýþlarýn belirlenmesi iþlemi----------------------------------

		printf("\n x, y, z, t  ana yollarindan giris ve cikis olanlari seciniz. \n");

		while (1)
		{
			char anayollar[] = "xyzt";
			char kontrol1[5];
			printf("%c:", anayollar[i]);
			scanf("%s", kontrol1);


			if ((strcmp(kontrol1, "giris")) == 0)
			{
				sayac1++;
				sayac3++;


				girisler[u] = anayollar[i];

				if (girisler[u] == anayollar[i])
				{

					u++;
					i++;
				}


				printf("%d\n", sayac1);
				if (sayac1>2)
				{

					printf("hata!! 3 tane giris veya cikis degeri giriniz.\n");
					sayac1 = 0;
					sayac2 = 0;
					sayac3 = 0;
					i = 0;
					u = 0;
				}



			}

			if ((strcmp(kontrol1, "cikis")) == 0)
			{
				sayac2++;
				sayac3++;

				cikislar[v] = anayollar[i];

				if (cikislar[v] == anayollar[i] && sayac2 <= 2)
				{

					v++;
					i++;
				}
				printf("%d\n", sayac2);
				if (sayac2>2)
				{

					printf("hata!! 3 tane giris veya cikis degeri giriniz.\n");
					sayac1 = 0;
					sayac2 = 0;
					sayac3 = 0;
					i = 0;
					v = 0;
				}




			}

			if ((strcmp(kontrol1, "giris")) != 0 && (strcmp(kontrol1, "cikis")) != 0) {

				printf("\n hata!!! sadece giris veya cikis yaziniz \n");
				int i = 0;
				int sayac1 = 0;
				int sayac2 = 0;
				int sayac3 = 0;
				int u = 0;
			}

			if (sayac3 == 4)
			{
				i = 0;

				break;

			}


		}
		//-----------------------------------------------------------------------------------------------------------------------------------------------
		//kullanýcýdan yoldan geçen ortalama araç deðerlerinin alýnmasý*****************************************************************


		int matrisboyut = 0;

		printf("\n Yollardan gecen ortalama arac sayisini giriniz \n");
		printf("\n Bilinmeyen yol icin -1 giriniz.. \n ");
		for (int k = 0; k <= 8; k++)
		{
			printf("%c yolundan saatte gecen arac sayýsý : ", yollarhepsi[k]);
			scanf("%d", &yollar[k]);
			if (yollar[k] == -1)
			{
				matrisboyut++;
			}

		}









		// a,b,c,d,e yollarýnýn yönlerinin kullanýcýdan alýnmasý iþlemi
		while (1)
		{

			// a yolu için yönün belirlenmesi------------------------- 
			if (j == 0)
			{
			m1:
				printf("%c yolunun baslangic noktasini giriniz  : ", arayollar[j]);
				rewind(stdin);
				scanf("%c", &kontrol2[0]);
				rewind(stdin);
				if (kontrol2[0] == 'x')
				{
					printf("baslangic noktasi x girilmistir.\n");


				}

				if (kontrol2[0] == 't')
				{
					printf("baslangic noktasi t girilmistir.\n");


				}
				if (kontrol2[0] != 't' && kontrol2[0] != 'x')
				{
					printf(" Hatali baslangic noktasi girdiniz !! x veya t giriniz..\n");
					goto m1;
				}

			n1:	 rewind(stdin);
				printf("\n%c yolunun yon noktasini giriniz:", arayollar[j]);
				scanf("%c", &kontrol3[0]);
				rewind(stdin);
				if (kontrol3[0] == 'x')
				{

					printf("yon noktasi x girilmistir.\n");



				}

				if (kontrol3[0] == 't')
				{
					printf("yon noktasi t girilmistir.\n");


				}

				if (kontrol3[0] != 't' && kontrol3[0] != 'x')
				{
					printf("\n Hatali yon noktasi girdiniz !! x veya t giriniz..\n");
					goto n1;
				}

				if (kontrol2[0] == kontrol3[0])
				{
					printf("\n hata!!! yon noktasi ile baslangic noktasi ayni olamaz.\n");

					goto m1;
				}

				//baslangic noktasi t bitis noktasi x
				if (kontrol2[0] == 't' && kontrol3[0] == 'x')
				{
					ok1d2 = 185;
					for (ok1d = 117; ok1d <= 165; ok1d++)
					{
						al_draw_bitmap(harita2, 0, 0, 0);
						al_flip_display();
						al_draw_bitmap(ok1, ok1d, ok1d2, 0);
						al_flip_display();
						al_rest(0.02);
						ok1d2 -= 1.15;

					}


				}

				//baslangic noktasi x bitis noktasi t
				if (kontrol2[0] == 'x' && kontrol3[0] == 't')
				{
					ok2d2 = 110;

					//ok2d arttýkça saða dogru gidiyor
					//ok2d2 arttýkça aþaðý doðru gidiyor
					for (ok2d = 185; ok2d >= 140; ok2d--)
					{
						al_draw_bitmap(harita2, 0, 0, 0);
						al_flip_display();
						al_draw_bitmap(ok2, ok2d, ok2d2, 0);
						al_flip_display();
						al_rest(0.02);
						ok2d2 += 1.15;

					}


				}

			}
			j++; //*******
			break;
		}



		// b yolu için yönün belirlenmesi-------------------------
		while (1)
		{

			if (j == 1)
			{
			ve1:
				printf("%c yolunun baslangic noktasini giriniz  : ", arayollar[j]);
				rewind(stdin);
				scanf("%c", &kontrol2[1]);
				rewind(stdin);
				if (kontrol2[1] == 'x')
				{
					printf("baslangic noktasi x girilmistir.\n");

				}

				if (kontrol2[1] == 'y')
				{
					printf("baslangic noktasi y girilmistir.\n");

				}
				if (kontrol2[1] != 'y' && kontrol2[1] != 'x')
				{
					printf(" Hatali baslangic noktasi girdiniz !! x veya y giriniz..\n");
					goto ve1;
				}

			vb1:   rewind(stdin);
				printf("\n%c yolunun yon noktasini giriniz:", arayollar[j]);
				scanf("%c", &kontrol3[1]);
				rewind(stdin);
				if (kontrol3[1] == 'x')
				{
					printf("yon noktasi x girilmistir.\n");

				}

				if (kontrol3[1] == 'y')
				{
					printf("yon noktasi y girilmistir.\n");
				}

				if (kontrol3[1] != 'y' && kontrol3[1] != 'x')
				{
					printf("\n Hatali yon noktasi girdiniz !! x veya y giriniz..\n");
					goto vb1;
				}

				if (kontrol2[1] == kontrol3[1])
				{
					printf("\n hata!!! yon noktasi ile baslangic noktasi ayni olamaz.\n");

					goto ve1;
				}


			}
			//**********************************************************************************************************
			//baslangic noktasinin x bitis noktasi y
			if (kontrol2[1] == 'x' && kontrol3[1] == 'y')
			{
				ok3d2 = 130;

				//ok2d arttýkça saða dogru gidiyor
				//ok2d2 arttýkça aþaðý doðru gidiyor
				for (ok3d = 328; ok3d <= 365; ok3d++)
				{
					al_draw_bitmap(harita2, 0, 0, 0);
					al_flip_display();
					al_draw_bitmap(ok3, ok3d, ok3d2, 0);
					al_flip_display();
					al_rest(0.02);
					ok3d2 += 1.15;

				}


			}
			//baslangic noktasi y bitis noktasi x

			if (kontrol2[1] == 'y' && kontrol3[1] == 'x')
			{
				ok4d2 = 190;

				//ok2d arttýkça saða dogru gidiyor
				//ok2d2 arttýkça aþaðý doðru gidiyor
				for (ok4d = 367; ok4d >= 320; ok4d--)
				{
					al_draw_bitmap(harita2, 0, 0, 0);
					al_flip_display();
					al_draw_bitmap(ok4, ok4d, ok4d2, 0);
					al_flip_display();
					al_rest(0.02);
					ok4d2 -= 1.15;

				}


			}


			j++;
			break;
		}



		// c yolunun belirlenmesi---------------------------------------


		while (1)
		{

			if (j == 2)
			{
			vef1:
				printf("%c yolunun baslangic noktasini giriniz  : ", arayollar[j]);
				rewind(stdin);
				scanf("%c", &kontrol2[2]);
				rewind(stdin);
				if (kontrol2[2] == 't')
				{
					printf("baslangic noktasi t girilmistir.\n");

				}

				if (kontrol2[2] == 'z')
				{
					printf("baslangic noktasi z girilmistir.\n");

				}
				if (kontrol2[2] != 't' && kontrol2[2] != 'z')
				{
					printf(" Hatali baslangic noktasi girdiniz !! t veya z giriniz..\n");
					goto vef1;
				}

			vbc1:  rewind(stdin);
				printf("\n%c yolunun yon noktasini giriniz:", arayollar[j]);

				scanf("%c", &kontrol3[2]);
				rewind(stdin);
				if (kontrol3[2] == 't')
				{
					printf("yon noktasi t girilmistir.\n");

				}

				if (kontrol3[2] == 'z')
				{
					printf("yon noktasi z girilmistir.\n");
				}

				if (kontrol3[2] != 't' && kontrol3[2] != 'z')
				{
					printf("\n Hatali yon noktasi girdiniz !! t veya z giriniz..\n");
					goto vbc1;
				}

				if (kontrol2[2] == kontrol3[2])
				{
					printf("\n hata!!! yon noktasi ile baslangic noktasi ayni olamaz.\n");

					goto vef1;
				}
			}


			//******************************************************************************************************************************************************
			//******************************************************************************************************************************************************
			//baslangic noktasinin t girilmesi durumu

			if (kontrol2[2] == 't' && kontrol3[2] == 'z')
			{
				ok5d2 = 330;

				//ok4d arttýkça saða dogru gidiyor
				//ok4d2 arttýkça aþaðý doðru gidiyor
				for (ok5d = 132; ok5d <= 172; ok5d++)
				{
					al_draw_bitmap(harita2, 0, 0, 0);
					al_flip_display();
					al_draw_bitmap(ok5, ok5d, ok5d2, 0);
					al_flip_display();
					al_rest(0.02);
					ok5d2 += 1.15;

				}


			}

			if (kontrol2[2] == 'z' && kontrol3[2] == 't')
			{
				ok6d2 = 359;

				//ok4d arttýkça saða dogru gidiyor
				//ok4d2 arttýkça aþaðý doðru gidiyor
				for (ok6d = 172; ok6d >= 132; ok6d--)
				{
					al_draw_bitmap(harita2, 0, 0, 0);
					al_flip_display();
					al_draw_bitmap(ok6, ok6d, ok6d2, 0);
					al_flip_display();
					al_rest(0.02);
					ok6d2 -= 1.15;

				}


			}


			j++;
			break;
		}

		// d yolunun belirlenmesi---------------------------

		while (1)
		{

			if (j == 3)
			{
			vefc1:
				printf("%c yolunun baslangic noktasini giriniz  : ", arayollar[j]);
				rewind(stdin);
				scanf("%c", &kontrol2[3]);
				rewind(stdin);
				if (kontrol2[3] == 'y')
				{
					printf("baslangic noktasi y girilmistir.\n");

				}

				if (kontrol2[3] == 'z')
				{
					printf("baslangic noktasi z girilmistir.\n");

				}
				if (kontrol2[3] != 'y' && kontrol2[3] != 'z')
				{
					printf(" Hatali baslangic noktasi girdiniz !! y veya z giriniz..\n");
					goto vefc1;
				}

			vbcd1:  rewind(stdin);
				printf("\n%c yolunun yon noktasini giriniz:", arayollar[j]);

				scanf("%c", &kontrol3[3]);
				rewind(stdin);
				if (kontrol3[3] == 'y')
				{
					printf("yon noktasi y girilmistir.\n");

				}

				if (kontrol3[3] == 'z')
				{
					printf("yon noktasi z girilmistir.\n");
				}

				if (kontrol3[3] != 'y' && kontrol3[3] != 'z')
				{
					printf("\n Hatali yon noktasi girdiniz !! y veya z giriniz..\n");
					goto vbcd1;
				}

				if (kontrol2[3] == kontrol3[3])
				{
					printf("\n hata!!! yon noktasi ile baslangic noktasi ayni olamaz.\n");

					goto vefc1;
				}
			}


			if (kontrol2[3] == 'z' && kontrol3[3] == 'y')
			{
				ok7d2 = 379;

				//ok4d arttýkça saða dogru gidiyor
				//ok4d2 arttýkça aþaðý doðru gidiyor
				for (ok7d = 308; ok7d < 354; ok7d++)
				{
					al_draw_bitmap(harita2, 0, 0, 0);
					al_flip_display();
					al_draw_bitmap(ok7, ok7d, ok7d2, 0);
					al_flip_display();
					al_rest(0.02);
					ok7d2 -= 1.15;

				}


			}


			if (kontrol2[3] == 'y' && kontrol3[3] == 'z')
			{
				ok8d2 = 325;

				//ok4d arttýkça saða dogru gidiyor
				//ok4d2 arttýkça aþaðý doðru gidiyor
				for (ok8d = 356; ok8d > 309; ok8d--)
				{
					al_draw_bitmap(harita2, 0, 0, 0);
					al_flip_display();
					al_draw_bitmap(ok8, ok8d, ok8d2, 0);
					al_flip_display();
					al_rest(0.02);
					ok8d2 += 1.15;

				}


			}
			j++;
			break;
		}



		// e yolunun belirlenmesi---------------------------

		while (1)
		{

			if (j == 4)
			{
			vefc2:
				printf("%c yolunun baslangic noktasini giriniz  : ", arayollar[j]);
				rewind(stdin);
				scanf("%c", &kontrol2[4]);
				rewind(stdin);
				if (kontrol2[4] == 'y')
				{
					printf("baslangic noktasi y girilmistir.\n");

				}

				if (kontrol2[4] == 't')
				{
					printf("baslangic noktasi t girilmistir.\n");

				}
				if (kontrol2[4] != 'y' && kontrol2[4] != 't')
				{
					printf(" Hatali baslangic noktasi girdiniz !! y veya t giriniz..\n");
					goto vefc2;
				}

			vbcd2:  rewind(stdin);
				printf("\n%c yolunun yon noktasini giriniz:", arayollar[j]);

				scanf("%c", &kontrol3[4]);
				rewind(stdin);
				if (kontrol3[4] == 'y')
				{
					printf("yon noktasi y girilmistir.\n");

				}

				if (kontrol3[4] == 't')
				{
					printf("yon noktasi t girilmistir.\n");
				}

				if (kontrol3[4] != 'y' && kontrol3[4] != 't')
				{
					printf("\n Hatali yon noktasi girdiniz !! y veya t giriniz..\n");
					goto vbcd2;
				}

				if (kontrol2[4] == kontrol3[4])
				{
					printf("\n hata!!! yon noktasi ile baslangic noktasi ayni olamaz.\n");

					goto vefc2;
				}
			}


			if (kontrol2[4] == 't' && kontrol3[4] == 'y')
			{
				ok9d2 = 245;

				//ok4d arttýkça saða dogru gidiyor
				//ok4d2 arttýkça aþaðý doðru gidiyor
				for (ok9d = 155; ok9d < 290; ok9d++)
				{
					al_draw_bitmap(harita2, 0, 0, 0);
					al_flip_display();
					al_draw_bitmap(ok9, ok9d, ok9d2, 0);
					al_flip_display();
					al_rest(0.01);


				}


			}


			if (kontrol2[4] == 'y' && kontrol3[4] == 't')
			{
				ok10d2 = 245;

				//ok4d arttýkça saða dogru gidiyor
				//ok4d2 arttýkça aþaðý doðru gidiyor
				for (ok10d = 310; ok10d > 185; ok10d--)
				{
					al_draw_bitmap(harita2, 0, 0, 0);
					al_flip_display();
					al_draw_bitmap(ok10, ok10d, ok10d2, 0);
					al_flip_display();
					al_rest(0.01);


				}


			}

			break;
		}








		//************************************BURDA KALDIM***********************************************************
		//************************************BURDA KALDIM***********************************************************
		//************************************BURDA KALDIM***********************************************************	//************************************BURDA KALDIM***********************************************************
		//************************************BURDA KALDIM***********************************************************
		//************************************BURDA KALDIM***********************************************************
		//************************************BURDA KALDIM***********************************************************
		//************************************BURDA KALDIM***********************************************************
		//************************************BURDA KALDIM***********************************************************
		//iþlem kýsmý-----------------------*-*-*-*-*-*-*-*-*-*-*-**-*-*-*-*-*-*-*-*-*-*-*-*------------------------------------
		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//baslangic noktasi x bitis noktasi t

		int *cozummatrisi;

		cozummatrisi = new int[6];
		for (int i = 0; i < 6; i++)
		{
			cozummatrisi[i] = 0;
		}

		int yollarklon[10][11];
		int giristoplam = 0;
		int cikistoplam = 0;

		for (int p = 0; p <= 8; p++)
		{
			for (int k = 0; k <= 9; k++)
			{
				yollarklon[p][k] = 0;
			}

		}


		if (girisler[0] == 'x' || girisler[1] == 'x')
		{
			giristoplam += yollar[0];
			if (yollar[0] == -1)
			{
				yollarklon[0][0] = yollar[0];
				yollarklon[0][0];
				giristoplam++;
			}
		}

		if (girisler[0] == 'y' || girisler[1] == 'y')
		{
			giristoplam += yollar[1];
			if (yollar[1] == -1)
			{
				yollarklon[0][1] = yollar[1];
				yollarklon[0][1];
				giristoplam++;
			}
		}

		if (girisler[0] == 'z' || girisler[1] == 'z')
		{
			giristoplam += yollar[2];
			if (yollar[2] == -1)
			{
				yollarklon[0][2] = yollar[2];
				yollarklon[0][2];
				giristoplam++;
			}
		}
		if (girisler[0] == 't' || girisler[1] == 't')
		{
			giristoplam += yollar[3];
			if (yollar[3] == -1)
			{
				yollarklon[0][3] = yollar[3];
				yollarklon[0][3];
				giristoplam++;
			}
		}


		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d


		if (cikislar[0] == 'x' || cikislar[1] == 'x')
		{
			cikistoplam += yollar[0];
			if (yollar[0] == -1)
			{
				yollarklon[0][0] = yollar[0];
				yollarklon[0][0] = (-yollarklon[0][0]);
				cikistoplam++;;
			}
		}

		if (cikislar[0] == 'y' || cikislar[1] == 'y')
		{
			cikistoplam += yollar[1];
			if (yollar[1] == -1)
			{
				yollarklon[0][1] = yollar[1];
				yollarklon[0][1] = (-yollarklon[0][1]);
				cikistoplam++;
			}
		}
		if (cikislar[0] == 'z' || cikislar[1] == 'z')
		{
			cikistoplam += yollar[2];
			if (yollar[2] == -1)
			{
				yollarklon[0][2] = yollar[2];
				yollarklon[0][2] = (-yollarklon[0][2]);

				cikistoplam++;
			}
		}
		if (cikislar[0] == 't' || cikislar[1] == 't')
		{
			cikistoplam += yollar[3];
			if (yollar[3] == -1)
			{
				yollarklon[0][3] = yollar[3];
				yollarklon[0][3] = (-yollarklon[0][3]);
				cikistoplam++;
			}
		}




		cozummatrisi[0] = giristoplam - cikistoplam;

		yollarklon[0][9] = cozummatrisi[0];





		int** matris = new int*[matrisboyut];
		for (int i = 0; i <= matrisboyut; i++)
		{
			matris[i] = new int[matrisboyut];
		}

		//bilinmeyen sayýsý boyutu kadar matris oluþturulmuþtur
		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//***************************BÝLÝNMEYENLERÝ MATRÝSE ATAMA ÝÞLEMÝ YAPILACAK*******************************************






		//baslangic noktasi t bitis noktasi x

		//-------------------------------------------------------------------------------------------
		if (kontrol2[0] == 't' && kontrol3[0] == 'x' && kontrol2[1] == 'y' && kontrol3[1] == 'x')
		{
			// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d

			if (girisler[0] == 'x' || girisler[1] == 'x')
			{
				//MATRÝS ÇÖZÜMSÜZDÜR!!!!********************************************** GOTO KULLAN.. AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA
				cozummatrisi[1] = -yollar[4] - yollar[5] + yollar[0];

				if (yollar[4] == -1)
				{
					yollarklon[1][4] = yollar[4];
					yollarklon[1][4];
					cozummatrisi[1]--;
				}
				if (yollar[5] == -1)
				{
					yollarklon[1][5] = yollar[5];
					yollarklon[1][5];
					cozummatrisi[1]--;
				}

				if (yollar[0] == -1)
				{
					yollarklon[1][0] = yollar[0];
					yollarklon[1][0] = (-yollarklon[1][0]);
					cozummatrisi[1]++;
				}

				//MATRÝS ÇÖZÜMSÜZDÜR!!!!********************************************** GOTO KULLAN..****************************
			}
			// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
			if (cikislar[0] == 'x' || cikislar[1] == 'x')
			{
				cozummatrisi[1] = yollar[4] + yollar[5] - yollar[0];


				if (yollar[4] == -1)
				{
					yollarklon[1][4] = yollar[4];
					yollarklon[1][4];
					cozummatrisi[1]++;
				}
				if (yollar[5] == -1)
				{
					yollarklon[1][5] = yollar[5];
					yollarklon[1][5];
					cozummatrisi[1]++;
				}

				if (yollar[0] == -1)
				{
					//**
					yollarklon[1][0] = yollar[0];
					yollarklon[1][0] = (-yollarklon[1][0]);
					cozummatrisi[1]--;
				}


			}

		}

		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		if (kontrol2[0] == 't' && kontrol3[0] == 'x' && kontrol2[1] == 'x' && kontrol3[1] == 'y')
		{

			if (girisler[0] == 'x' || girisler[1] == 'x')
			{

				cozummatrisi[1] = -yollar[4] + yollar[5] - yollar[0];


				if (yollar[4] == -1)
				{
					yollarklon[1][4] = yollar[4];
					yollarklon[1][4] = (-yollarklon[1][4]);
					cozummatrisi[1]--;
				}
				if (yollar[5] == -1)
				{
					yollarklon[1][5] = yollar[5];
					yollarklon[1][5];
					cozummatrisi[1]++;
				}

				if (yollar[0] == -1)
				{
					yollarklon[1][0] = yollar[0];
					yollarklon[1][0] = (-yollarklon[1][0]);
					cozummatrisi[1]--;
				}

			}


			if (cikislar[0] == 'x' || cikislar[1] == 'x')
			{
				cozummatrisi[1] = yollar[4] - yollar[5] - yollar[0];
				if (yollar[4] == -1)
				{
					yollarklon[1][4] = yollar[4];
					yollarklon[1][4];
					cozummatrisi[1]++;
				}
				if (yollar[5] == -1)
				{
					yollarklon[1][5] = yollar[5];
					yollarklon[1][5] = (-yollarklon[1][5]);
					cozummatrisi[1]--;
				}

				if (yollar[0] == -1)
				{
					yollarklon[1][0] = yollar[0];
					yollarklon[1][0] = (-yollarklon[1][0]);
					cozummatrisi[1]--;
				}
			}

		}




		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		if (kontrol2[0] == 'x' && kontrol3[0] == 't' && kontrol2[1] == 'x' && kontrol3[1] == 'y')
		{

			if (girisler[0] == 'x' || girisler[1] == 'x')
			{

				cozummatrisi[1] = -yollar[4] - yollar[5] + yollar[0];


				if (yollar[4] == -1)
				{
					yollarklon[1][4] = yollar[4];
					yollarklon[1][4] = (-yollarklon[1][4]);
					cozummatrisi[1]--;
				}
				if (yollar[5] == -1)
				{
					yollarklon[1][5] = yollar[5];
					yollarklon[1][5] = (-yollarklon[1][5]);
					cozummatrisi[1]--;
				}

				if (yollar[0] == -1)
				{
					yollarklon[1][0] = yollar[0];
					yollarklon[1][0];
					cozummatrisi[1]++;
				}

			}


			if (cikislar[0] == 'x' || cikislar[1] == 'x')
			{

				//**MAtris cozulemez............********************************AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA

				cozummatrisi[1] = -yollar[4] - yollar[5] + yollar[0];

				if (yollar[4] == -1)
				{
					yollarklon[1][4] = yollar[4];
					yollarklon[1][4];
					cozummatrisi[1]--;
				}
				if (yollar[5] == -1)
				{
					yollarklon[1][5] = yollar[5];
					yollarklon[1][5];
					cozummatrisi[1]--;
				}

				if (yollar[0] == -1)
				{
					yollarklon[1][0] = yollar[0];
					yollarklon[1][0] = (-yollarklon[1][0]);
					cozummatrisi[1]++;
				}
			}


		}


		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		if (kontrol2[0] == 'x' && kontrol3[0] == 't' && kontrol2[1] == 'y' && kontrol3[1] == 'x')
		{

			if (girisler[0] == 'x' || girisler[1] == 'x')
			{

				cozummatrisi[1] = yollar[4] - yollar[5] - yollar[0];


				if (yollar[4] == -1)
				{
					yollarklon[1][4] = yollar[4];
					yollarklon[1][4];
					cozummatrisi[1]++;
				}
				if (yollar[5] == -1)
				{
					yollarklon[1][5] = yollar[5];
					yollarklon[1][5] = (-yollarklon[1][5]);
					cozummatrisi[1]--;
				}

				if (yollar[0] == -1)
				{
					yollarklon[1][0] = yollar[0];
					yollarklon[1][0] = (-yollarklon[1][0]);
					cozummatrisi[1]--;
				}

			}


			if (cikislar[0] == 'x' || cikislar[1] == 'x')
			{
				cozummatrisi[1] = -yollar[4] + yollar[5] - yollar[0];

				if (yollar[4] == -1)
				{
					yollarklon[1][4] = yollar[4];
					yollarklon[1][4] = (-yollarklon[1][4]);
					cozummatrisi[1]--;
				}
				if (yollar[5] == -1)
				{
					yollarklon[1][5] = yollar[5];
					yollarklon[1][5];
					cozummatrisi[1]++;
				}

				if (yollar[0] == -1)
				{
					yollarklon[1][0] = yollar[0];
					yollarklon[1][0] = (-yollarklon[1][0]);
					cozummatrisi[1]--;
				}
			}


		}
		yollarklon[1][9] = cozummatrisi[1];


		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d, yollar[8] = e
		//-------------------------------------------------------------------------------------------
		// b ve d yollarýnýn kontrolü---------------------------------------------------------------------

		if (kontrol2[1] == 'x' && kontrol3[1] == 'y' && kontrol2[3] == 'z' && kontrol3[3] == 'y'  && kontrol2[4] == 'y' && kontrol3[4] == 't')
		{

			if (girisler[0] == 'y' || girisler[1] == 'y')
			{

				cozummatrisi[2] = -yollar[5] - yollar[7] - yollar[1] + yollar[8];


				if (yollar[7] == -1)
				{
					yollarklon[2][7] = yollar[7];
					yollarklon[2][7] = (-yollarklon[2][7]);
					cozummatrisi[2]--;
				}
				if (yollar[5] == -1)
				{
					yollarklon[2][5] = yollar[5];
					yollarklon[2][5] = (-yollarklon[2][5]);
					cozummatrisi[2]--;
				}

				if (yollar[1] == -1)
				{
					yollarklon[2][1] = yollar[1];
					yollarklon[2][1] = (-yollarklon[2][1]);
					cozummatrisi[2]--;
				}
				if (yollar[8] == -1)
				{
					yollarklon[2][8] = yollar[8];
					yollarklon[2][8];
					cozummatrisi[2]++;
				}

			}

			// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d, yollar[8] = e
			if (cikislar[0] == 'y' || cikislar[1] == 'y')
			{
				cozummatrisi[2] = yollar[5] + yollar[7] - yollar[1] - yollar[8];

				if (yollar[7] == -1)
				{
					yollarklon[2][7] = yollar[7];
					yollarklon[2][7];
					cozummatrisi[2]++;
				}
				if (yollar[5] == -1)
				{
					yollarklon[2][5] = yollar[5];
					yollarklon[2][5];
					cozummatrisi[2]++;
				}

				if (yollar[1] == -1)
				{
					yollarklon[2][1] = yollar[1];
					yollarklon[2][1] = (-yollarklon[2][1]);
					cozummatrisi[2]--;
				}
				if (yollar[8] == -1)
				{
					yollarklon[2][8] = yollar[8];
					yollarklon[2][8] = (-yollarklon[2][8]);
					cozummatrisi[2]--;
				}
			}


		}


		//---------------------------------------

		if (kontrol2[1] == 'x' && kontrol3[1] == 'y' && kontrol2[3] == 'z' && kontrol3[3] == 'y'  && kontrol2[4] == 't' && kontrol3[4] == 'y')
		{
			//MATRÝS ÇÖZÜMSÜZDÜR.........................------------------------------------ GOTO KULLANAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA
			printf("\n ifin içine girdi...\n");

			if (girisler[0] == 'y' || girisler[1] == 'y')
			{
				printf("\n MATRÝS COZUMSUZDUR..\n");
				cozummatrisi[2] = -yollar[5] - yollar[7] - yollar[1] + yollar[8];


				if (yollar[7] == -1)
				{
					yollarklon[2][7] = yollar[7];
					yollarklon[2][7] = (-yollarklon[2][7]);
					cozummatrisi[2]--;
				}
				if (yollar[5] == -1)
				{
					yollarklon[2][5] = yollar[5];
					yollarklon[2][5] = (-yollarklon[2][5]);
					cozummatrisi[2]--;
				}

				if (yollar[1] == -1)
				{
					yollarklon[2][1] = yollar[1];
					yollarklon[2][1] = (-yollarklon[2][1]);
					cozummatrisi[2]--;
				}
				if (yollar[8] == -1)
				{
					yollarklon[2][8] = yollar[8];
					yollarklon[2][8];
					cozummatrisi[2]++;
				}

			}

			// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d, yollar[8] = e
			if (cikislar[0] == 'y' || cikislar[1] == 'y')
			{
				cozummatrisi[2] = yollar[5] + yollar[7] - yollar[1] + yollar[8];

				if (yollar[7] == -1)
				{
					yollarklon[2][7] = yollar[7];
					yollarklon[2][7];
					cozummatrisi[2]++;
				}
				if (yollar[5] == -1)
				{
					yollarklon[2][5] = yollar[5];
					yollarklon[2][5];
					cozummatrisi[2]++;
				}

				if (yollar[1] == -1)
				{
					yollarklon[2][1] = yollar[1];
					yollarklon[2][1] = (-yollarklon[2][1]);
					cozummatrisi[2]--;
				}
				if (yollar[8] == -1)
				{
					yollarklon[2][8] = yollar[8];
					yollarklon[2][8];
					cozummatrisi[2]++;
				}

				printf("\n %d\t %d\t %d\t ", yollarklon[2][5], yollarklon[2][1], yollarklon[2][8]);
			}


		}




		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		// b ve d yollarýnýn kontrolü---------------------------------------------------------------------

		if (kontrol2[1] == 'x' && kontrol3[1] == 'y' && kontrol2[3] == 'y' && kontrol3[3] == 'z' && kontrol2[4] == 't' && kontrol3[4] == 'y')
		{

			if (girisler[0] == 'y' || girisler[1] == 'y')
			{

				cozummatrisi[2] = -yollar[5] + yollar[7] - yollar[1] - yollar[8];


				if (yollar[7] == -1)
				{
					yollarklon[2][7] = yollar[7];
					yollarklon[2][7];
					cozummatrisi[2]++;
				}
				if (yollar[5] == -1)
				{
					yollarklon[2][5] = yollar[5];
					yollarklon[2][5] = (-yollarklon[2][5]);
					cozummatrisi[2]--;
				}

				if (yollar[1] == -1)
				{
					yollarklon[2][1] = yollar[1];
					yollarklon[2][1] = (-yollarklon[2][1]);
					cozummatrisi[2]--;
				}
				if (yollar[8] == -1)
				{
					yollarklon[2][8] = yollar[8];
					yollarklon[2][8] = (-yollarklon[2][8]);
					cozummatrisi[2]--;
				}

			}

			// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
			if (cikislar[0] == 'y' || cikislar[1] == 'y')
			{
				cozummatrisi[2] = yollar[5] - yollar[7] - yollar[1] + yollar[8];

				if (yollar[7] == -1)
				{
					yollarklon[2][7] = yollar[7];
					yollarklon[2][7] = (-yollarklon[2][7]);
					cozummatrisi[2]--;
				}
				if (yollar[5] == -1)
				{
					yollarklon[2][5] = yollar[5];
					yollarklon[2][5];
					cozummatrisi[2]++;
				}

				if (yollar[1] == -1)
				{
					yollarklon[2][1] = yollar[1];
					yollarklon[2][1] = (-yollarklon[2][1]);
					cozummatrisi[2]--;
				}
				if (yollar[8] == -1)
				{
					yollarklon[2][8] = yollar[8];
					yollarklon[2][8];
					cozummatrisi[2]++;
				}

			}


		}

		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		// b ve d yollarýnýn kontrolü---------------------------------------------------------------------

		if (kontrol2[1] == 'x' && kontrol3[1] == 'y' && kontrol2[3] == 'y' && kontrol3[3] == 'z' && kontrol2[4] == 'y' && kontrol3[4] == 't')
		{

			if (girisler[0] == 'y' || girisler[1] == 'y')
			{

				cozummatrisi[2] = -yollar[5] + yollar[7] - yollar[1] + yollar[8];


				if (yollar[7] == -1)
				{
					yollarklon[2][7] = yollar[7];
					yollarklon[2][7];
					cozummatrisi[2]++;
				}
				if (yollar[5] == -1)
				{
					yollarklon[2][5] = yollar[5];
					yollarklon[2][5] = (-yollarklon[2][5]);
					cozummatrisi[2]--;
				}

				if (yollar[1] == -1)
				{
					yollarklon[2][1] = yollar[1];
					yollarklon[2][1] = (-yollarklon[2][1]);
					cozummatrisi[2]--;
				}
				if (yollar[8] == -1)
				{
					yollarklon[2][8] = yollar[8];
					yollarklon[2][8];
					cozummatrisi[2]++;
				}

			}

			// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
			if (cikislar[0] == 'y' || cikislar[1] == 'y')
			{
				cozummatrisi[2] = yollar[5] - yollar[7] - yollar[1] - yollar[8];

				if (yollar[7] == -1)
				{
					yollarklon[2][7] = yollar[7];
					yollarklon[2][7] = (-yollarklon[2][7]);
					cozummatrisi[2]--;
				}
				if (yollar[5] == -1)
				{
					yollarklon[2][5] = yollar[5];
					yollarklon[2][5];
					cozummatrisi[2]++;
				}

				if (yollar[1] == -1)
				{
					yollarklon[2][1] = yollar[1];
					yollarklon[2][1] = (-yollarklon[2][1]);
					cozummatrisi[2]--;
				}
				if (yollar[8] == -1)
				{
					yollarklon[2][8] = yollar[8];
					yollarklon[2][8] = (-yollarklon[2][8]);
					cozummatrisi[2]--;
				}

			}


		}



		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		// b ve d yollarýnýn kontrolü---------------------------------------------------------------------

		if (kontrol2[1] == 'y' && kontrol3[1] == 'x' && kontrol2[3] == 'y' && kontrol3[3] == 'z' && kontrol2[4] == 'y' && kontrol3[4] == 't')
		{

			if (girisler[0] == 'y' || girisler[1] == 'y')
			{

				cozummatrisi[2] = -yollar[5] - yollar[7] + yollar[1] - yollar[8];


				if (yollar[7] == -1)
				{
					yollarklon[2][7] = yollar[7];
					yollarklon[2][7] = (-yollarklon[2][7]);
					cozummatrisi[2]--;
				}
				if (yollar[5] == -1)
				{
					yollarklon[2][5] = yollar[5];
					yollarklon[2][5] = (-yollarklon[2][5]);
					cozummatrisi[2]--;
				}

				if (yollar[1] == -1)
				{
					yollarklon[2][1] = yollar[1];
					yollarklon[2][1];
					cozummatrisi[2]++;
				}
				if (yollar[8] == -1)
				{
					yollarklon[2][8] = yollar[8];
					yollarklon[2][8] = (-yollarklon[2][8]);
					cozummatrisi[2]--;
				}

			}


			if (cikislar[0] == 'y' || cikislar[1] == 'y')
			{
				//*******************MAtris cozulemez............********************************AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAApasASDASD
				cozummatrisi[2] = -yollar[5] - yollar[7] + yollar[1];

				if (yollar[7] == -1)
				{
					yollarklon[2][7] = yollar[7];
					yollarklon[2][7];
					cozummatrisi[2]--;
				}
				if (yollar[5] == -1)
				{
					yollarklon[2][5] = yollar[5];
					yollarklon[2][5];
					cozummatrisi[2]--;
				}

				if (yollar[1] == -1)
				{
					yollarklon[2][1] = yollar[1];
					yollarklon[2][1] = (-yollarklon[2][1]);
					cozummatrisi[2]++;
				}
			}


		}

		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		// b ve d yollarýnýn kontrolü---------------------------------------------------------------------

		if (kontrol2[1] == 'y' && kontrol3[1] == 'x' && kontrol2[3] == 'y' && kontrol3[3] == 'z' && kontrol2[4] == 't' && kontrol3[4] == 'y')
		{

			if (girisler[0] == 'y' || girisler[1] == 'y')
			{

				cozummatrisi[2] = -yollar[5] - yollar[7] + yollar[1] + yollar[8];


				if (yollar[7] == -1)
				{
					yollarklon[2][7] = yollar[7];
					yollarklon[2][7] = (-yollarklon[2][7]);
					cozummatrisi[2]--;
				}
				if (yollar[5] == -1)
				{
					yollarklon[2][5] = yollar[5];
					yollarklon[2][5] = (-yollarklon[2][5]);
					cozummatrisi[2]--;
				}

				if (yollar[1] == -1)
				{
					yollarklon[2][1] = yollar[1];
					yollarklon[2][1];
					cozummatrisi[2]++;
				}
				if (yollar[8] == -1)
				{
					yollarklon[2][8] = yollar[8];
					yollarklon[2][8];
					cozummatrisi[2]++;
				}

			}


			if (cikislar[0] == 'y' || cikislar[1] == 'y')
			{

				cozummatrisi[2] = -yollar[5] - yollar[7] - yollar[1] + yollar[8];

				if (yollar[7] == -1)
				{
					yollarklon[2][7] = yollar[7];
					yollarklon[2][7] = (-yollarklon[2][7]);
					cozummatrisi[2]--;
				}
				if (yollar[5] == -1)
				{
					yollarklon[2][5] = yollar[5];
					yollarklon[2][5] = (-yollarklon[2][5]);
					cozummatrisi[2]--;
				}

				if (yollar[1] == -1)
				{
					yollarklon[2][1] = yollar[1];
					yollarklon[2][1] = (-yollarklon[2][1]);
					cozummatrisi[2]--;
				}

				if (yollar[8] == -1)
				{
					yollarklon[2][8] = yollar[8];
					yollarklon[2][8];
					cozummatrisi[2]++;
				}
			}


		}


		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		// b ve d yollarýnýn kontrolü---------------------------------------------------------------------

		if (kontrol2[1] == 'y' && kontrol3[1] == 'x' && kontrol2[3] == 'z' && kontrol3[3] == 'y' && kontrol2[4] == 'y' && kontrol3[4] == 't')
		{

			if (girisler[0] == 'y' || girisler[1] == 'y')
			{

				cozummatrisi[2] = yollar[5] - yollar[7] - yollar[1] + yollar[8];


				if (yollar[7] == -1)
				{
					yollarklon[2][7] = yollar[7];
					yollarklon[2][7] = (-yollarklon[2][7]);
					cozummatrisi[2]--;
				}
				if (yollar[5] == -1)
				{
					yollarklon[2][5] = yollar[5];
					yollarklon[2][5];
					cozummatrisi[2]++;
				}

				if (yollar[1] == -1)
				{
					yollarklon[2][1] = yollar[1];
					yollarklon[2][1] = (-yollarklon[2][1]);
					cozummatrisi[2]--;
				}
				if (yollar[8] == -1)
				{
					yollarklon[2][8] = yollar[8];
					yollarklon[2][8];
					cozummatrisi[2]++;
				}
			}


			if (cikislar[0] == 'y' || cikislar[1] == 'y')
			{
				cozummatrisi[2] = -yollar[5] + yollar[7] - yollar[1] - yollar[8];

				if (yollar[7] == -1)
				{
					yollarklon[2][7] = yollar[7];
					yollarklon[2][7];
					cozummatrisi[2]++;
				}
				if (yollar[5] == -1)
				{
					yollarklon[2][5] = yollar[5];
					yollarklon[2][5] = (-yollarklon[2][5]);
					cozummatrisi[2]--;
				}

				if (yollar[1] == -1)
				{
					yollarklon[2][1] = yollar[1];
					yollarklon[2][1] = (-yollarklon[2][1]);
					cozummatrisi[2]--;
				}
				if (yollar[8] == -1)
				{
					yollarklon[2][8] = yollar[8];
					yollarklon[2][8] = (-yollarklon[2][8]);
					cozummatrisi[2]--;
				}
			}


		}



		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		// b ve d yollarýnýn kontrolü---------------------------------------------------------------------

		if (kontrol2[1] == 'y' && kontrol3[1] == 'x' && kontrol2[3] == 'z' && kontrol3[3] == 'y' && kontrol2[4] == 't' && kontrol3[4] == 'y')
		{

			if (girisler[0] == 'y' || girisler[1] == 'y')
			{

				cozummatrisi[2] = yollar[5] - yollar[7] - yollar[1] - yollar[8];


				if (yollar[7] == -1)
				{
					yollarklon[2][7] = yollar[7];
					yollarklon[2][7] = (-yollarklon[2][7]);
					cozummatrisi[2]--;
				}
				if (yollar[5] == -1)
				{
					yollarklon[2][5] = yollar[5];
					yollarklon[2][5];
					cozummatrisi[2]++;
				}

				if (yollar[1] == -1)
				{
					yollarklon[2][1] = yollar[1];
					yollarklon[2][1] = (-yollarklon[2][1]);
					cozummatrisi[2]--;
				}
				if (yollar[8] == -1)
				{
					yollarklon[2][8] = yollar[8];
					yollarklon[2][8] = (-yollarklon[2][8]);
					cozummatrisi[2]--;
				}
			}


			if (cikislar[0] == 'y' || cikislar[1] == 'y')
			{
				cozummatrisi[2] = -yollar[5] + yollar[7] - yollar[1] + yollar[8];

				if (yollar[7] == -1)
				{
					yollarklon[2][7] = yollar[7];
					yollarklon[2][7];
					cozummatrisi[2]++;
				}
				if (yollar[5] == -1)
				{
					yollarklon[2][5] = yollar[5];
					yollarklon[2][5] = (-yollarklon[2][5]);
					cozummatrisi[2]--;
				}

				if (yollar[1] == -1)
				{
					yollarklon[2][1] = yollar[1];
					yollarklon[2][1] = (-yollarklon[2][1]);
					cozummatrisi[2]--;
				}
				if (yollar[8] == -1)
				{
					yollarklon[2][8] = yollar[8];
					yollarklon[2][8];
					cozummatrisi[2]++;
				}
			}


		}

		yollarklon[2][9] = cozummatrisi[2];

		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		// c ve d yollarýnýn kontrolü---------------------------------------------------------------------

		if (kontrol2[2] == 't' && kontrol3[2] == 'z' && kontrol2[3] == 'y' && kontrol3[3] == 'z')
		{

			if (girisler[0] == 'z' || girisler[1] == 'z')
			{
				//MATRÝS ÇÖZÜMSÜZDÜR!!!!********************************************** GOTO KULLAN.. AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA
				cozummatrisi[3] = -yollar[6] - yollar[7] - yollar[2];


				if (yollar[7] == -1)
				{
					yollarklon[3][7] = yollar[7];
					yollarklon[3][7];
					cozummatrisi[3]--;
				}
				if (yollar[6] == -1)
				{
					yollarklon[3][6] = yollar[6];
					yollarklon[3][6];
					cozummatrisi[3]--;
				}

				if (yollar[2] == -1)
				{
					yollarklon[3][2] = yollar[2];
					yollarklon[3][2];
					cozummatrisi[3]--;
				}

			}

			// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
			if (cikislar[0] == 'z' || cikislar[1] == 'z')
			{
				cozummatrisi[3] = yollar[6] + yollar[7] - yollar[2];

				if (yollar[7] == -1)
				{
					yollarklon[3][7] = yollar[7];
					yollarklon[3][7];
					cozummatrisi[3]++;
				}
				if (yollar[6] == -1)
				{
					yollarklon[3][6] = yollar[6];
					yollarklon[3][6];
					cozummatrisi[3]++;
				}

				if (yollar[2] == -1)
				{
					yollarklon[3][2] = yollar[2];
					yollarklon[3][2] = (-yollarklon[3][2]);
					cozummatrisi[3]--;
				}
			}


		}

		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		// c ve d yollarýnýn kontrolü---------------------------------------------------------------------

		if (kontrol2[2] == 't' && kontrol3[2] == 'z' && kontrol2[3] == 'z' && kontrol3[3] == 'y')
		{

			if (girisler[0] == 'z' || girisler[1] == 'z')
			{

				cozummatrisi[3] = yollar[6] - yollar[7] + yollar[2];


				if (yollar[7] == -1)
				{
					yollarklon[3][7] = yollar[7];
					yollarklon[3][7] = (-yollarklon[3][7]);
					cozummatrisi[3]--;
				}
				if (yollar[6] == -1)
				{
					yollarklon[3][6] = yollar[6];
					yollarklon[3][6];
					cozummatrisi[3]++;
				}

				if (yollar[2] == -1)
				{
					yollarklon[3][2] = yollar[2];
					yollarklon[3][2];
					cozummatrisi[3]++;
				}

			}

			// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
			if (cikislar[0] == 'z' || cikislar[1] == 'z')
			{
				cozummatrisi[3] = -yollar[6] + yollar[7] + yollar[2];

				if (yollar[7] == -1)
				{
					yollarklon[3][7] = yollar[7];
					yollarklon[3][7];
					cozummatrisi[3]++;
				}
				if (yollar[6] == -1)
				{
					yollarklon[3][6] = yollar[6];
					yollarklon[3][6] = (-yollarklon[3][6]);
					cozummatrisi[3]--;
				}

				if (yollar[2] == -1)
				{
					yollarklon[3][2] = yollar[2];
					yollarklon[3][2];
					cozummatrisi[3]++;
				}
			}


		}


		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		// c ve d yollarýnýn kontrolü---------------------------------------------------------------------

		if (kontrol2[2] == 'z' && kontrol3[2] == 't' && kontrol2[3] == 'z' && kontrol3[3] == 'y')
		{

			if (girisler[0] == 'z' || girisler[1] == 'z')
			{

				cozummatrisi[3] = -yollar[6] - yollar[7] + yollar[2];


				if (yollar[7] == -1)
				{
					yollarklon[3][7] = yollar[7];
					yollarklon[3][7] = (-yollarklon[3][7]);
					cozummatrisi[3]--;
				}
				if (yollar[6] == -1)
				{
					yollarklon[3][6] = yollar[6];
					yollarklon[3][6] = (-yollarklon[3][6]);
					cozummatrisi[3]--;
				}

				if (yollar[2] == -1)
				{
					yollarklon[3][2] = yollar[2];
					yollarklon[3][2];
					cozummatrisi[3]++;
				}

			}


			if (cikislar[0] == 'z' || cikislar[1] == 'z')
			{
				//COZUMSUZ MATRÝS !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!***************************AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA
				cozummatrisi[3] = -yollar[6] - yollar[7] + yollar[2];

				if (yollar[7] == -1)
				{
					yollarklon[3][7] = yollar[7];
					yollarklon[3][7];
					cozummatrisi[3]--;
				}
				if (yollar[6] == -1)
				{
					yollarklon[3][6] = yollar[6];
					yollarklon[3][6];
					cozummatrisi[3]--;
				}

				if (yollar[2] == -1)
				{
					yollarklon[3][2] = yollar[2];
					yollarklon[3][2] = (-yollarklon[3][2]);
					cozummatrisi[3]++;
				}
			}


		}


		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		// c ve d yollarýnýn kontrolü---------------------------------------------------------------------

		if (kontrol2[2] == 'z' && kontrol3[2] == 't' && kontrol2[3] == 'y' && kontrol3[3] == 'z')
		{

			if (girisler[0] == 'z' || girisler[1] == 'z')
			{

				cozummatrisi[3] = -yollar[6] + yollar[7] + yollar[2];


				if (yollar[7] == -1)
				{
					yollarklon[3][7] = yollar[7];
					yollarklon[3][7];
					cozummatrisi[3]++;
				}
				if (yollar[6] == -1)
				{
					yollarklon[3][6] = yollar[6];
					yollarklon[3][6] = (-yollarklon[3][6]);
					cozummatrisi[3]--;
				}

				if (yollar[2] == -1)
				{
					yollarklon[3][2] = yollar[2];
					yollarklon[3][2];
					cozummatrisi[3]++;
				}

			}

			// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
			//-------------------------------------------------------------------------------------------
			if (cikislar[0] == 'z' || cikislar[1] == 'z')
			{
				cozummatrisi[3] = +yollar[6] - yollar[7] + yollar[2];

				if (yollar[7] == -1)
				{
					yollarklon[3][7] = yollar[7];
					yollarklon[3][7] = (-yollarklon[3][7]);
					cozummatrisi[3]--;
				}
				if (yollar[6] == -1)
				{
					yollarklon[3][6] = yollar[6];
					yollarklon[3][6];
					cozummatrisi[3]++;
				}

				if (yollar[2] == -1)
				{
					yollarklon[3][2] = yollar[2];
					yollarklon[3][2];
					cozummatrisi[3]++;
				}
			}
			yollarklon[3][9] = cozummatrisi[3];


		}

		yollarklon[3][9] = cozummatrisi[3];
		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		// c ve a yollarýnýn kontrolü---------------------------------------------------------------------

		if (kontrol2[2] == 'z' && kontrol3[2] == 't' && kontrol2[0] == 'x' && kontrol3[0] == 't' && kontrol2[4] == 't' && kontrol3[4] == 'y')
		{


			if (girisler[0] == 't' || girisler[1] == 't')
			{

				cozummatrisi[4] = -yollar[6] - yollar[4] - yollar[3] + yollar[8];


				if (yollar[4] == -1)
				{
					yollarklon[4][4] = yollar[4];
					yollarklon[4][4];
					cozummatrisi[4]--;
				}
				if (yollar[6] == -1)
				{
					yollarklon[4][6] = yollar[6];
					yollarklon[4][6];
					cozummatrisi[4]--;
				}

				if (yollar[3] == -1)
				{
					yollarklon[4][3] = yollar[3];
					yollarklon[4][3];
					cozummatrisi[4]--;
				}
				if (yollar[8] == -1)
				{
					yollarklon[4][8] = yollar[8];
					yollarklon[4][8];
					cozummatrisi[4]++;
				}
			}


			if (cikislar[0] == 't' || cikislar[1] == 't')
			{
				cozummatrisi[4] = +yollar[6] + yollar[4] - yollar[3] - yollar[8];

				if (yollar[4] == -1)
				{
					yollarklon[4][4] = yollar[4];
					yollarklon[4][4];
					cozummatrisi[4]++;
				}
				if (yollar[6] == -1)
				{
					yollarklon[4][6] = yollar[6];
					yollarklon[4][6];
					cozummatrisi[4]++;
				}

				if (yollar[3] == -1)
				{
					yollarklon[4][3] = yollar[3];
					yollarklon[4][3] = (-yollarklon[4][3]);
					cozummatrisi[4]--;
				}
				if (yollar[8] == -1)
				{
					yollarklon[4][8] = yollar[8];
					yollarklon[4][8] = (-yollarklon[4][8]);
					cozummatrisi[4]--;
				}
			}


		}
		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		// c ve a yollarýnýn kontrolü---------------------------------------------------------------------

		if (kontrol2[2] == 'z' && kontrol3[2] == 't' && kontrol2[0] == 'x' && kontrol3[0] == 't' && kontrol2[4] == 'y' && kontrol3[4] == 't')
		{


			if (girisler[0] == 't' || girisler[1] == 't')
			{

				//MATRÝS ÇÖZÜMSÜZDÜR********************************************************************* GOTO KULLAN


				cozummatrisi[4] = -yollar[6] - yollar[4] - yollar[3] + yollar[8];


				if (yollar[4] == -1)
				{
					yollarklon[4][4] = yollar[4];
					yollarklon[4][4];
					cozummatrisi[4]--;
				}
				if (yollar[6] == -1)
				{
					yollarklon[4][6] = yollar[6];
					yollarklon[4][6];
					cozummatrisi[4]--;
				}

				if (yollar[3] == -1)
				{
					yollarklon[4][3] = yollar[3];
					yollarklon[4][3];
					cozummatrisi[4]--;
				}
				if (yollar[8] == -1)
				{
					yollarklon[4][8] = yollar[8];
					yollarklon[4][8] = (-yollarklon[4][8]);
					cozummatrisi[4]++;
				}
			}


			if (cikislar[0] == 't' || cikislar[1] == 't')
			{
				cozummatrisi[4] = +yollar[6] + yollar[4] - yollar[3] + yollar[8];

				if (yollar[4] == -1)
				{
					yollarklon[4][4] = yollar[4];
					yollarklon[4][4];
					cozummatrisi[4]++;
				}
				if (yollar[6] == -1)
				{
					yollarklon[4][6] = yollar[6];
					yollarklon[4][6];
					cozummatrisi[4]++;
				}

				if (yollar[3] == -1)
				{
					yollarklon[4][3] = yollar[3];
					yollarklon[4][3] = (-yollarklon[4][3]);
					cozummatrisi[4]--;
				}
				if (yollar[8] == -1)
				{
					yollarklon[4][8] = yollar[8];
					yollarklon[4][8];
					cozummatrisi[4]++;
				}
			}


		}

		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		// c ve a yollarýnýn kontrolü---------------------------------------------------------------------

		if (kontrol2[2] == 't' && kontrol3[2] == 'z' && kontrol2[0] == 'x' && kontrol3[0] == 't' && kontrol2[4] == 't' && kontrol3[4] == 'y')
		{


			if (girisler[0] == 't' || girisler[1] == 't')
			{

				cozummatrisi[4] = +yollar[6] - yollar[4] - yollar[3] + yollar[8];


				if (yollar[4] == -1)
				{
					yollarklon[4][4] = yollar[4];
					yollarklon[4][4] = (-yollarklon[4][4]);
					cozummatrisi[4]--;
				}
				if (yollar[6] == -1)
				{
					yollarklon[4][6] = yollar[6];
					yollarklon[4][6];
					cozummatrisi[4]++;
				}

				if (yollar[3] == -1)
				{
					yollarklon[4][3] = yollar[3];
					yollarklon[4][3] = (-yollarklon[4][3]);
					cozummatrisi[4]--;
				}
				if (yollar[8] == -1)
				{
					yollarklon[4][8] = yollar[8];
					yollarklon[4][8];
					cozummatrisi[4]++;
				}

			}


			if (cikislar[0] == 't' || cikislar[1] == 't')
			{
				cozummatrisi[4] = -yollar[6] + yollar[4] - yollar[3] - yollar[8];

				if (yollar[4] == -1)
				{
					yollarklon[4][4] = yollar[4];
					yollarklon[4][4];
					cozummatrisi[4]++;
				}
				if (yollar[6] == -1)
				{
					yollarklon[4][6] = yollar[6];
					yollarklon[4][6] = (-yollarklon[4][6]);
					cozummatrisi[4]--;
				}

				if (yollar[3] == -1)
				{
					yollarklon[4][3] = yollar[3];
					yollarklon[4][3] = (-yollarklon[4][3]);
					cozummatrisi[4]--;
				}
				if (yollar[8] == -1)
				{
					yollarklon[4][8] = yollar[8];
					yollarklon[4][8] = (-yollarklon[4][8]);
					cozummatrisi[4]--;
				}

			}


		}

		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		// c ve a yollarýnýn kontrolü---------------------------------------------------------------------

		if (kontrol2[2] == 't' && kontrol3[2] == 'z' && kontrol2[0] == 'x' && kontrol3[0] == 't' && kontrol2[4] == 'y' && kontrol3[4] == 't')
		{


			if (girisler[0] == 't' || girisler[1] == 't')
			{

				cozummatrisi[4] = +yollar[6] - yollar[4] - yollar[3] - yollar[8];


				if (yollar[4] == -1)
				{
					yollarklon[4][4] = yollar[4];
					yollarklon[4][4] = (-yollarklon[4][4]);
					cozummatrisi[4]--;
				}
				if (yollar[6] == -1)
				{
					yollarklon[4][6] = yollar[6];
					yollarklon[4][6];
					cozummatrisi[4]++;
				}

				if (yollar[3] == -1)
				{
					yollarklon[4][3] = yollar[3];
					yollarklon[4][3] = (-yollarklon[4][3]);
					cozummatrisi[4]--;
				}
				if (yollar[8] == -1)
				{
					yollarklon[4][8] = yollar[8];
					yollarklon[4][8] = (-yollarklon[4][8]);
					cozummatrisi[4]--;
				}

			}


			if (cikislar[0] == 't' || cikislar[1] == 't')
			{
				cozummatrisi[4] = -yollar[6] + yollar[4] - yollar[3] + yollar[8];

				if (yollar[4] == -1)
				{
					yollarklon[4][4] = yollar[4];
					yollarklon[4][4];
					cozummatrisi[4]++;
				}
				if (yollar[6] == -1)
				{
					yollarklon[4][6] = yollar[6];
					yollarklon[4][6] = (-yollarklon[4][6]);
					cozummatrisi[4]--;
				}

				if (yollar[3] == -1)
				{
					yollarklon[4][3] = yollar[3];
					yollarklon[4][3] = (-yollarklon[4][3]);
					cozummatrisi[4]--;
				}
				if (yollar[8] == -1)
				{
					yollarklon[4][8] = yollar[8];
					yollarklon[4][8];
					cozummatrisi[4]++;
				}

			}


		}

		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		// c ve a yollarýnýn kontrolü---------------------------------------------------------------------

		if (kontrol2[2] == 't' && kontrol3[2] == 'z' && kontrol2[0] == 't' && kontrol3[0] == 'x' && kontrol2[4] == 't' && kontrol3[4] == 'y')
		{

			if (girisler[0] == 't' || girisler[1] == 't')
			{

				cozummatrisi[4] = -yollar[6] - yollar[4] + yollar[3] - yollar[8];


				if (yollar[4] == -1)
				{
					yollarklon[4][4] = yollar[4];
					yollarklon[4][4] = (-yollarklon[4][4]);
					cozummatrisi[4]--;
				}
				if (yollar[6] == -1)
				{
					yollarklon[4][6] = yollar[6];
					yollarklon[4][6] = (-yollarklon[4][6]);
					cozummatrisi[4]--;
				}

				if (yollar[3] == -1)
				{
					yollarklon[4][3] = yollar[3];
					yollarklon[4][3];
					cozummatrisi[4]++;
				}
				if (yollar[8] == -1)
				{
					yollarklon[4][8] = yollar[8];
					yollarklon[4][8] = (-yollarklon[4][8]);
					cozummatrisi[4]--;
				}

			}


			if (cikislar[0] == 't' || cikislar[1] == 't')
			{
				//MATRÝS ÇÖZÜMSÜZDÜR-******************************************-------------*-*-*-*-*-*-*-*-*-*_AAAAAAAAAAAAAAAAAAAAAAAAAAAA
				//MATRÝS ÇÖZÜMSÜZDÜR-******************************************-------------*-*-*-*-*-*-*-*-*-*_AAAAAAAAAAAAAAAAAAAAAAAAAAAA
				//MATRÝS ÇÖZÜMSÜZDÜR-******************************************-------------*-*-*-*-*-*-*-*-*-*_AAAAAAAAAAAAAAAAAAAAAAAAAAAA
				cozummatrisi[4] = -yollar[6] - yollar[4] - yollar[3] - yollar[8];

				if (yollar[4] == -1)
				{
					yollarklon[4][4] = yollar[4];
					yollarklon[4][4];
					cozummatrisi[4]--;
				}
				if (yollar[6] == -1)
				{
					yollarklon[4][6] = yollar[6];
					yollarklon[4][6];
					cozummatrisi[4]--;
				}

				if (yollar[3] == -1)
				{
					yollarklon[4][3] = yollar[3];
					yollarklon[4][3] = (-yollarklon[4][3]);
					cozummatrisi[4]++;
				}
			}


		}


		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		// c ve a yollarýnýn kontrolü---------------------------------------------------------------------

		if (kontrol2[2] == 't' && kontrol3[2] == 'z' && kontrol2[0] == 't' && kontrol3[0] == 'x' && kontrol2[4] == 'y' && kontrol3[4] == 't')
		{

			if (girisler[0] == 't' || girisler[1] == 't')
			{

				cozummatrisi[4] = -yollar[6] - yollar[4] + yollar[3] + yollar[8];


				if (yollar[4] == -1)
				{
					yollarklon[4][4] = yollar[4];
					yollarklon[4][4] = (-yollarklon[4][4]);
					cozummatrisi[4]--;
				}
				if (yollar[6] == -1)
				{
					yollarklon[4][6] = yollar[6];
					yollarklon[4][6] = (-yollarklon[4][6]);
					cozummatrisi[4]--;
				}

				if (yollar[3] == -1)
				{
					yollarklon[4][3] = yollar[3];
					yollarklon[4][3];
					cozummatrisi[4]++;
				}
				if (yollar[8] == -1)
				{
					yollarklon[4][8] = yollar[8];
					yollarklon[4][8];
					cozummatrisi[4]++;
				}

			}


			if (cikislar[0] == 't' || cikislar[1] == 't')
			{

				cozummatrisi[4] = -yollar[6] - yollar[4] - yollar[3] + yollar[8];

				if (yollar[4] == -1)
				{
					yollarklon[4][4] = yollar[4];
					yollarklon[4][4] = (-yollarklon[4][4]);
					cozummatrisi[4]--;
				}
				if (yollar[6] == -1)
				{
					yollarklon[4][6] = yollar[6];
					yollarklon[4][6] = (-yollarklon[4][6]);
					cozummatrisi[4]--;
				}

				if (yollar[3] == -1)
				{
					yollarklon[4][3] = yollar[3];
					yollarklon[4][3] = (-yollarklon[4][3]);
					cozummatrisi[4]--;
				}
				if (yollar[8] == -1)
				{
					yollarklon[4][8] = yollar[8];
					yollarklon[4][8];
					cozummatrisi[4]++;
				}

			}


		}




		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		// c ve a yollarýnýn kontrolü---------------------------------------------------------------------

		if (kontrol2[2] == 'z' && kontrol3[2] == 't' && kontrol2[0] == 't' && kontrol3[0] == 'x' && kontrol2[4] == 't' && kontrol3[4] == 'y')
		{

			if (girisler[0] == 't' || girisler[1] == 't')
			{

				cozummatrisi[4] = -yollar[6] + yollar[4] - yollar[3] + yollar[8];


				if (yollar[4] == -1)
				{
					yollarklon[4][4] = yollar[4];
					yollarklon[4][4];
					cozummatrisi[4]++;
				}
				if (yollar[6] == -1)
				{
					yollarklon[4][6] = yollar[6];
					yollarklon[4][6] = (-yollarklon[4][6]);
					cozummatrisi[4]--;
				}

				if (yollar[3] == -1)
				{
					yollarklon[4][3] = yollar[3];
					yollarklon[4][3] = (-yollarklon[4][3]);
					cozummatrisi[4]--;
				}
				if (yollar[8] == -1)
				{
					yollarklon[4][8] = yollar[8];
					yollarklon[4][8];
					cozummatrisi[4]++;
				}
			}


			if (cikislar[0] == 't' || cikislar[1] == 't')
			{
				cozummatrisi[4] = yollar[6] - yollar[4] - yollar[3] - yollar[8];

				if (yollar[4] == -1)
				{
					yollarklon[4][4] = yollar[4];
					yollarklon[4][4] = (-yollarklon[4][4]);
					cozummatrisi[4]--;
				}
				if (yollar[6] == -1)
				{
					yollarklon[4][6] = yollar[6];
					yollarklon[4][6];
					cozummatrisi[4]++;
				}

				if (yollar[3] == -1)
				{
					yollarklon[4][3] = yollar[3];
					yollarklon[4][3] = (-yollarklon[4][3]);
					cozummatrisi[4]++;
				}
				if (yollar[8] == -1)
				{
					yollarklon[4][8] = yollar[8];
					yollarklon[4][8] = (-yollarklon[4][8]);
					cozummatrisi[4]--;
				}
			}



		}


		// yollar[0] = x, yollar[1] = y, yollar[2] = z, yollar[3] = t,  yollar[4] = a, yollar[5] = b, yollar[6] = c, yollar[7] = d
		//-------------------------------------------------------------------------------------------
		// c ve a yollarýnýn kontrolü---------------------------------------------------------------------

		if (kontrol2[2] == 'z' && kontrol3[2] == 't' && kontrol2[0] == 't' && kontrol3[0] == 'x' && kontrol2[4] == 'y' && kontrol3[4] == 't')
		{

			if (girisler[0] == 't' || girisler[1] == 't')
			{

				cozummatrisi[4] = -yollar[6] + yollar[4] - yollar[3] - yollar[8];


				if (yollar[4] == -1)
				{
					yollarklon[4][4] = yollar[4];
					yollarklon[4][4];
					cozummatrisi[4]++;
				}
				if (yollar[6] == -1)
				{
					yollarklon[4][6] = yollar[6];
					yollarklon[4][6] = (-yollarklon[4][6]);
					cozummatrisi[4]--;
				}

				if (yollar[3] == -1)
				{
					yollarklon[4][3] = yollar[3];
					yollarklon[4][3] = (-yollarklon[4][3]);
					cozummatrisi[4]--;
				}
				if (yollar[8] == -1)
				{
					yollarklon[4][8] = yollar[8];
					yollarklon[4][8] = (-yollarklon[4][8]);
					cozummatrisi[4]++;
				}
			}


			if (cikislar[0] == 't' || cikislar[1] == 't')
			{
				cozummatrisi[4] = yollar[6] - yollar[4] - yollar[3] + yollar[8];

				if (yollar[4] == -1)
				{
					yollarklon[4][4] = yollar[4];
					yollarklon[4][4] = (-yollarklon[4][4]);
					cozummatrisi[4]--;
				}
				if (yollar[6] == -1)
				{
					yollarklon[4][6] = yollar[6];
					yollarklon[4][6];
					cozummatrisi[4]++;
				}

				if (yollar[3] == -1)
				{
					yollarklon[4][3] = yollar[3];
					yollarklon[4][3] = (-yollarklon[4][3]);
					cozummatrisi[4]++;
				}
				if (yollar[8] == -1)
				{
					yollarklon[4][8] = yollar[8];
					yollarklon[4][8];
					cozummatrisi[4]++;
				}
			}



		}
		yollarklon[4][9] = cozummatrisi[4];






		int** matrisson = new int*[matrisboyut + 1];
		for (int i = 0; i <= matrisboyut + 1; i++)
		{
			matrisson[i] = new int[matrisboyut + 1];
		}
		for (int a = 0; a <= matrisboyut; a++)
		{
			for (int b = 0; b <= matrisboyut; b++)
			{
				matrisson[b][a] = 0;

			}

		}

		for (int k = 1; k <= 8; k++)
		{
			printf("x[%d] \t", k);
		}
		printf("\n");

		for (int p = 0; p <= matrisboyut; p++)
		{

			for (int k = 0; k <= 9; k++)
			{
				printf("%d \t", yollarklon[p][k]);

			}


			printf("\n \n");
		}

		int o = 0;
		int zt = 0;
		for (int g = 0; g <= 9; g++)
		{
			for (int tv = 0; tv <= matrisboyut; tv++)
			{


				if (yollarklon[tv][g] == 1 || yollarklon[tv][g] == -1)
				{
					matrisson[tv][o] = yollarklon[tv][g];
					/*matrisson[tv][o + 1] = yollarklon[tv][9];*/
					zt = 1;

				}



			}
			if (zt == 1)
			{
				o++;
				zt = 0;
			}

		}



		for (int tv = 0; tv <= matrisboyut; tv++)
		{


			matrisson[tv][o + 1] = yollarklon[tv][9];


		}





		//DENKLEM MATRÝSÝNÝ YAZDIRMAK





		printf("Denklem Matrisi : \n");
		for (int p = 0; p <= matrisboyut; p++)
		{

			for (int k = 0; k <= o + 1; k++)
			{
				printf("%d \t", matrisson[p][k]);
			}


			printf("\n \n");
		}


		printf("\n \n");
		printf("cozum matrisi : ");
		printf("\n \n");
		for (int i = 0; i <= matrisboyut; i++)
		{
			printf("%d", cozummatrisi[i]);
			printf("\n");
		}
		// GAUSS JORDAN YONTEMÝ************************************************************************************


		printf("\nGauss jordan uygulancak matris \n");
		for (int gj1 = 0; gj1 <= matrisboyut; gj1++)
		{

			for (int gj2 = 0; gj2 < o; gj2++)
			{

				printf("%d \t", matrisson[gj1][gj2]);


			}
			printf("\n \n");

		}
		int gj3 = 0; int gj4 = 0;
		int swapmatris[8][8];
		int swapcozum[8];

		for (int gj2 = 0; gj2 < o + 1; gj2++)
		{
			for (int gj1 = 1; gj1 <= matrisboyut; gj1++)
			{

				if (matrisson[gj1][gj2] == 1)
				{
					if (gj3 != gj1 || gj4 != gj2)
					{
						if (matrisson[gj3][gj4] == 1)
						{

							for (int i = 0; i <= matrisboyut; i++)
							{
								matrisson[gj1][i] -= matrisson[gj3][i];

							}
							cozummatrisi[gj1] -= cozummatrisi[gj3];
							printf("\n matrisson[%d][i]  -  matrisson[%d][i]\n  islemi yapildi", gj1, gj3);
							printf("\n\n");
							for (int gj1 = 0; gj1 <= matrisboyut; gj1++)
							{

								for (int gj2 = 0; gj2 < o; gj2++)
								{

									printf("%d \t", matrisson[gj1][gj2]);


								}
								printf("\n \n");

							}
							printf("\n");

						}
					}
					if (matrisson[gj3][gj4] == -1)
					{

						for (int i = 0; i <= matrisboyut; i++)
						{
							matrisson[gj1][i] += matrisson[gj3][i];


						}
						cozummatrisi[gj1] += cozummatrisi[gj3];
						printf("\n matrisson[%d][i]  +  matrisson[%d][i]\n  islemi yapildi", gj1, gj3);
						printf("\n\n");
						printf("\n\n");
						for (int gj1 = 0; gj1 <= matrisboyut; gj1++)
						{

							for (int gj2 = 0; gj2 < o; gj2++)
							{

								printf("%d \t", matrisson[gj1][gj2]);


							}
							printf("\n \n");

						}
						printf("\n");


					}


					if (matrisson[gj3][gj4] == 0)
					{

						for (int i = 0; i <= matrisboyut; i++)
						{
							swapmatris[gj3][i] = matrisson[gj1][i];
							matrisson[gj1][i] = matrisson[gj3][i];
							matrisson[gj3][i] = swapmatris[gj3][i];
						}
						swapcozum[gj3] = cozummatrisi[gj1];
						cozummatrisi[gj1] = cozummatrisi[gj3];
						cozummatrisi[gj3] = swapcozum[gj3];


						printf("\n \n");
						printf("\n matrisson[%d][i]  ile  matrisson[%d][i]\n  yer degistirildi", gj1, gj3);
						printf("\n\n");
						for (int gj1 = 0; gj1 <= matrisboyut; gj1++)
						{

							for (int gj2 = 0; gj2 < o; gj2++)
							{

								printf("%d \t", matrisson[gj1][gj2]);


							}
							printf("\n \n");

						}
						printf("\n");


					}

				}
				if (matrisson[gj1][gj2] == -1)
				{
					if (matrisson[gj3][gj4] == 1)
					{
						printf("\n ifin icine girdi\n");
						for (int i = 0; i <= matrisboyut; i++)
						{
							matrisson[gj1][i] += matrisson[gj3][i];


						}
						cozummatrisi[gj1] += cozummatrisi[gj3];
						printf("\n matrisson[%d][i]  +  matrisson[%d][i]\n  islemi yapildi", gj1, gj3);
						printf("\n\n");
						for (int gj1 = 0; gj1 <= matrisboyut; gj1++)
						{

							for (int gj2 = 0; gj2 < o; gj2++)
							{

								printf("%d \t", matrisson[gj1][gj2]);


							}
							printf("\n \n");

						}
						printf("\n");

					}
					if (matrisson[gj3][gj4] == -1)
					{
						if (gj3 != gj1 && gj4 != gj2)
						{
							for (int i = 0; i <= matrisboyut; i++)
							{
								matrisson[gj1][i] -= matrisson[gj3][i];


							}
							cozummatrisi[gj1] -= cozummatrisi[gj3];
							printf("\n matrisson[%d][i]  -  matrisson[%d][i]\n  islemi yapildi", gj1, gj3);
							printf("\n\n");
							for (int gj1 = 0; gj1 <= matrisboyut; gj1++)
							{

								for (int gj2 = 0; gj2 < o; gj2++)
								{

									printf("%d \t", matrisson[gj1][gj2]);


								}
								printf("\n \n");

							}
						}
					}



					if (matrisson[gj3][gj4] == 0)
					{

						for (int i = 0; i <= matrisboyut; i++)
						{
							swapmatris[gj3][i] = matrisson[gj1][i];
							matrisson[gj1][i] = matrisson[gj3][i];
							matrisson[gj3][i] = swapmatris[gj3][i];
						}
						swapcozum[gj3] = cozummatrisi[gj1];
						cozummatrisi[gj1] = cozummatrisi[gj3];
						cozummatrisi[gj3] = swapcozum[gj3];

						printf("\n \n");
						printf("\n matrisson[%d][i]  ile  matrisson[%d][i]\n  yer degistirildi", gj1, gj3);

					}
					printf("\n \n");
					for (int gj1 = 0; gj1 <= matrisboyut; gj1++)
					{

						for (int gj2 = 0; gj2 < o; gj2++)
						{

							printf("%d \t", matrisson[gj1][gj2]);


						}
						printf("\n \n");

					}

				}






			}
			gj3++; gj4++;
		}


		for (int gj1 = 0; gj1 <= matrisboyut; gj1++)
		{

			for (int gj2 = 0; gj2 < o; gj2++)
			{

				if (gj1 == gj2)
				{
					if (matrisson[gj1][gj2] == -1)
					{

						for (int i = 0; i < o; i++)
						{
							matrisson[gj1][i] = -matrisson[gj1][i];


						}
						cozummatrisi[gj1] = -cozummatrisi[gj1];
					}
				}


			}


		}

		for (int gj1 = 0; gj1 <= matrisboyut; gj1++)
		{

			for (int gj2 = 0; gj2 < o; gj2++)
			{

				printf("%d \t", matrisson[gj1][gj2]);


			}
			printf("\n \n");

		}

		for (int gj2 = 0; gj2 < o; gj2++)
		{

			printf(" %d \n", cozummatrisi[gj2]);


		}


		int gj5 = 0; int gj6 = 0;
		for (int gj1 = 0; gj1 <= matrisboyut; gj1++)
		{
			for (int gj2 = 1; gj2 < o + 1; gj2++)
			{

				if (gj1 != gj2)
				{


					if (matrisson[gj1][gj2] == -1)
					{

						for (int i = 0; i <= matrisboyut; i++)
						{
							matrisson[gj1][i] += matrisson[gj2][i];


						}
						cozummatrisi[gj1] += cozummatrisi[gj2];
					}

					if (matrisson[gj1][gj2] == +1)
					{

						for (int i = 0; i <= matrisboyut; i++)
						{
							matrisson[gj1][i] -= matrisson[gj2][i];


						}
						cozummatrisi[gj1] -= cozummatrisi[gj2];
					}
				}
			}

		}

		printf("\n\n Sonuc Matrisi : \n");

		for (int gj1 = 0; gj1 <= matrisboyut; gj1++)
		{

			for (int gj2 = 0; gj2 < o; gj2++)
			{

				printf("%d \t", matrisson[gj1][gj2]);


			}
			printf("%d", cozummatrisi[gj1]);
			printf("\n \n");

		}
		printf("\n eger matris eselon hale getirilemediyse matris cozumsuzdur.. \n");




		al_rest(900);







	}





	return 0;
}
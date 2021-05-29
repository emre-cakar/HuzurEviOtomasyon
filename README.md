# HUZUR EVİ OTOMASYON PROJESİ


![alt yazı][resim]

[resim]: https://lh3.googleusercontent.com/oVtezXHGugGg-AoaZ7kh2apQfVie_TLshMt1c04gkfMdHt5WsMCLB1n_WSWEf2pif1gLXFJcecQqtcglrTTDwqFWcThuEuXxB7tDrfbybBgh9c2EP0Bt3IUOedkCzhxcR6Ptps39jYFJaAuxvr95LbNLGzkwiQK4lJ84w6NM5Qbh7sF0pEk8mHqYqEsEJ9gOXGiQEf3jP9mZD_GpFQqeautGHIsyj221DUVRsjepWdMyQxcHlJAs7OTGgybveaNsxzl_393FS8NKSBcwY3s5vgCjoYGB6DGoORfb5pdOAzmKrEXWdowVL6UCB3Yc3hgl5hP5nNI0Wa7z2eAUxb5oiVDHAzdCKQ_LG2JyON07gMynDECAltGT0iIwxLEvqSbCerL0HqFfIWuU0BZ0rYxB7VsilzKlD0HBx4ctCK6LlczQfpVHA3q9hkEFK7y-7VNr2GQc6AKHpK_cv_FpZPdavIFSvVyW8YrlQzxYq363L10cwGy_hOGuhhoOgFvahFM1dIp7blqzLQg0DGMO3l4BRCzz_IaDSMIGeZTzd555hdfdxxePiU38zWclY_ce6s2R_gmRMACtjS89jNixlOA_7qANaaprIdztsFFeLcni0T4RRT_aAbjvp9Sf-BGXRVrFQT5gSbQ0HQH08Avcchw2_3OeehECGUQMp8Uv7xa8j8jOLSL5GRmNMU9a5ITRcQ3tzCcqdyf4FBUBElPAGPtqwlY=w1792-h937-no?authuser=0


Marmara Üniversitesi Teknoloji Fakültesi Bilgisayar Mühendisliği 2021 Bahar dönemi Bilgisayar Programlama 1 dersi projesidir. Ders içeriği olarak işlenen konuların uygulaması yapılmıştır. 

Projemiz 5 kısımdan oluşmaktadır. 

- İlgili kütüphanenin projeye dahil edilmesi
- Global değişkenlerin ve sabitlerin tanımlanması
- Fonksiyon bildirimlerin yapılması
- Enum ve Struct veri yapıların tanımlanması
- Struct veriyapıların oluşturulması
- Fonksiyonların yazılması
- Main (ana) fonksiyonun içeriğin oluşturulması

## Fonksiyonlar
Projemizde kullanılan kütüphaneler kod blokların içerisinde belirtilmiştir.
```
#include <stdio.h>
#include <string.h>
#include <locale.h>
#include <time.h>
#include <stdlib.h>
#include <windows.h>
```
## Global değişkenler ve sabitlerin bildirilmesi
Projede bildirilen gloabel değişkenler ve sabitler aşağıdaki gibidir:
```
int const SMBaslama=8, SMGenislik=28, YMSatir=8, YMSutun =40, YMGenislik=18, IcerikSatir=11, IcerikSutun=40; 
int const IcerikEtiket=20, IcerikGenislik=18, YUKSEKLIK=1;
short satir, kolon, karakter=219 , DMSecim=0, YMSecim=0, KBSecim=0, YAPSecim=0, SBSecim=0, ss, GirisKontrol=0;
char ListeSecim[3]="0";
unsigned char tus;
```

## Fonksiyonların Bildirilmesi
```
void DikeyMenuSecim();void YakinaAitBilgi(); void SaglikBilgi();void YatayMenu(short s, short byt);void SakinListele();
void YatayMenuSecim();void KYatayMenuSecim();void sifreEkrani();
```

## Enum ve Struct Yapıları
Boolen veri yapısını projemize dahil etmek için enum yapısı kullanılmıştır. F ve T ifadeleri ile durumun FALSE(0) yada TRUE(1) bildirimi yapılması sağlanmıştır.

Standart veri yapıların yetersiz kaldığı durumlarda kullanıcı tanımlı veri yapıları oluşturulmuştur. Menulerin içeriğini sakladığımız ( baslik, uzunluk , altbaslik vb...) bir veri yapı tanımlanmıştır. 

```
enum boolean{ F, T }durum=T;
struct Menu{
	char baslik[25]; 
	short uzunluk;   
	short AltBaslikAdet;
	char AltBaslik[5][18];
};
struct Icerik {
	char e[20]; //etiket
	char i[25]; // icerik
};
typedef struct{
	char tc[25],adi[25],soyadi[25],dogum[25],yakin[25],yadi[25],ysoyadi[25],ytel[25],tani[25],ilac[25],klnsekli[25],klnskl[25];
}Kisi;
typedef struct {
```


Veri yapısı tanımlandıktan sonra projemizde bu veri yapıları kullanılarak ilgili başlıklar oluşturulmuştur. 
```
struct Menu SolMenuBasliklari [8]={
		{"K A Y I T",9,4,{"Kisisel Bilgi","Yakina Ait Bilgi","Saglik Bilgi","KAPAT"}},
		{"S A K I N L E R",15,2,{"Listele","KAPAT"}},
		{"A R I Z A  & T A L E P",22,3,{"Ariza","Talep","KAPAT"}},
		{"P E R S O N E L",15,2,{"Listele","KAPAT"}},
		{"D E P O",7,4,{"Urun Giris","Urun Cikis","Listele","KAPAT"}},
		{"G U N L U K",11,5,{"Kahvalti","Ogle","Aksam","Etkinlik","KAPAT"}},
		{"H A K K I M I Z D A",19,0,{0}},
		{"C I K I S",9,0,{0}}
	};
struct Icerik KisiselBilgiBaslik [4]={
	{"TC Numarasi","____________________"},
	{"Adi","____________________"},
	{"Soyadi","____________________"},
	{"Dogum Tarihi","____________________"},
};
struct Icerik YakinaAitBilgiBaslik [4]={
	{"Yakinligi","____________________"},
	{"Adi","____________________"},
	{"Soyadi","____________________"},
	{"Telefon","____________________"},
};
struct Icerik SaglikBilgiBaslik [4]={
	{"Tani","____________________"},
	{"Ilac Adi","____________________"},
	{"Kullanim Sekli","____________________"},
	{"Kullanim Sikligi","____________________"},
};
struct Menu SakinSolMenuBasliklari [10]={
```


## Fonksiyonlar ve Açıklamaları
Proje içerisinde kullanılan fonksiyonlar şu şekildedir:
```
void TamEkran(){}
void ImlecGizle(){}
void ImlecGoster(){}
void git(int s,int k){}
void Isaretle(short x, short y, short u, short d){}
void IcerikYazIsaretle(short x, short y, short u, short d, char icerik[25]){}
void DikeyMenu(struct Menu M[], short byt, short x, short w){}
void YatayMenu(short s, short byt){}
void EkranTaslak(){	}
void TarihSaatBilgisi(){}
void Temizle(){}
void IcerikTemizle(){}
void VarsayilanDegerler(){}
void Buton(short x, short y, char b[]){git(x,y); printf("%s",b);}
void KisiselBilgiGiris(){}
void YakinaAitBilgiGiris(){}
void SaglikBilgiGiris(){}
void DosyayaYaz(char dsyAdi[15], Kisi k){}
void DosyaOku(char dsyAdi[15], short x, short y, int g[]){}
void Kaydet(){}
void EkleIleri2(){}
void EkleIleri(){}
void YakinaAitBilgi(){}
void SaglikBilgi(){}
void KisiselBilgi(){}
void TabloOlustur(short x, short y, short secim,short detay, short sil,short kapat ){}
void SakinDetayGetir(int x){}
void SakinSil(int x){}
void SakinListele(){}
void ArizaListele(char dosyaadi[]){}
void hakkimizda(x,y,w,h){}
void Kontrol(){}
void YatayMenuSecim(){}
void DikeyMenuSecim(){}
void KYatayMenu(short s, short byt){}
void KDikeyMenuSecim(){}
void KYatayMenuSecim(){}
void isimyaz(){}
void sifreEkrani(){}
```

### TamEkran Fonksiyonu
Konsol ekranını tam ekran yapar.

### ImlecGizle ve ImlecGoster Fonksiyonu
Konsol ekranında imlecin yanıp sönmesini gösterilmesini veya gizleme işlemini yapar.

### git Fonksiyonu
s ve k adlı iki parametre alır. Bu parametreler ile konsol üzerinde ilgil konuma gidilmesini sağlar. s satir bilgisini saklarken k bilgisi sütun bilgisini saklar.

### Isaretle Fonksiyonu
Dört parametre alır. x, y , u ve d parametleri ile ilgili kullanıcıdan şu bilgileri toplar.
x : İlgili işaretlemenin yapılacağı satır bilgisi
y : İlgili işaretlemenin yapılacağı sütun bilgisi
u : İlgili işaretlemenin yapılacağı uzunluk bilgisi
d : İşaretlemin yapılıp yapılmayacağı bilgisi

Bu fonksiyon ile ilgili metnin etrafına dikdörtgen çizimi yapılması sağlanır. 

### IcerikYazIsaretle Fonksiyonu
İşaretle fonksiyonun benzeridir. İşaretle fonksiyonun parametrelerine ek olarak içerik bilgisini de alır. Bu şekilde direk işaretle yanında ilgili yazının yazılmasını sağlar.

### DikeyMenu Fonksiyonu
İlgili ekranın sol düşey menünun oluşturulduğu bölümdür. 4 parametre alır. 
M : Menü struct bilgisini alır. Menü başlıklarını içerir.
byt : Menü sayısının belirtildiği kısımdır.
x : Menünün yazılmaya başlanacağı satır bilgisini alır. 
w : Menü başlıkların yazılacağı genişlik alanın bilgisini alır bu bilgiye göre yazının ortalanmasını sağlar

### KYatayMenu ve YatayMenu Fonksiyonu 
Düşey menüden seçilmesi ile gelecek yatay menüyü oluşturur. 2 parametre alır.
s : Seçim yapıldığı düşey menü bilgisini alır
byt : Seçimin yapıldığı düşey menünün kaç alt başlık içerdiği bilgisini alır.

### EkranTaslak Fonksiyonu
Ekran taslağının oluşturulduğu bölümdür.

### TarihSaatBilgisi Fonksiyonu
Ekran taslağında tarih ve saat bilgisinin yazıldığı fonksiyondur.

### Temizle Fonksiyonu 
Düşey menü seçiminden sonra oluşturulan içeriği temizler.

### IcerikTemizle Fonksiyonu
Yatay menü seçiminden sonra oluşturulan içeriği temizler

### VarsayilanDegerler() Fonsksiyonu
Sakin kayıt sırasında oluşturulan içerik verilerin varsayılan değer almasını sağlar.

### Buton Fonksiyonu
Buton oluşturulmasını sağlayan fonksiyondur. 

### KisiselBilgiGiris, YakinaAitBilgiGiris ve SaglikBilgiGiris  Fonksiyonları
Sakin alt başlık giriş bilgilerin oluşturulduğu fonksiyonlardır.

### DosyayaYaz ve DosyaOku Fonksiyonu
Verilerin ilgili dosyalara yazılması ve ilgili dosyadan verilerin okunmasını sağlayan fonksiyonlardır.

### Kaydet Fonksiyonu 
Girilen verilerin struct yapılarına kayıt edildiği kısımdır. 

### EkleIleri ve EkleIleri2 Fonksiyonları 
Ekle ve ileri butonların seçiminin yapıldığı bölümdür. 

### KisiselBilgi, SaglikBilgi ve YakinaAitBilgi Fonksiyonları
Sakin kayıtların yapılması için ilgili alt menü başlık içeriklerin oluşturulduğu ve verilerin alındığı bölümdür. 

### TabloOlustur
Tablo oluşturulmasını sağlar. 

### SakinDetayGetir, SakinSil ve SakinListele Fonksiyonları 
Sakin bilgilerin listelendiği, silindiği ve detay bilgilerin getirildiği bölümdür.

### ArizaListele Fonksiyonları 
Arıza kayıtların listelenmesi sağlandığı fonksiyondur. 

### hakkimizda Fonksiyonu
Hakkımızda düşey menü içeriğin oluşturulduğu kısımdır. 4 parametre alır. 
x : İlgili içeriğin başlanılacağı satır bilgisini alır
y : İlgili içeriğin başlanılacağı sütun bilgisini alır
w : İlgili içeriğin yazılacağı genişlik bilgisini alır
h : İlgli içeriğin yazılacağı yükseklik bilgisini alır

### Kontrol Fonksiyonu 
Yatay ve düşey menü seçimlerin sonucunda çalıştırılacak fonksiyonların içerdiği fonksiyondur. 

###  KYatayMenuSecim ve YatayMenuSecim Fonksiyonu
Yatay menünün oluşturulduğu ve ilgili başlıkların arasında gezinmenin sağlandığı bölümdür.

### KDikeyMenuSecim ve DikeyMenuSecim
Düşey menünün oluşturulduğu ve ilgili başlıkların arasında gezinmenin sağlandığı bölümdür.

### isimyaz Fonksiyonu
Sakin giriş ekranında giriş yapanın bilgisin yazıldığı bölümdür.

### sifreEkrani Fonskiyonu
Programın çalıştırılması ile giriş ekranın oluşturulduğu ve giriş kontrolün sağlandığı kısımdır. 










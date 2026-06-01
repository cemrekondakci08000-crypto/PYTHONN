1.GİRİŞ 
Bu projede Python programlama dili kullanılarak basit bir müşteri yönetim sistemi geliştirilmiştir. 
Sistem içerisinde müşterilerin aylık ücretleri, sadakat süreleri ve kullandıkları hizmetler analiz 
edilmiştir. 
Projede liste, sözlük, döngü, fonksiyon ve koşullu ifadeler gibi temel programlama yapıları 
kullanılmıştır. Ayrıca random kütüphanesi ile müşteri ID oluşturulmuş, string işlemleri ile veriler 
standart hale getirilmiştir ve datetime ile tarih bilgisi eklenmiştir. 
Sistem içerisinde müşterilerin VIP olup olmadığı belirlenmiş ve belirli kriterlere göre churn (müşteri 
kaybı) riski analiz edilmiştir. Bu sayede gerçek hayattaki müşteri analiz sistemlerine benzer bir yapı 
oluşturulmuştur. 
<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/0bfcd2c5-686f-4f04-891d-445f1190174e" />


 
Kod: 

aktif=input("müşteri aktif mi(e/h):") 

if aktif.lower()=="e": 

aktif_mi=True 

else: 

aktif_mi=False 

Açıklama:kullanıcıdan müşteri bilgisi alınır aktif ise “e” pasif ise “h” olucak şekilde.daha sonra if 
döngüsü kurulur lower ile alınan bilgi küçük harfe çevrilir ve “e”harfine eşit ise true değil ise false 
olarak belirtilir. Boolean yapısının kullanılmasının amacı, müşterinin durumunu daha hızlı ve anlaşılır 
şekilde kontrol edebilmektir. 

Kod: 

hizmetler=[] 

for i in range(5): 

hizmet=input(f"{i+1}.hizmeti giriniz:") 

hizmetler.append(hizmet) 

Açıklama:Hizmetler adın da boş bir liste oluştururuz,kullanıcının girdigi hizmetler bu listede 
tutulur.bir for döngüsü kurarız bu sayede kaç hizmet girileceğini belirtiriz.burda range(5)olduğu için 
toplam 5 hizmet girileceği bellidir ve daha sonra kullanıcı hızmetleri girer ve append ile bu listeye 
ekleriz. 

Kullanılan kod: 
hizmet = input(f"{i+1}. hizmeti giriniz:") 

Bu kod satırında kullanıcıdan her döngüde bir hizmet adı girmesi istenmektedir. 
Burada kullanılan: 
input() fonksiyonu kullanıcıdan veri almak için, 

f-string yapısı ise ekrana dinamik mesaj yazdırmak için kullanılmıştır.

i+1 ifadesi hizmetlerin sıra numarasını göstermek amacıyla kullanılmıştır. 

Örneğin ekranda şu şekilde görünmektedir: 
1. hizmeti giriniz: 
2. hizmeti giriniz: 
3. hizmeti giriniz:

Bu yapı sayesinde kullanıcıdan birden fazla hizmet bilgisi düzenli şekilde alınabilmektedir. 
Projede müşteri bilgilerini saklamak için Python dictionary veri yapısı kullanılmıştır. Dictionary yapısı 
sayesinde müşteriye ait bilgiler anahtar-değer mantığıyla düzenli şekilde tutulmuştur.

Her müşteri için: 

• ad soyad  
• aylık ücret  
• sadakat süresi  
• aktiflik durumu  
• kullanılan hizmetler  
tek bir yapı içerisinde saklanmıştır. 

Kullanılan örnek kod aşağıdaki gibidir: 
musteri={#sözlük oluşturma 
"ad_soyad":ad_soyad, 
"ayliK_ucret":aylik_ucret, 
"sadakat_ayi":sadakat_ayi, 
"aktif_mi":aktif_mi, 
"hizmetler":hizmetler 
} 

Bu yapıda: 
• "ad_soyad" müşterinin ad bilgisini,  
• "aylik_ucret" müşterinin ödediği ücreti,  
• "sadakat_ayi" müşterinin şirkette kalma süresini,  
• "aktif_mi" müşterinin aktif olup olmadığını,  
• "hizmetler" ise kullandığı hizmetleri temsil etmektedir. 
Dictionary kullanılmasının nedeni verilere isimleriyle kolay erişim sağlamasıdır. Eğer liste kullanılmış 
olsaydı verilere sadece sıra numarasıyla erişilecekti ve bu durum kodun okunabilirliğini azaltacaktı. Bu 
nedenle dictionary kullanımı daha düzenli ve anlaşılır bir yapı sağlamıştır. 
Projede müşterilerin VIP olup olmadığını belirlemek için if-else yapısı kullanılmıştır. 

Kullanılan kod: 
if aylik_ucret > 500 or sadakat_ayi > 24: 
print("VIP müşteri indirim tanımlandı") 
else: 
print("indirim tanımlanmadı") 

Bu yapıda müşterinin: 
Aylık ücretinin 500 TL’den fazla olmasıveya sadakat süresinin 24 aydan büyük olması durumları 
kontrol edilmektedir. 
Koşullardan en az biri doğru olduğunda müşteri VIP olarak değerlendirilmekte ve sisteme indirim 
tanımlanmaktadır. 

Kod içerisinde kullanılan or operatörü, iki koşuldan sadece birinin doğru olmasının yeterli olduğunu 
ifade etmektedir. 

Örneğin: 
• müşteri yüksek ödeme yapıyorsa,  
• veya uzun süredir şirkette bulunuyorsa  

VIP müşteri kabul edilmektedir. 
Eğer iki koşul da sağlanmazsa sistem müşteriyi standart müşteri olarak değerlendirmektedir. 

import random   
print("BÜYÜK İSİM", ad_soyad.upper())   
customerID = "IST-2026-" + str(random.randint(1000, 9999)) 

Bu kodda: 
random kütüphanesi, rastgele sayı üretmek için kullanılmıştır. Bu sayede her müşteriye benzersiz bir 
ID verilmesi sağlanmıştır.ayrica kullanıcı ismi upper ile büyük harflere çevrilmiştir. 

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/aa71b408-9d03-4d48-9be3-4ba12f4075a1" />

 <img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/30875729-a213-491a-a8cd-cf4e61902ad1" />

 <img width="1920" height="869" alt="image" src="https://github.com/user-attachments/assets/9051a2a8-e36c-4f5f-ad92-7db0916fd235" />

 
Kod: 
def tutar_hesapla(aylik_ucret): 
    return aylik_ucret * 1.20 
    
Açıklama: 
Bu fonksiyon müşterinin aylık ücretine %20 KDV ekleyerek toplam tutarı hesaplar. 
 
Kod: 

musteriler = [] 

while True:#break gelene kadar sürekli çalış 

    print("\n--- Yeni Müşteri ---") 
  
    #  Kullanıcıdan veri alma 
    ad_soyad = input("Ad Soyad: ") 
    aylik_ucret = float(input("Aylık ücret: ")) 
    sadakat_ayi = int(input("Sadakat ayı: ")) 
    aktif = input("Aktif mi? (E/H): ") 
    aktif_mi = True if aktif.lower() == "e" else False#kisa if kullanımı kullandık aktif olup olmadıgına baktık 
    #  Hizmetler 
    hizmetler = [] 
    for i in range(5): 
        hizmet = input(f"{i+1}. hizmet: ") 
        hizmetler.append(hizmet) 
    #  ID oluşturma 
    customerID = "IST-2026-" + str(random.randint(1000, 9999))#rastgele müşteri id oluşturuyo 
    #  VIP kontrol 
    if aylik_ucret > 500 or sadakat_ayi > 24: 
        durum = "VIP" 
    else: 
        durum = "Standart" 
 
    #  KDV'li ücret 
    toplam = tutar_hesapla(aylik_ucret) 
    toplam = math.ceil(toplam)  # yukarı yuvarla mesela 600.2 olursa 601 yazariz 
    #  Tarih 
    tarih = datetime.now().strftime("%d-%m-%Y")#datetime now şuanki tarih bilgisini alir str kısmı da istedigimiz formata çevirme gün at yil yaptık 
    #  Tekrarlı hizmetleri temizle 
    benzersiz_hizmetler = list(set(hizmetler))#girilen hizmetlerde iki tane ayni şey olursa tek bi kere alir onu 
    #  Müşteri sözlüğü 
    musteri = { 
        "id": customerID, 
        "ad_soyad": ad_soyad.upper(),#ismi büyük yazdirma 
        "aylik_ucret": aylik_ucret, 
        "kdvli_ucret": toplam, 
        "sadakat_ayi": sadakat_ayi, 
        "aktif_mi": aktif_mi, 
        "durum": durum, 
        "hizmetler": benzersiz_hizmetler, 
        "tarih": tarih 
    } 
    #Listeye ekle 
    musteriler.append(musteri) 
    print("Müşteri eklendi ") 
    #  Devam kontrol 
    devam = input("Başka müşteri ekle? (E/H): ")#devam edersek başa döner ve yeni müşteri eklersin 
    if devam.lower() == "h": 
        break 
 
 
Açıklama: Bu program, bir müşteri yönetim sistemi oluşturmak için geliştirilmiştir. Sistem, 
kullanıcıdan müşteri bilgilerini alarak bunları bir döngü içerisinde işler ve liste yapısında saklar. 
Her müşteri için ad-soyad, aylık ücret, sadakat süresi, aktiflik durumu ve kullandığı hizmetler gibi 
bilgiler alınmaktadır. Aktiflik durumu Boolean yapıya çevrilerek True/False şeklinde tutulmaktadır. 
Müşteriye özel benzersiz bir ID, random kütüphanesi kullanılarak oluşturulmaktadır. Müşterinin VIP 
olup olmadığı, aylık ücret ve sadakat süresine göre if-else yapısı ile belirlenmektedir. 
Ayrıca aylık ücret üzerine %20 KDV eklenerek toplam tutar hesaplanmakta ve math.ceil() ile yukarı 
yuvarlanmaktadır. Müşteri eklenme tarihi datetime kütüphanesi ile sisteme kaydedilmektedir. 
Hizmetler liste içerisinde saklanmakta ve set() kullanılarak tekrar eden değerler temizlenmektedir. 
Tüm bilgiler bir dictionary yapısında toplanarak ana müşteri listesine eklenmektedir. 
Bu yapı sayesinde birden fazla müşteriyi analiz edebilen basit bir veri yönetim sistemi 
oluşturulmuştur. 

Kod: 

for m in musteriler: 

print("ID:", m["id"])

print("Ad:", m["ad_soyad"]) 

print("Durum:", m["durum"]) 

print("KDV'li Ücret:", m["kdvli_ucret"]) 

print("Hizmetler:", m["hizmetler"]) 

print("Tarih:", m["tarih"]) 


Açıklama: 
Bu bölüm, sistemde kayıtlı tüm müşterilerin detaylı şekilde görüntülenmesini sağlamaktadır. 

Sonuç 
Bu projede Python kullanılarak basit bir müşteri yönetim sistemi yapılmıştır. Kullanıcıdan müşteri 
bilgileri alınmış, liste ve sözlük yapıları ile saklanmıştır. 
Projede döngüler, koşullu ifadeler ve fonksiyonlar kullanılmıştır. Ayrıca random ile müşteri ID 
oluşturulmuş, math ile hesaplamalar yapılmış ve datetime ile tarih eklenmiştir. 
Sistem sayesinde müşteriler VIP veya Standart olarak sınıflandırılmış ve bilgiler düzenli şekilde ekrana 
yazdırılmıştır. 
Sonuç olarak bu proje sayesinde Python’daki temel veri yapıları ve mantık yapıları daha iyi 
anlaşılmıştır. 

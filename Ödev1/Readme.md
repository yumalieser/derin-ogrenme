{\rtf1\ansi\ansicpg1254\cocoartf2867
\cocoatextscaling0\cocoaplatform0{\fonttbl\f0\fswiss\fcharset0 Helvetica-Bold;\f1\fswiss\fcharset0 Helvetica;}
{\colortbl;\red255\green255\blue255;\red0\green0\blue0;\red109\green109\blue109;}
{\*\expandedcolortbl;;\cssrgb\c0\c0\c0;\cssrgb\c50196\c50196\c50196;}
{\*\listtable{\list\listtemplateid1\listhybrid{\listlevel\levelnfc23\levelnfcn23\leveljc0\leveljcn0\levelfollow0\levelstartat0\levelspace360\levelindent0{\*\levelmarker \{disc\}}{\leveltext\leveltemplateid1\'01\uc0\u8226 ;}{\levelnumbers;}\fi-360\li720\lin720 }{\listname ;}\listid1}
{\list\listtemplateid2\listhybrid{\listlevel\levelnfc0\levelnfcn0\leveljc0\leveljcn0\levelfollow0\levelstartat1\levelspace360\levelindent0{\*\levelmarker \{decimal\}}{\leveltext\leveltemplateid101\'01\'00;}{\levelnumbers\'01;}\fi-360\li720\lin720 }{\listname ;}\listid2}
{\list\listtemplateid3\listhybrid{\listlevel\levelnfc23\levelnfcn23\leveljc0\leveljcn0\levelfollow0\levelstartat0\levelspace360\levelindent0{\*\levelmarker \{disc\}}{\leveltext\leveltemplateid201\'01\uc0\u8226 ;}{\levelnumbers;}\fi-360\li720\lin720 }{\listname ;}\listid3}
{\list\listtemplateid4\listhybrid{\listlevel\levelnfc0\levelnfcn0\leveljc0\leveljcn0\levelfollow0\levelstartat1\levelspace360\levelindent0{\*\levelmarker \{decimal\}}{\leveltext\leveltemplateid301\'01\'00;}{\levelnumbers\'01;}\fi-360\li720\lin720 }{\listname ;}\listid4}}
{\*\listoverridetable{\listoverride\listid1\listoverridecount0\ls1}{\listoverride\listid2\listoverridecount0\ls2}{\listoverride\listid3\listoverridecount0\ls3}{\listoverride\listid4\listoverridecount0\ls4}}
\paperw11900\paperh16840\margl1440\margr1440\vieww11520\viewh8400\viewkind0
\deftab720
\pard\pardeftab720\sa321\partightenfactor0

\f0\b\fs48 \cf0 \expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 \uc0\u55357 \u56764 \u65039  CIFAR-10 G\'f6r\'fcnt\'fc S\u305 n\u305 fland\u305 rma: K-NN ve Hiperparametre Optimizasyonu\
\pard\pardeftab720\sa240\partightenfactor0

\f1\b0\fs24 \cf0 Bu \'e7al\uc0\u305 \u351 ma, temel bir makine \'f6\u287 renmesi algoritmas\u305  olan 
\f0\b K-Nearest Neighbors (K-En Yak\uc0\u305 n Kom\u351 u)
\f1\b0  y\'f6ntemini kullanarak 
\f0\b CIFAR-10
\f1\b0  veri setindeki nesneleri s\uc0\u305 n\u305 fland\u305 rmay\u305  ama\'e7lar. Proje, veri \'f6n i\u351 lemeden hiperparametre optimizasyonuna kadar t\'fcm u\'e7tan uca s\'fcreci kapsar.\
\pard\pardeftab720\partightenfactor0
\cf3 \strokec3 \
\pard\pardeftab720\sa298\partightenfactor0

\f0\b\fs36 \cf0 \strokec2 \uc0\u55358 \u56784  1. Proje ve Veri Seti Hakk\u305 nda\
\pard\pardeftab720\sa240\partightenfactor0

\fs24 \cf0 CIFAR-10
\f1\b0 , bilgisayarl\uc0\u305  g\'f6r\'fc (computer vision) alan\u305 nda standart bir k\u305 yaslama veri setidir.\
\pard\tx220\tx720\pardeftab720\li720\fi-720\sa240\partightenfactor0
\ls1\ilvl0
\f0\b \cf0 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 \uc0\u304 \'e7erik:
\f1\b0  10 farkl\uc0\u305  s\u305 n\u305 f (u\'e7ak, otomobil, ku\u351 , kedi, geyik, k\'f6pek, kurba\u287 a, at, gemi, kamyon).\
\ls1\ilvl0
\f0\b \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Boyut:
\f1\b0  $32 \\times 32$ piksellik, 3 kanall\uc0\u305  (RGB) renkli g\'f6r\'fcnt\'fcler.\
\ls1\ilvl0
\f0\b \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Zorluk:
\f1\b0  D\'fc\uc0\u351 \'fck \'e7\'f6z\'fcn\'fcrl\'fck ve nesnelerin g\'f6r\'fcnt\'fc i\'e7indeki farkl\u305  konumlar\u305 , K-NN gibi piksel tabanl\u305  modeller i\'e7in zorlay\u305 c\u305 d\u305 r.\
\pard\pardeftab720\partightenfactor0
\cf3 \strokec3 \
\pard\pardeftab720\sa298\partightenfactor0

\f0\b\fs36 \cf0 \strokec2 \uc0\u55358 \u56800  2. Algoritma: K-Nearest Neighbors (K-NN)\
\pard\pardeftab720\sa240\partightenfactor0

\f1\b0\fs24 \cf0 K-NN, "bana arkada\uc0\u351 \u305 n\u305  s\'f6yle, sana kim oldu\u287 unu s\'f6yleyeyim" mant\u305 \u287 \u305 yla \'e7al\u305 \u351 \u305 r. Bir g\'f6r\'fcnt\'fcn\'fcn s\u305 n\u305 f\u305 n\u305  belirlemek i\'e7in e\u287 itim setindeki en yak\u305 n $k$ adet kom\u351 usuna bakar.\
\pard\pardeftab720\sa298\partightenfactor0

\f0\b\fs36 \cf0 Mesafe Metri\uc0\u287 i (L1 vs L2)\
\pard\pardeftab720\sa240\partightenfactor0

\f1\b0\fs24 \cf0 G\'f6r\'fcnt\'fcler aras\uc0\u305 ndaki benzerli\u287 i \'f6l\'e7mek i\'e7in genellikle iki y\'f6ntem kullan\u305 l\u305 r:\
\pard\tx220\tx720\pardeftab720\li720\fi-720\sa240\partightenfactor0
\ls2\ilvl0
\f0\b \cf0 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	1	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 L1 (Manhattan) Mesafesi:
\f1\b0  Pikseller aras\uc0\u305  mutlak farklar\u305 n toplam\u305 .\u8232 $$d_1(I_1, I_2) = \\sum_\{p\} |I_1^p - I_2^p|$$\u8232 \
\ls2\ilvl0
\f0\b \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	2	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 L2 (Euclidean) Mesafesi:
\f1\b0  Pikseller aras\uc0\u305  farklar\u305 n karelerinin toplam\u305 n\u305 n karek\'f6k\'fc.\u8232 $$d_2(I_1, I_2) = \\sqrt\{\\sum_\{p\} (I_1^p - I_2^p)^2\}$$\u8232 \
\pard\pardeftab720\partightenfactor0
\cf3 \strokec3 \
\pard\pardeftab720\sa298\partightenfactor0

\f0\b\fs36 \cf0 \strokec2 \uc0\u55357 \u57056 \u65039  3. Uygulama Ad\u305 mlar\u305 \
A. Veri \'d6n \uc0\u304 \u351 leme (Preprocessing)\
\pard\pardeftab720\sa240\partightenfactor0

\f1\b0\fs24 \cf0 G\'f6r\'fcnt\'fcler 3 boyutlu matrisler ($32 \\times 32 \\times 3$) halindedir. K-NN'in \'e7al\uc0\u305 \u351 abilmesi i\'e7in her g\'f6r\'fcnt\'fcy\'fc 3072 elemanl\u305  bir vekt\'f6re d\'f6n\'fc\u351 t\'fcr\'fcyoruz (
\f0\b Flattening
\f1\b0 ). Ayr\uc0\u305 ca, mesafe hesaplamalar\u305 n\u305 n domine edilmemesi i\'e7in de\u287 erleri $[0, 1]$ aras\u305 na normalize ediyoruz.\
\pard\pardeftab720\sa298\partightenfactor0

\f0\b\fs36 \cf0 B. Hiperparametre Optimizasyonu (K-Fold Cross Validation)\
\pard\pardeftab720\sa240\partightenfactor0

\f1\b0\fs24 \cf0 Hangi $k$ de\uc0\u287 erinin en iyi sonucu verece\u287 ini deneme-yan\u305 lma (Cross-Validation) ile buluyoruz. Veriyi 5 par\'e7aya (fold) b\'f6lerek modelin genelleme yetene\u287 ini \'f6l\'e7\'fcyoruz.\
\pard\pardeftab720\partightenfactor0
\cf3 \strokec3 \
\pard\pardeftab720\sa298\partightenfactor0

\f0\b\fs36 \cf0 \strokec2 \uc0\u55357 \u56522  4. Deneysel Sonu\'e7lar ve Analiz\
\pard\pardeftab720\sa240\partightenfactor0

\f1\b0\fs24 \cf0 Yap\uc0\u305 lan testler sonucunda:\
\pard\tx220\tx720\pardeftab720\li720\fi-720\sa240\partightenfactor0
\ls3\ilvl0
\f0\b \cf0 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 En \uc0\u304 yi $k$ De\u287 eri:
\f1\b0  Genellikle 5 ile 10 aras\uc0\u305 nda bir de\u287 er en y\'fcksek sonucu verir.\
\ls3\ilvl0
\f0\b \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Do\uc0\u287 ruluk (Accuracy):
\f1\b0  %28 - %35 band\uc0\u305 nda bir ba\u351 ar\u305  elde edilir.\
\pard\pardeftab720\sa240\partightenfactor0

\f0\b \cf0 \uc0\u9888 \u65039  \'d6nemli Not:
\f1\b0  K-NN, piksellerin konumuna ve rengine \'e7ok duyarl\uc0\u305 d\u305 r. Bir nesnenin \u351 eklinden ziyade arka plan rengi benzerse K-NN hata yapabilir. Bu nedenle derin \'f6\u287 renme (CNN) modelleri bu veri setinde %90+ ba\u351 ar\u305 ya ula\u351 \u305 rken, K-NN daha k\u305 s\u305 tl\u305  kal\u305 r.\
\pard\pardeftab720\partightenfactor0
\cf3 \strokec3 \
\pard\pardeftab720\sa298\partightenfactor0

\f0\b\fs36 \cf0 \strokec2 \uc0\u55357 \u56960  5. Nas\u305 l \'c7al\u305 \u351 t\u305 r\u305 l\u305 r?\
\pard\tx220\tx720\pardeftab720\li720\fi-720\sa240\partightenfactor0
\ls4\ilvl0
\f1\b0\fs24 \cf0 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	1	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Kaggle'da internet eri\uc0\u351 imini a\'e7\u305 n (
\f0\b Settings > Internet On
\f1\b0 ).\
\ls4\ilvl0\kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	2	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 torchvision k\'fct\'fcphanesi ile veriyi otomatik indirin.\
}
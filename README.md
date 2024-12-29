# Wireshark-
Tarmoq trafigini tahlil qilish uchun eng mashhur vosita.

Umumiy ma'lumot
Wireshark Linux, macOS, *BSD va boshqa Unix va Unix-ga o'xshash operatsion tizimlar hamda Windows uchun tarmoq trafigi analizatori yoki "sniffer" hisoblanadi. U Qt, grafik foydalanuvchi interfeysi kutubxonasi va libpcap va npcap dan paketlarni yozib olish va filtrlash kutubxonalari sifatida foydalanadi.

Wireshark taqsimoti TShark bilan birga keladi, u chiziqqa yo'naltirilgan sniffer (Sun's snoop yoki tcpdump-ga o'xshash) bo'lib, Wireshark bilan bir xil dissektsiya, yozib olish faylini o'qish va yozish va paketlarni filtrlash kodidan foydalanadi va editcap bilan birga keladi. suratga olish fayllarini o'qish va ushbu yozib olish faylidan paketlarni yozish uchun dastur, ehtimol boshqa fayl formatida, va ba'zi paketlar, ehtimol, qo'lga olishdan olib tashlanishi mumkin.

Wiresharkning rasmiy uyi - https://www.wireshark.org .

Eng so'nggi tarqatishni https://www.wireshark.org/download pastki katalogida topish mumkin

O'rnatish
Wireshark loyihasi muntazam ravishda quyidagi platformalarda tuzadi va sinovdan o'tkazadi:

Linux (Ubuntu)
Microsoft Windows
macOS / {Mac} OS X
Rasmiy o'rnatish paketlari Microsoft Windows va macOS uchun mavjud.

U Debian, Ubuntu, Fedora, CentOS, RHEL, Arch, Gentoo, openSUSE, FreeBSD, DragonFly BSD, NetBSD va OpenBSD kabi koʻplab mashhur operatsion tizimlar va Linux distributivlari uchun standart yoki qoʻshimcha paket sifatida mavjud.

Bundan tashqari, u pkgsrc, OpenCSW, Homebrew va MacPorts kabi ko'plab uchinchi tomon qadoqlash tizimlari orqali mavjud.

U boshqa Unix-ish tizimlarida juda ko'p muammosiz ishlashi kerak.

Ba'zi hollarda Wiresharkning joriy versiyasi operatsion tizimingizni qo'llab-quvvatlamasligi mumkin. Bu Wireshark 1.10 va undan oldingi versiyalari tomonidan qo'llab-quvvatlanadigan Windows XP uchun. Boshqa hollarda Wireshark uchun standart paket eski bo'lishi mumkin. Bu Solaris va HP-UX uchun xuddi shunday.

Wiresharkni yaratish uchun Python 3 kerak. AsciiDoctor hujjatlarni, shu jumladan man sahifalarini yaratish uchun talab qilinadi. Ba'zi manba kodlarini yaratish uchun Perl va flex talab qilinadi.

Shuning uchun Python 3, AsciiDoctor va GNU "flex" (vanilla "lex" ishlamaydi) ni ular yetishmaydigan tizimlarga o'rnatishingiz kerak. Perl-ni ham o'rnatishingiz kerak bo'lishi mumkin.

Oʻrnatish boʻyicha toʻliq koʻrsatmalarni INSTALL faylida va https://www.wireshark.org/docs/wsdg_html_chunked/ saytidagi Dasturchi qoʻllanmasida topish mumkin.

Shuningdek, tegishli README ga qarang. OS uchun maxsus o'rnatish ko'rsatmalari uchun OS fayllari.

Foydalanish
Tarmoqdan paketlarni olish uchun siz dumpcap dasturini-UID-ni root-ga o'rnatishingiz kerak yoki tizimingiz juda moyil bo'lsa, tegishli yozuvga kirishingiz kerak /dev(BSD-dan olingan tizimlar va Solaris va tizimlar kabi tizimlar). DLPI-ni qo'llab-quvvatlaydigan HP-UX odatda ushbu toifaga kiradi). Wireshark va TShark bajariladigan fayllarni o'rnatuvchi ildiz qilish yoki ularni root sifatida ishga tushirish jozibador bo'lishi mumkin bo'lsa-da, iltimos qilmang. Qo'lga olish jarayoni dumpcap ichida izolyatsiya qilingan; bu oddiy dastur xavfsizlik teshiklarini o'z ichiga olishi ehtimoli kamroq va shuning uchun root sifatida ishlash xavfsizroq.

Har bir buyruq qatori opsiyasi va interfeys funksiyasining tavsifi uchun man sahifasiga murojaat qiling.

Bir nechta fayl turlari
Wireshark turli xil fayl turlaridan paketlarni o'qiy oladi. Qo'llab-quvvatlanadigan fayl formatlari ro'yxati uchun Wireshark foydalanuvchi sahifasiga yoki Wireshark foydalanuvchi qo'llanmasiga qarang.

Wireshark kompilyatsiya qilinganda kerakli siqish kutubxonasi mavjud bo'lsa, Wireshark ushbu fayllarning siqilgan versiyalarini shaffof o'qiy oladi. Hozirda qo'llab-quvvatlanadigan siqishni formatlari:

GZIP
LZ4
ZSTD
GZIP va LZ4 (mustaqil bloklardan foydalanilganda, bu sukut bo'yicha) tezkor tasodifiy qidiruvni qo'llab-quvvatlaydi, bu esa katta fayllarda grafik interfeysning ancha yaxshi ishlashini ta'minlaydi. Ushbu siqish formatlarining har qandayini kompilyatsiya vaqtida cmake ga mos variantni o'tkazish orqali o'chirib qo'yish mumkin, ya'ni, cmake -DENABLE_ZLIB=OFF, cmake -DENABLE_LZ4=OFF, yoki cmake -DENABLE_ZSTD=OFF.

Wireshark AIX iptrace fayllarini o'qiy olsa-da, AIX ning iptrace packet-trace buyrug'idagi hujjatlar juda kam. Buyruq iptraceizni to'xtatish uchun o'ldirishingiz kerak bo'lgan demonni ishga tushiradi. Tajriba natijasida ma'lum bo'lishicha, bu iptrace demoniga HUP signalini yuborish oqlangan o'chirishga olib keladi va iz fayliga to'liq paket yoziladi. Agar qisman paket oxirida saqlangan bo'lsa, Wireshark ushbu faylni o'qiyotganda shikoyat qiladi, lekin siz boshqa barcha paketlarni o'qiy olasiz. Agar shunday bo'lsa, Wireshark dasturchilariga wireshark-dev@wireshark.org manziliga xabar bering ; agar u kichik bo'lsa va sezgir bo'lmagan ma'lumotlarni o'z ichiga olgan bo'lsa, bizga ushbu iz faylining nusxasini yuborishni unutmang.

Lucent/Ascend mahsulotlarini qo'llab-quvvatlash MAX va Pipline seriyali mahsulotlar tomonidan ishlab chiqarilgan disk raskadrovka izi chiqishi bilan cheklangan. Wireshark wandsession, wandisplay, wannextva buyruqlar chiqishini o'qiy oladi wdd .

Wireshark shuningdek, ISDN routerlarining (TR-600 va TR-650) Toshiba "Compact Router" liniyasidan chiqindi izi chiqishini o'qiy oladi. Routerga telnet ulashingiz va bilan dump seansini boshlashingiz mumkin snoop dump.

CoSine L2 disk raskadrovka chiqishi Wireshark tomonidan ham o'qilishi mumkin. L2 disk raskadrovka chiqishini olish uchun avval diags rejimiga kiring va keyin qatlam-2 toifasi ostida create-pkt-log-profileva buyruqlaridan foydalaning. Ushbu buyruqlardan qanday foydalanish haqida batafsil ma'lumot olish uchun yoki apply-pkt-lozg-profileorqali yordam buyrug'ini ko'rib chiqishingiz kerak .layer-2 create ?layer-2 apply ?

Wireshark bilan Lucent/Ascend, Toshiba va CoSine izlaridan foydalanish uchun siz diskdagi faylga kuzatuv chiqishini yozib olishingiz kerak. Iz marshrutizator ichida sodir bo'lmoqda va marshrutizatorda izni siz uchun faylga saqlash imkoni yo'q. Unix ostida buni qilishning oson yo'li ishga tushirishdir telnet <ascend> | tee <outfile>. Yoki tizimingizda "skript" buyrug'i o'rnatilgan bo'lsa, siz qobiq seansini, shu jumladan telnetni faylga saqlashingiz mumkin. Masalan, tracefile.out nomli faylga kirish uchun:

$ script tracefile.out
Script started on <date/time>
$ telnet router
..... do your trace, then exit from the router's telnet session.
$ exit
Script done on <date/time>
Nom o'lchamlari
Wireshark IPv4 va IPv6 paketlarini dekodlashda teskari nomlarni aniqlash imkoniyatlaridan foydalanishga harakat qiladi.

Agar siz Wireshark-dan foydalanayotganda nom aniqligini oʻchirib qoʻymoqchi boʻlsangiz, Wireshark-ni -nbarcha nom aniqligini oʻchirish (jumladan MAC manzillari va TCP/UDP/SMTP port raqamlarini nomlarga oʻzgartirish) yoki -N mtnom aniqligini oʻchirish opsiyasi bilan Wireshark-ni ishga tushiring. tarmoq sathining barcha manzillari (IPv4, IPv6, IPX).

Tartibga solish menyusidagi Preferences bandidan foydalanib, Preferences dialog oynasini ochib, "Nom resolution" ni tanlab, tegishli nomlarni aniqlash parametrlarini o'chirib, "OK" tugmasini bosish orqali buni standart sozlamaga qo'yishingiz mumkin.

SNMP
Wireshark SNMP paketlarining asosiy dekodlanishini amalga oshirishi mumkin; MIB fayllarini o'qish va ushbu fayllardagi ma'lumotlardan OID va o'zgaruvchan bog'lanish qiymatlarini yanada qulayroq ko'rsatish uchun foydalanish orqali yanada murakkab dekodlashni amalga oshirish uchun libsmi kutubxonasidan foydalanishi mumkin. CMake sizning tizimingizda libsmi kutubxonasi mavjudligini avtomatik ravishda aniqlaydi. Agar sizda libsmi kutubxonasi bo'lsa, lekin Wireshark uni ishlatishini xohlamasangiz, cmake ni opsiya bilan ishga tushirishingiz mumkin-DENABLE_SMI=OFF .

Xato haqida qanday xabar berish kerak
Wireshark doimiy ravishda ishlab chiqilmoqda, shuning uchun uni ishlatishda xatolikka duch kelishingiz mumkin. Xatolar haqida https://gitlab.com/wireshark/wireshark/-/issues manzilida xabar bering . Xatoga kirganingizga ishonch hosil qiling:

Yordam menyusidagi "Wireshark haqida" bandidan to'liq tuzilish ma'lumotlari yoki Wireshark xatolari uchun chiqishi va TShark xatolari uchun wireshark -vchiqishi ;tshark -v

Agar xatolik Linuxda ro'y bergan bo'lsa, siz foydalanayotgan Linux distributivi va ushbu tarqatish versiyasi;

Wireshark-ni chaqirishda foydalangan buyruq, agar siz Wireshark-ni buyruq satridan ishga tushirgan bo'lsangiz yoki TShark-ni ishga tushirgan bo'lsangiz, TShark-ni ishga tushirgan bo'lsangiz va xatoning paydo bo'lishiga olib kelgan amallar ketma-ketligi.

Agar xato ma'lum bir kuzatuv fayli tomonidan yaratilgan bo'lsa, iltimos, xato tavsifi bilan birga kuzatuv faylini ilova qiling. Agar kuzatuv faylida maxfiy ma'lumotlar (masalan, parollar) bo'lsa, uni yubormang.

Agar Wireshark sizda "segmentatsiya buzilishi", "avtobus xatosi", "bekor qilish" yoki UNIX yadroli dump faylini keltirib chiqaradigan boshqa xatolik tufayli vafot etgan bo'lsa, sizda tuzatuvchi o'rnatilgan bo'lsa, ishlab chiquvchilarga katta yordam bera olasiz. Stack izini tuzatuvchi (bu misolda "gdb"), wireshark ikkilik fayli va natijada olingan yadro fayli yordamida olish mumkin. Buni amalga oshirish uchun gdb 'backtrace' buyrug'idan qanday foydalanishga misol keltiramiz.

$ gdb wireshark core
(gdb) backtrace
..... prints the stack trace
(gdb) quit
$
Yadro dump fayli ba'zi platformalarda (masalan, BSD tizimlari) "yadro" emas, balki "wireshark.core" deb nomlanishi mumkin. Agar sizda Wireshark o'rniga TShark bilan asosiy dump bo'lsa, tuzatuvchining birinchi argumenti sifatida "tshark" dan foydalaning; yadro chiqindisi "tshark.core" deb nomlanishi mumkin.

Litsenziya
Wireshark GNU GPLv2 ostida tarqatiladi. Litsenziyaning toʻliq matni uchun NUSXA OLISH fayliga qarang. Shubha tug'ilganda, to'liq matn yuridik jihatdan majburiy qism hisoblanadi. Ushbu eslatmalar GPLv2 bilan tanish bo'lmagan odamlar uchun qulaylik yaratish uchun qilingan.

Uni ishlatishda hech qanday cheklovlar yo'q. Uni manba yoki ikkilik shaklda tarqatishda cheklovlar mavjud.

Wiresharkning aksariyat qismlari "GPL 2 yoki undan keyingi versiya" litsenziyasi bilan qoplangan. Ba'zi fayllar GPLv2 bilan mos keladigan turli litsenziyalar bilan qoplangan.

E'tiborga molik istisno sifatida, Wireshark manbasi bilan tarqatiladigan ba'zi yordamchi dasturlar GPLv2 bilan bevosita mos kelmaydigan boshqa litsenziyalar bilan qoplangan. Bu yaxshi, chunki faqat asboblarning o'zi shu tarzda litsenziyalangan, asboblarning chiqishi olingan ish hisoblanmaydi va shuning uchun Wireshark'dan foydalanish uchun xavfsiz litsenziyalanishi mumkin. Ushbu vositalarning to'liq bo'lmagan tanlovi quyidagilarni o'z ichiga oladi:

pidl yordam dasturi (tools/pidl) GPLv3+ ostida litsenziyalangan.
Wireshark qismlarini qurish va kutubxona sifatida tarqatish mumkin. Ushbu qismlar hali ham GPL tomonidan qoplanadi, ammo Lesser General Public License yoki boshqa litsenziya bilan EMAS.

Agar siz Wireshark-ni butunlay yoki bir qismini o'z ilovangizga qo'shsangiz va uni nashr etish yoki chiqarishni tanlasangiz, birlashtirilgan ish GPLv2 shartlariga muvofiq chiqarilishi kerak.

Rad etish
Ushbu mahsulot bilan bog'liq aniq yoki nazarda tutilgan hech qanday kafolat yo'q. O'zingizning xavf-xataringiz ostida foydalaning.

powered by anonymooc 

# 👻 Ghost Təhlükəsizlik Modulu
**PowerShell əsaslı Windows və Azure Təhlükəsizlik Möhkəmləndirmə Aləti**

> **Windows son nöqtələri və Azure mühitləri üçün proaktiv təhlükəsizlik möhkəmləndirməsi.** Ghost lazımsız xidmətləri və protokolları söndürməklə ümumi hücum vektorlarının azaldılmasına kömək edə bilən PowerShell əsaslı möhkəmləndirmə funksiyalarını təmin edir.

## ⚠️ Mühüm İmtinalar

**TEST TƏLƏB OLUNUR**: Ghost-u həmişə ilk olaraq qeyri-istehsal mühitlərində sınaq edin. Xidmətlərin söndürülməsi qanuni biznes funksiyalarına təsir edə bilər.

**HEÇ BİR ZƏMANƏTİ YOXDUR**: Ghost ümumi hücum vektorlarını hədəf alsada, heç bir təhlükəsizlik aləti bütün hücumları qarşısını ala bilməz. Bu əhatəli təhlükəsizlik strategiyasının bir komponentidir.

**ƏMƏLİYYAT TƏSİRİ**: Bəzi funksiyalar sistem funksiyalarına təsir edə bilər. Yerləşdirmədən əvvəl hər tənzimləməni diqqətlə nəzərdən keçirin.

**PEŞƏKİK QİYMƏTLƏNDİRMƏ**: İstehsal mühitləri üçün tənzimləmələrin təşkilatınızın ehtiyaclarına uyğun olmasını təmin etmək üçün təhlükəsizlik mütəxəssisləri ilə məsləhətləşin.

## 📊 Təhlükəsizlik Mənzərəsi

Ransomware zərərləri **2025-ci ildə 57 milyard dollara** çatdı, tədqiqatlar göstərir ki, bir çox uğurlu hücumlar əsas Windows xidmətlərini və səhv konfiqurasiyaları istismar edir. Ümumi hücum vektorları aşağıdakıları daxil edir:

- **Ransomware hadisələrinin 90%-i** RDP istismarını əhatə edir
- **SMBv1 zəiflikləri** WannaCry və NotPetya kimi hücumları mümkün etdi
- **Sənəd makroları** malware çatdırılmasının əsas üsulu olaraq qalır
- **USB əsaslı hücumlar** havadan təcrid olunmuş şəbəkələri hədəf almağa davam edir
- **PowerShell sui-istifadəsi** son illərdə əhəmiyyətli dərəcədə artdı

## 🛡️ Ghost Təhlükəsizlik Funksiyaları

Ghost **16 Windows möhkəmləndirmə funksiyası** və **Azure təhlükəsizlik inteqrasiyası** təmin edir:

### Windows Son Nöqtə Möhkəmləndirməsi

| Funksiya | Məqsəd | Nəzərə Alınacaqlar |
|----------|---------|-------------------|
| `Set-RDP` | Uzaq masaüstü girişini idarə edir | Uzaq administrasiyaya təsir edə bilər |
| `Set-SMBv1` | Köhnə SMB protokolunu idarə edir | Çox köhnə sistemlər üçün tələb olunur |
| `Set-AutoRun` | AutoPlay/AutoRun-u idarə edir | İstifadəçi rahatlığına təsir edə bilər |
| `Set-USBStorage` | USB yaddaş cihazlarını məhdudlaşdırır | Qanuni USB istifadəsinə təsir edə bilər |
| `Set-Macros` | Office makro icrasını idarə edir | Makro aktivləşdirilmiş sənədlərə təsir edə bilər |
| `Set-PSRemoting` | PowerShell uzaq bağlantını idarə edir | Uzaq idarəçiliyə təsir edə bilər |
| `Set-WinRM` | Windows Uzaq İdarəçiliyi idarə edir | Uzaq administrasiyaya təsir edə bilər |
| `Set-LLMNR` | Ad həlli protokolunu idarə edir | Adətən söndürmək üçün təhlükəsizdir |
| `Set-NetBIOS` | TCP/IP üzərində NetBIOS-u idarə edir | Köhnə tətbiqlərə təsir edə bilər |
| `Set-AdminShares` | İnzibati paylaşımları idarə edir | Uzaq fayl girişinə təsir edə bilər |
| `Set-Telemetry` | Məlumat toplanmasını idarə edir | Diaqnostik qabiliyyətlərə təsir edə bilər |
| `Set-GuestAccount` | Qonaq hesabını idarə edir | Adətən söndürmək üçün təhlükəsizdir |
| `Set-ICMP` | Ping cavablarını idarə edir | Şəbəkə diaqnostikasına təsir edə bilər |
| `Set-RemoteAssistance` | Uzaq Yardımı idarə edir | Köməkçi masası əməliyyatlarına təsir edə bilər |
| `Set-NetworkDiscovery` | Şəbəkə kəşfiyyatını idarə edir | Şəbəkə baxışına təsir edə bilər |
| `Set-Firewall` | Windows Firewall-u idarə edir | Şəbəkə təhlükəsizliyi üçün kritikdir |

### Azure Cloud Təhlükəsizliyi

| Funksiya | Məqsəd | Tələblər |
|----------|---------|----------|
| `Set-AzureSecurityDefaults` | Əsas Azure AD təhlükəsizliyini aktivləşdirir | Microsoft Graph icazələri |
| `Set-AzureConditionalAccess` | Giriş siyasətlərini konfiqurasiya edir | Azure AD P1/P2 lisenziyası |
| `Set-AzurePrivilegedUsers` | İmtiyazlı hesabları audit edir | Global Admin icazələri |

### Müəssisə Yerləşdirmə Seçimləri

| Metod | İstifadə Halı | Tələblər |
|-------|---------------|----------|
| **Birbaşa İcra** | Test, kiçik mühitlər | Lokal admin hüquqları |
| **Group Policy** | Domain mühitləri | Domain admin, GP idarəçiliyi |
| **Microsoft Intune** | Cloud idarə olunan cihazlar | Intune lisenziyası, Graph API |

## 🚀 Sürətli Başlanğıc

### Təhlükəsizlik Qiymətləndirməsi
```powershell
# Ghost modulunu yüklə
Invoke-WebRequest 'https://raw.githubusercontent.com/jimrtyler/Ghost/main/Ghost.ps1' -OutFile .\Ghost.ps1
Get-Content .\Ghost.ps1
. .\Ghost.ps1

# Cari təhlükəsizlik vəziyyətini yoxla
Get-Ghost
```

### Əsas Möhkəmləndirmə (İlk Olaraq Test Et)
```powershell
# Vacib möhkəmləndirmə - ilk olaraq laboratoriya mühitində test et
Set-Ghost -SMBv1 -AutoRun -Macros

# Dəyişiklikləri nəzərdən keçir
Get-Ghost
```

### Müəssisə Yerləşdirməsi
```powershell
# Group Policy yerləşdirməsi (domain mühitləri)
Set-Ghost -SMBv1 -AutoRun -GroupPolicy

# Intune yerləşdirməsi (cloud idarə olunan cihazlar)
Set-Ghost -SMBv1 -RDP -USBStorage -Intune
```

## 📋 Quraşdırma Metodları

### Seçim 1: Birbaşa Yükləmə (Test)
```powershell
Invoke-WebRequest 'https://raw.githubusercontent.com/jimrtyler/Ghost/main/Ghost.ps1' -OutFile .\Ghost.ps1
Get-Content .\Ghost.ps1
. .\Ghost.ps1
```

### Seçim 2: Modul Quraşdırılması
```powershell
# PowerShell Gallery-dən quraşdır (mövcud olduqda)
Install-Module Ghost -Scope CurrentUser
Import-Module Ghost
```

### Seçim 3: Müəssisə Yerləşdirməsi
```powershell
# Group Policy yerləşdirməsi üçün şəbəkə yerləşdinə kopyala
# Cloud yerləşdirməsi üçün Intune PowerShell skriptlərini konfiqurasiya et
```

## 💼 İstifadə Halları Nümunələri

### Kiçik Biznes
```powershell
# Minimal təsirlə əsas qorunma
Set-Ghost -SMBv1 -AutoRun -Macros -ICMP
```

### Səhiyyə Mühiti
```powershell
# HIPAA-fokuslu möhkəmləndirmə
Set-Ghost -SMBv1 -RDP -USBStorage -AdminShares -Telemetry
```

### Maliyyə Xidmətləri
```powershell
# Yüksək təhlükəsizlik konfiqurasiyası
Set-Ghost -RDP -SMBv1 -AutoRun -USBStorage -Macros -PSRemoting -AdminShares
```

### Cloud-İlk Təşkilat
```powershell
# Intune idarə olunan yerləşdirmə
Connect-IntuneGhost -Interactive
Set-Ghost -SMBv1 -RDP -AutoRun -Macros -Intune
```

## 🔍 Funksiya Təfərrüatları

### Əsas Möhkəmləndirmə Funksiyaları

#### Şəbəkə Xidmətləri
- **RDP**: Uzaq masaüstü girişini bloklayır və ya portu təsadüfi edir
- **SMBv1**: Köhnə fayl paylaşımı protokolunu söndürür
- **ICMP**: Kəşfiyyat üçün ping cavablarını qarşısını alır
- **LLMNR/NetBIOS**: Köhnə ad həlli protokollarını bloklayır

#### Tətbiq Təhlükəsizliyi
- **Makrolar**: Office tətbiqlərində makro icrasını söndürür
- **AutoRun**: Çıxarıla bilən mediyadan avtomatik icranı qarşısını alır

#### Uzaq İdarəçilik
- **PSRemoting**: PowerShell uzaq sessiyalarını söndürür
- **WinRM**: Windows Uzaq İdarəçiliyi dayandırır
- **Uzaq Yardım**: Uzaq yardım bağlantılarını bloklayır

#### Giriş Nəzarəti
- **Admin Paylaşımları**: C$, ADMIN$ paylaşımlarını söndürür
- **Qonaq Hesabı**: Qonaq hesabı girişini söndürür
- **USB Yaddaş**: USB cihaz istifadəsini məhdudlaşdırır

### Azure İnteqrasiyası
```powershell
# Azure tenant-ə qoşul
Connect-AzureGhost -Interactive

# Təhlükəsizlik default-larını aktivləşdir
Set-AzureSecurityDefaults -Enable

# Şərti girişi konfiqurasiya et
Set-AzureConditionalAccess -BlockLegacyAuth -RequireMFA

# İmtiyazlı istifadəçiləri audit et
Set-AzurePrivilegedUsers -AuditOnly
```

### Intune İnteqrasiyası (v2-də Yeni)
```powershell
# Intune-a qoşul
Connect-IntuneGhost -Interactive

# Intune siyasətləri vasitəsilə yerləşdir
Set-IntuneGhost -Settings @{
    RDP = $true
    SMBv1 = $true
    USBStorage = $true
    Macros = $true
}
```

## ⚠️ Mühüm Nəzərə Alınacaqlar

### Test Tələbləri
- **Laboratoriya Mühiti**: Bütün tənzimləmələri əvvəlcə təcrid olunmuş mühitdə test edin
- **Mərhələli Yerləşdirmə**: Problemləri müəyyən etmək üçün tədricən yerləşdirin
- **Geri Dönüş Planı**: Lazım olduqda dəyişiklikləri geri qaytara biləcəyinizə əmin olun
- **Sənədləşdirmə**: Mühitiniz üçün hansı tənzimləmələrin işlədiyini qeyd edin

### Potensial Təsir
- **İstifadəçi Məhsuldarlığı**: Bəzi tənzimləmələr gündəlik iş axınına təsir edə bilər
- **Köhnə Tətbiqlər**: Köhnə sistemlər müəyyən protokollar tələb edə bilər
- **Uzaq Giriş**: Qanuni uzaq administrasiyaya təsiri nəzərə alın
- **Biznes Prosesləri**: Tənzimləmələrin kritik funksiyaları pozmamasını yoxlayın

### Təhlükəsizlik Məhdudiyyətləri
- **Dərinlikdə Müdafiə**: Ghost təhlükəsizliyin bir təbəqəsidir, tam həll deyil
- **Davamlı İdarəçilik**: Təhlükəsizlik davamlı monitörinq və yeniləmələr tələb edir
- **İstifadəçi Təlimi**: Texniki nəzarət təhlükəsizlik məlumatlılığı ilə birləşdirilməlidir
- **Təhdid Təkamülü**: Yeni hücum metodları mövcud qorunmanı ötə bilər

## 🎯 Hücum Ssenariləri Nümunələri

Ghost ümumi hücum vektorlarını hədəf aldığı halda, spesifik qarşısının alınması düzgün həyata keçirmə və testdən asılıdır:

### WannaCry-Stil Hücumlar
- **Azaldma**: `Set-Ghost -SMBv1` həssas protokolu söndürür
- **Nəzərə Alınacaq**: Heç bir köhnə sistemin SMBv1 tələb etmədiyinə əmin olun

### RDP Əsaslı Ransomware
- **Azaldma**: `Set-Ghost -RDP` uzaq masaüstü girişini bloklayır
- **Nəzərə Alınacaq**: Alternativ uzaq giriş metodları tələb edə bilər

### Sənəd Əsaslı Malware
- **Azaldma**: `Set-Ghost -Macros` makro icrasını söndürür
- **Nəzərə Alınacaq**: Qanuni makro aktivləşdirilmiş sənədlərə təsir edə bilər

### USB Çatdırılan Təhdidlər
- **Azaldma**: `Set-Ghost -USBStorage -AutoRun` USB funksionallığını məhdudlaşdırır
- **Nəzərə Alınacaq**: Qanuni USB cihaz istifadəsinə təsir edə bilər

## 🏢 Müəssisə Xüsusiyyətləri

### Group Policy Dəstəyi
```powershell
# Tənzimləmələri Group Policy registri vasitəsilə tətbiq et
Set-Ghost -SMBv1 -RDP -AutoRun -GroupPolicy

# GP yenilənməsindən sonra tənzimləmələr domain genişliyində tətbiq olunur
gpupdate /force
```

### Microsoft Intune İnteqrasiyası
```powershell
# Ghost tənzimləmələri üçün Intune siyasətləri yarat
Set-IntuneGhost -Settings $GhostSettings -Interactive

# Siyasətlər avtomatik olaraq idarə olunan cihazlara yerləşdirilir
```

### Uyğunluq Hesabatı
```powershell
# Təhlükəsizlik qiymətləndirmə hesabatı yarat
Get-Ghost | Export-Csv -Path "SecurityAudit-$(Get-Date -Format 'yyyy-MM-dd').csv"

# Azure təhlükəsizlik vəziyyəti hesabatı
Get-AzureGhost | Out-File "AzureSecurityReport.txt"
```

## 📚 Ən Yaxşı Təcrübələr

### Öncə-Yerləşdirmə
1. **Cari Vəziyyəti Sənədləşdir**: Dəyişikliklərdən əvvəl `Get-Ghost` işlət
2. **Hərtərəfli Test Et**: Qeyri-istehsal mühitində doğrula
3. **Geri Dönüş Planla**: Hər tənzimləməni necə geri qaytarmağı bil
4. **Maraqdar Tərəflərin Nəzərdən Keçirməsi**: Biznes bölmələrinin dəyişiklikləri təsdiq etməsini təmin et

### Yerləşdirmə Zamanı
1. **Mərhələli Yanaşma**: İlk olaraq pilot qruplara yerləşdir
2. **Təsiri Monitör Et**: İstifadəçi şikayətlərini və ya sistem problemlərini izlə
3. **Problemləri Sənədləşdir**: Gələcək istinad üçün hər problemi qeyd et
4. **Dəyişiklikləri Bildir**: İstifadəçiləri təhlükəsizlik təkmilləşdirmələri haqqında məlumatlandır

### Sonra-Yerləşdirmə
1. **Müntəzəm Qiymətləndirmə**: Tənzimləmələri yoxlamaq üçün dövri olaraq `Get-Ghost` işlət
2. **Sənədləməni Yenilə**: Təhlükəsizlik konfiqurasiyalarını cari saxla
3. **Effektivliyi Nəzərdən Keçir**: Təhlükəsizlik hadisələrini monitör et
4. **Davamlı Təkmilləşdirmə**: Təhdid mənzərəsinə əsasən tənzimləmələri düzəlt

## 🔧 Problemlərin Həlli

### Ümumi Problemlər
- **İcazə Xətaları**: Yüksəldilmiş PowerShell sessiyasını təmin edin
- **Xidmət Asılılıqları**: Bəzi xidmətlərin asılılıqları ola bilər
- **Tətbiq Uyğunluğu**: Biznes tətbiqləri ilə test edin
- **Şəbəkə Bağlantısı**: Uzaq girişin hələ də işlədiyini yoxlayın

### Bərpa Seçimləri
```powershell
# Lazım olduqda spesifik xidmətləri yenidən aktivləşdir
Set-RDP -Enable
Set-SMBv1 -Enable
Set-AutoRun -Enable
Set-Macros -Enable
```

## 👨‍💻 Müəllif Haqqında

**Jim Tyler** - PowerShell üçün Microsoft MVP
- **YouTube**: [@PowerShellEngineer](https://youtube.com/@PowerShellEngineer) (10,000+ abunəçi)
- **Xəbər Bülleteni**: [PowerShell.News](https://powershell.news) - Həftəlik təhlükəsizlik məlumatları
- **Müəllif**: "PowerShell for Systems Engineers"
- **Təcrübə**: PowerShell avtomatlaşdırılması və Windows təhlükəsizliyinin onillikləri

## 📄 Lisenziya və İmtina

### MIT Lisenziyası
Ghost pulsuz istifadə, dəyişdirmə və paylaşdırma üçün MIT Lisenziyası altında təmin edilir.

### Təhlükəsizlik İmtinası
- **Heç Bir Zəmanət Yoxdur**: Ghost "olduğu kimi" heç bir növ zəmanət olmadan təmin edilir
- **Test Tələb Olunur**: Həmişə əvvəlcə qeyri-istehsal mühitlərində test edin
- **Peşəkar Rəhbərlik**: İstehsal yerləşdirmələri üçün təhlükəsizlik mütəxəssisləri ilə məsləhətləşin
- **Əməliyyat Təsiri**: Müəlliflər hər hansı əməliyyat pozulması üçün məsul deyillər
- **Hərtərəfli Təhlükəsizlik**: Ghost tam təhlükəsizlik strategiyasının bir komponentidir

### Dəstək
- **GitHub Problemləri**: [Xətaları bildir və ya xüsusiyyətlər tələb et](https://github.com/jimrtyler/Ghost/issues)
- **Sənədləşdirmə**: Ətraflı kömək üçün `Get-Help <function> -Full` istifadə et
- **İcma**: PowerShell və təhlükəsizlik icması forumları

---

**🔐 Ghost ilə təhlükəsizlik vəziyyətinizi möhkəmləndirin - amma həmişə əvvəlcə test edin.**

```powershell
# Fərziyyələrlə deyil, qiymətləndirmə ilə başla
Get-Ghost
```

**⭐ Ghost təhlükəsizlik vəziyyətinizi yaxşılaşdırmağa kömək edirsə, bu repozitoriyaya ulduz verin!**
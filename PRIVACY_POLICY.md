# Payna Meeting Note — Gizlilik Politikası

**Türkçe** | [English](#payna-meeting-note--privacy-policy)

*Son güncelleme: 22 Ekim 2026 (uygulama sürümü 0.5.2)*

Payna Meeting Note, toplantılarınızı kaydeden, yazıya döken ve özetleyen bir masaüstü uygulamasıdır. Uygulama, işini **bilgisayarınızda** yapacak şekilde tasarlanmıştır. Bu politika, hangi verilerin cihazınızda kaldığını, hangi durumlarda cihazınızdan çıkabileceğini ve bunu nasıl denetleyebileceğinizi açıklar.

## Kısaca

- Ses kayıtlarınız, transkriptleriniz ve özetleriniz **cihazınızda** saklanır. Uygulama bunları kendiliğinden hiçbir sunucuya göndermez.
- Cihazınızdan veri çıkması yalnızca şu durumlarda olur: (1) **anonim kullanım istatistikleri** (varsayılan olarak açık, istediğiniz zaman kapatılabilir), (2) sizin yazıp gönderdiğiniz **geri bildirim**, (3) özet için sizin seçtiğiniz **harici yapay zekâ servisi**, (4) güncelleme kontrolü ve model indirmeleri gibi **teknik bağlantılar**.
- Toplantı içeriğiniz (ses, transkript, özet, toplantı başlığı, dosya adı) kullanım istatistiklerine **hiçbir zaman** dahil edilmez.

## 1. Cihazınızda kalan veriler

- **Kayıt ve transkripsiyon:** Konuşma tanıma (Whisper veya Parakeet motoru) tamamen cihazınızda çalışır.
- **Özetler:** Cihazınızdaki yerel bir model (yerleşik model veya yerel Ollama) ile üretilebilir. Bu durumda hiçbir içerik cihazınızdan çıkmaz.
- **Saklama:** Kayıtlar, transkriptler, özetler ve yerel veritabanı cihazınızda düzenli dosyalar olarak tutulur. İşletim sisteminizin dosya izinleri ve etkinleştirdiyseniz disk şifrelemesi (BitLocker vb.) bunları korur.
- **Silme:** Bir toplantıyı sildiğinizde hem veritabanı kaydı hem de kayıt klasörü diskten kaldırılır. Uygulamayı kaldırırken "uygulama verisini sil" seçeneğini işaretlemezseniz verileriniz cihazınızda kalır; işaretlerseniz silinir.

## 2. Cihazınızdan çıkabilecek veriler

| Ne | Ne zaman | Nereye | Hangi veri | Denetim |
|---|---|---|---|---|
| Anonim kullanım istatistikleri | Varsayılan olarak açık | PostHog (AB bölgesi sunucuları) | Aşağıda 3. bölümde | Ayarlar veya Hakkında bölümünden kapatılır |
| Geri bildirim | Yalnızca siz gönderirseniz | Payna'nın geri bildirim servisi (Cloudflare) ve e-posta gönderim servisi (Resend) üzerinden Payna ekibine | Yazdığınız mesaj, kategori, isteğe bağlı yanıt adresiniz, uygulama sürümü, işletim sistemi | Göndermek tamamen size bağlı |
| Özet için harici servis | Yalnızca siz bir harici servis seçip kullanırsanız | Seçtiğiniz servis (Claude/Anthropic, Groq, OpenAI, OpenRouter veya kendi uyumlu servisiniz) | Özetlenecek transkript metni (ses kaydı asla gönderilmez) | Yerel model seçerek tamamen önlenir |
| Güncelleme kontrolü | Uygulama açılışında ve "Güncellemeleri Kontrol Et" ile | GitHub (Payna'nın herkese açık sürüm deposu) | Uygulamanın kendisi ek veri göndermez; GitHub, her web sitesi gibi IP adresinizi görür | — |
| Model indirmeleri | Bir konuşma tanıma veya özet modelini indirdiğinizde | Hugging Face ve modelin yayıncısının barındırdığı sunucu | Standart bir indirme isteği; sunucu IP adresinizi görür | Modeli indirmeyerek önlenir |

Harici servisleri (analitik hizmeti hariç) Payna yönetmez; bu servisler kendi gizlilik politikalarına tabidir.

## 3. Anonim kullanım istatistikleri

İstatistikler varsayılan olarak **açıktır** ve **Ayarlar** ile **Hakkında** bölümündeki anahtardan istediğiniz zaman kapatılabilir. Kapattığınızda bundan sonra istatistik verisi gönderilmez.

**Toplananlar:**

- Cihaz başına rastgele üretilmiş, sizi kimliğinizle ilişkilendirmeyen bir kullanıcı numarası.
- Uygulama sürümü, işletim sistemi, sürümü ve işlemci mimarisi.
- Uygulamanın açılması/kapanması, oturum süresi ve günlük kullanım.
- Hangi özelliklerin kullanıldığı; kayıt başlatma/durdurma, kayıt süresi, transkript parça sayısı, ayar değişiklikleri (ayar türü ve seçilen değer, örneğin seçilen model).
- Özet işlemleri: kullanılan sağlayıcı ve model adı, transkript uzunluğu (karakter sayısı), işlemin başarılı olup olmadığı ve süresi, kısaltılmış hata mesajları.
- Toplantılar için rastgele bir toplantı numarası (başlık veya içerik değil).
- Hata olayları. Hata mesajlarındaki dosya yolları kaydedilmeden önce temizlenir ve mesajlar kısaltılır.

**Toplanmayanlar:**

- Toplantı içeriği: ses, transkript, özet, yapay zekâ konuşmaları.
- Toplantı başlıkları, dosya ve klasör adları, dosya yolları.
- Ad, e-posta adresi veya sizi doğrudan tanıtan herhangi bir bilgi.
- Ses cihazlarınızın adları, tarayıcı/kullanıcı aracısı bilgileri.
- Katılımcı adları, API anahtarları ve parolalar.

**İşleme ayrıntıları:**

- **Sağlayıcı:** PostHog, Avrupa (AB) bölgesindeki sunucularıyla. Analitik projemiz, istemci IP adreslerini saklamayacak şekilde yapılandırılmıştır.
- **Amaç:** Hataları bulmak, performansı iyileştirmek ve hangi özelliklerin işe yaradığını anlayarak ürünü geliştirmek.
- **Erişim:** Yalnızca Payna ekibindeki yetkili kişiler.
- **Saklama:** İstatistik verisini yukarıdaki amaçlar için gerektiği süre boyunca tutarız.

## 4. API anahtarları

Harici bir yapay zekâ servisi için girdiğiniz API anahtarı yalnızca işletim sisteminizin güvenli kimlik bilgisi deposunda (Windows Kimlik Bilgisi Yöneticisi, macOS Anahtar Zinciri, Linux Secret Service) saklanır. Uygulamanın veritabanına veya düz metin dosyalara yazılmaz ve Payna'ya gönderilmez.

## 5. Haklarınız

Verileriniz cihazınızda olduğu için çoğu işlemi doğrudan kendiniz yapabilirsiniz: görüntüleyebilir, dışa aktarabilir ve silebilirsiniz. İstatistikleri istediğiniz zaman kapatabilirsiniz. Cihaz kimliğiniz (rastgele numara) üzerinden istatistik verisiyle ilgili talepleriniz için, ayrıca yanıt adresi bıraktıysanız geri bildirimlerinizle ilgili taleplerinizin silinmesi veya bilgi verilmesi için aşağıdaki iletişim yolundan bize ulaşabilirsiniz. Geçerli veri koruma mevzuatı (6698 sayılı KVKK ve uygulandığı durumlarda GDPR) kapsamındaki haklarınız saklıdır.

## 6. Değişiklikler

Bu politikada önemli bir değişiklik olduğunda güncel metni bu depoda yayımlar ve sürüm notlarında belirtiriz. Sayfanın başındaki tarih, son güncelleme tarihini gösterir.

## 7. İletişim

Gizlilikle ilgili sorularınız için [GitHub Issues](https://github.com/Payna-AI/payna-meeting-note-releases/issues) üzerinden bize yazabilir veya uygulamadaki geri bildirim düğmesini kullanabilirsiniz. Issues herkese açıktır; lütfen kişisel bilgilerinizi orada paylaşmayın, bu tür talepler için geri bildirim düğmesini kullanın.

## 8. Açık kaynak

Payna Meeting Note, MIT lisanslı **Meetily** projesinden türetilmiştir. Veri işleme kodunun tamamı kaynak kodda incelenebilir.

---

# Payna Meeting Note — Privacy Policy

[Türkçe](#payna-meeting-note--gizlilik-politikası) | **English**

*Last updated: 22 October 2026 (app version 0.5.2)*

Payna Meeting Note is a desktop app that records, transcribes and summarizes your meetings. It is designed to do its work **on your own computer**. This policy explains which data stays on your device, when data can leave it, and how you can control that.

## In short

- Your audio recordings, transcripts and summaries are stored **on your device**. The app does not send them to any server on its own.
- Data leaves your device only in these cases: (1) **anonymous usage analytics** (on by default, can be turned off at any time), (2) **feedback** that you write and send, (3) an **external AI service** that you choose for summaries, (4) **technical connections** such as update checks and model downloads.
- Your meeting content (audio, transcripts, summaries, meeting titles, file names) is **never** part of the usage analytics.

## 1. Data that stays on your device

- **Recording and transcription:** Speech recognition (the Whisper or Parakeet engine) runs entirely on your device.
- **Summaries:** Can be generated by a local model on your device (the built-in model or a local Ollama install). In that case no content leaves your device.
- **Storage:** Recordings, transcripts, summaries and the local database are kept as regular files on your device, protected by your operating system's file permissions and by disk encryption if you have enabled it (BitLocker etc.).
- **Deletion:** Deleting a meeting removes both its database record and its recording folder from disk. If you do not tick "delete application data" when uninstalling, your data stays on your device; if you do, it is deleted.

## 2. Data that can leave your device

| What | When | Where to | Which data | Your control |
|---|---|---|---|---|
| Anonymous usage analytics | On by default | PostHog (EU region servers) | See section 3 | Turn off in Settings or About |
| Feedback | Only if you submit it | Payna's feedback service (Cloudflare) and email delivery service (Resend), to the Payna team | Your message, category, optional reply address, app version, operating system | Entirely up to you |
| External service for summaries | Only if you choose and use one | The service you pick (Claude/Anthropic, Groq, OpenAI, OpenRouter or your own compatible endpoint) | The transcript text to be summarized (audio is never sent) | Avoided entirely by choosing a local model |
| Update check | At app start and via "Check for Updates" | GitHub (Payna's public releases repository) | The app sends no additional data; GitHub sees your IP address like any website | — |
| Model downloads | When you download a speech or summary model | Hugging Face and the server hosted by the model's publisher | A standard download request; the server sees your IP address | Avoided by not downloading the model |

Payna does not operate the external services (other than the analytics service); they are subject to their own privacy policies.

## 3. Anonymous usage analytics

Analytics is **on by default** and can be turned off at any time with the switch in **Settings** and **About**. Once turned off, no further analytics data is sent.

**What is collected:**

- A randomly generated per-device user ID that does not identify you by identity.
- App version, operating system, its version and processor architecture.
- App start/stop, session duration and daily usage.
- Which features are used; recording start/stop, recording duration, transcript segment count, settings changes (setting type and chosen value, for example the selected model).
- Summary operations: provider and model name, transcript length (character count), success and duration, shortened error messages.
- A random meeting ID for meetings (not the title or any content).
- Error events. File paths in error messages are removed before recording, and messages are truncated.

**What is not collected:**

- Meeting content: audio, transcripts, summaries, AI conversations.
- Meeting titles, file and folder names, file paths.
- Your name, email address or any information that directly identifies you.
- Names of your audio devices, browser/user-agent information.
- Participant names, API keys and passwords.

**Processing details:**

- **Provider:** PostHog, using servers in the European (EU) region. Our analytics project is configured not to store client IP addresses.
- **Purpose:** Finding bugs, improving performance, and improving the product by understanding which features are useful.
- **Access:** Only authorized members of the Payna team.
- **Retention:** We keep analytics data only as long as needed for the purposes above.

## 4. API keys

An API key you enter for an external AI service is stored only in your operating system's secure credential store (Windows Credential Manager, macOS Keychain, Linux Secret Service). It is never written to the app's database or to plain-text files and is never sent to Payna.

## 5. Your rights

Because your data is on your device, you can do most things yourself: view, export and delete it. You can turn analytics off at any time. For requests about analytics data linked to your device ID (the random number), or, if you left a reply address, about your feedback, you can contact us through the channel below to ask for information or deletion. Your rights under applicable data protection law (Turkish KVKK, Law No. 6698, and the GDPR where applicable) remain reserved.

## 6. Changes

When we make a material change to this policy we publish the updated text in this repository and mention it in the release notes. The date at the top shows the last update.

## 7. Contact

For privacy questions, write to us on [GitHub Issues](https://github.com/Payna-AI/payna-meeting-note-releases/issues) or use the feedback button in the app. Issues are public; please do not post personal information there, and use the feedback button for such requests.

## 8. Open source

Payna Meeting Note is derived from the MIT-licensed **Meetily** project. All data-handling code can be reviewed in the source code.

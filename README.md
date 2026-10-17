# Payna Meeting Note

**Türkçe** | [English](#english)

Payna Meeting Note, toplantılarınızı kaydeden, gerçek zamanlı yazıya döken ve özetleyen, bunların hepsini **bilgisayarınızda** yapan bir masaüstü uygulamasıdır. Kayıtlarınız, transkriptleriniz ve özetleriniz cihazınızdan çıkmaz.

- [Neler yapar?](#neler-yapar)
- [İndirme ve kurulum](#indirme-ve-kurulum)
- [Güncelleme](#güncelleme)
- [Gizlilik](#gizlilik)
- [Lisans ve teşekkür](#lisans-ve-teşekkür)

## Neler yapar?

- **Yerelde çalışır:** Kayıt, transkripsiyon ve (yerel model seçilirse) özetleme bilgisayarınızda yapılır. Veri buluta gönderilmez.
- **Gerçek zamanlı transkript:** Toplantı sürerken konuşmaları canlı olarak yazıya döker. Türkçe dahil birçok dili destekler.
- **Mikrofon ve sistem sesi:** Mikrofonunuzu ve bilgisayardan çalan sesi birlikte kaydedebilir; çevrimiçi toplantılar için uygundur.
- **Yapay zekâ ile özet:** Toplantı bitince özet çıkarır. Toplantı türüne uygun şablonlar vardır (günlük toplantı, proje senkronu, retrospektif, müşteri görüşmesi, standart toplantı gibi).
- **Model seçimi size ait:** Özet için bilgisayarınızda çalışan yerel modelleri kullanabilir veya isterseniz Claude, Groq, OpenRouter ya da kendi OpenAI uyumlu servisinizi bağlayabilirsiniz.
- **Ekran kartı hızlandırma:** NVIDIA ekran kartlarında CUDA ile daha hızlı çalışan ayrı bir sürüm bulunur (NVIDIA ekran kartı ve güncel sürücü gerekir).
- **Türkçe ve İngilizce arayüz,** açık ve koyu tema.
- **Uygulama içinden geri bildirim:** Sorunları ve önerileri uygulamadaki şikayet butonundan iletebilirsiniz.

## İndirme ve kurulum

Şu an yayınlanan sürümler **Windows 10/11 (x64)** içindir. İşlemcinizin **AVX2** desteği olmalıdır (yaklaşık 2013 sonrası Intel ve 2015 sonrası AMD işlemciler). CUDA sürümü için ayrıca **NVIDIA ekran kartı ve güncel NVIDIA sürücüsü** gerekir.

### Önerilen yol: Kurulum sihirbazı (launcher)

1. [Payna-Meeting-Note-Launcher.exe](https://github.com/Payna-AI/payna-meeting-note-releases/releases/latest/download/Payna-Meeting-Note-Launcher.exe) dosyasını indirin ve çalıştırın.
2. Launcher ekran kartınızı tanır ve size uygun sürümü seçer: NVIDIA kartı olanlar için CUDA sürümü (yaklaşık 421 MB indirme, yaklaşık 1,6 GB kurulum), diğerleri için standart sürüm (yaklaşık 41 MB indirme, yaklaşık 160 MB kurulum). Ekran kartınız NVIDIA ise ama sürücüsü kurulu değilse CUDA sürümü açılmaz; önce sürücüyü kurun veya standart sürümü kullanın.
3. Kurulum klasörünü onaylayın, indirme ve kurulum bitene kadar bekleyin.
4. İsterseniz kurulum bitince uygulamayı doğrudan başlatın.

### Windows SmartScreen uyarısı

Uygulama ve launcher henüz kod imzalama sertifikasıyla imzalanmadığı için Windows ilk çalıştırmada "Windows bilgisayarınızı korudu" uyarısı gösterebilir. Bu, dosyanın zararlı olduğu anlamına gelmez; Windows yalnızca yayıncıyı doğrulayamadığını belirtir. Devam etmek için:

1. **Daha fazla bilgi** bağlantısına tıklayın.
2. **Yine de çalıştır** düğmesine basın.

### Elle kurulum

Launcher kullanmak istemezseniz [Releases](https://github.com/Payna-AI/payna-meeting-note-releases/releases/latest) sayfasından doğrudan kurulum dosyasını indirebilirsiniz:

- `Payna.Meeting.Note_<sürüm>_x64-setup.exe`: standart sürüm
- `Payna.Meeting.Note-cuda_<sürüm>_x64-setup.exe`: NVIDIA (CUDA) sürümü
- `Payna.Meeting.Note_<sürüm>_x64_en-US.msi`: MSI paketi

NVIDIA ekran kartı ve sürücüsü olmayan bilgisayarlarda `-cuda` sürümünü indirmeyin; standart sürümü kullanın. İlk kullanımda gerekli modeller uygulama içinden indirilir.

## Güncelleme

Uygulama açılırken yeni sürümü kendiliğinden kontrol eder. Yeni sürüm varsa bildirim gösterir; bildirimden güncellemeyi uygulama içinde indirip kurabilirsiniz. Elle kontrol için **Hakkında → Güncellemeleri Kontrol Et** düğmesini kullanabilirsiniz.

> **CUDA sürümü kullanıyorsanız:** v0.5.x CUDA kurulumlarında uygulama içi güncelleme standart sürümü önerebilir. Bu durumda güncellemeyi uygulama içinden kurmayın; yeni sürümü launcher ile yeniden kurun.

## Gizlilik

- Kayıtlar, transkriptler ve özetler bilgisayarınızda saklanır. Yerel model kullandığınızda hiçbir içerik cihazınızdan çıkmaz.
- Özet için Claude, Groq, OpenRouter gibi harici bir servis seçerseniz, özetlenecek metin yalnızca o servise gönderilir. Bu seçim size aittir.
- Anonim kullanım istatistikleri varsayılan olarak **açıktır**; **Ayarlar** bölümünden istediğiniz zaman kapatabilirsiniz. Bu istatistikler toplantı içeriğinizi (ses, transkript, özet) içermez.
- Geri bildirim butonunu kullandığınızda yalnızca yazdığınız mesaj, isteğe bağlı yanıt adresiniz, uygulama sürümü ve işletim sistemi bilgisi gönderilir.

Ayrıntılar için [Gizlilik Politikası](PRIVACY_POLICY.md) sayfasına bakın.

## Lisans ve teşekkür

Payna Meeting Note, [Zackriya Solutions](https://github.com/Zackriya-Solutions/meeting-minutes) tarafından geliştirilen MIT lisanslı **Meetily** projesinden türetilmiştir. Özgün projenin geliştiricilerine ve katkı verenlere teşekkür ederiz. Lisans MIT'dir; özgün telif ve lisans notu (Copyright (c) 2024 Zackriya Solutions) korunmuştur.

Ayrıca şu projelere ve emeklere de teşekkür ederiz:

- [Whisper.cpp](https://github.com/ggerganov/whisper.cpp), [Screenpipe](https://github.com/mediar-ai/screenpipe) ve [transcribe-rs](https://crates.io/crates/transcribe-rs): kodundan faydalanılan projeler.
- **NVIDIA:** Parakeet modeli için.
- [istupakov](https://huggingface.co/istupakov/parakeet-tdt-0.6b-v3-onnx): Parakeet modelinin ONNX dönüşümü için.

---

<a id="english"></a>

# Payna Meeting Note (English)

[Türkçe](#payna-meeting-note) | **English**

Payna Meeting Note is a desktop app that records your meetings, transcribes them in real time and summarizes them, all **on your own computer**. Your recordings, transcripts and summaries do not leave your device.

- [What it does](#what-it-does)
- [Download and install](#download-and-install)
- [Updates](#updates)
- [Privacy](#privacy)
- [License and credits](#license-and-credits)

## What it does

- **Runs locally:** Recording, transcription and (when a local model is selected) summarization happen on your computer. No data is sent to the cloud.
- **Real-time transcript:** Live transcription while the meeting is in progress, with support for many languages including Turkish.
- **Microphone and system audio:** Can record your microphone and the sound playing on your computer together, which suits online meetings.
- **AI summaries:** Generates a summary when the meeting ends, with templates for different meeting types (daily standup, project sync, retrospective, client call, standard meeting and more).
- **You choose the model:** Use local models running on your computer, or connect Claude, Groq, OpenRouter or your own OpenAI-compatible service if you prefer.
- **GPU acceleration:** A separate build uses CUDA for faster processing on NVIDIA graphics cards (an NVIDIA GPU and an up-to-date driver are required).
- **Turkish and English interface,** with light and dark themes.
- **In-app feedback:** Send problems and suggestions with the feedback button inside the app.

## Download and install

Published releases currently target **Windows 10/11 (x64)**. Your processor must support **AVX2** (roughly Intel from 2013 and AMD from 2015 onwards). The CUDA build additionally needs an **NVIDIA graphics card and an up-to-date NVIDIA driver**.

### Recommended: the installer wizard (launcher)

1. Download and run [Payna-Meeting-Note-Launcher.exe](https://github.com/Payna-AI/payna-meeting-note-releases/releases/latest/download/Payna-Meeting-Note-Launcher.exe).
2. The launcher detects your graphics card and picks the right build: the CUDA build for NVIDIA cards (about 421 MB download, about 1.6 GB installed) or the standard build for everything else (about 41 MB download, about 160 MB installed). If you have an NVIDIA card but no NVIDIA driver installed, the CUDA build will not start; install the driver first or use the standard build.
3. Confirm the install folder and wait for the download and installation to finish.
4. Optionally start the app right after installation.

### Windows SmartScreen warning

Because the app and the launcher are not yet signed with a code-signing certificate, Windows may show a "Windows protected your PC" warning the first time you run them. This does not mean the file is harmful; Windows simply cannot verify the publisher. To continue:

1. Click **More info**.
2. Click **Run anyway**.

### Manual install

If you prefer not to use the launcher, download an installer directly from the [Releases](https://github.com/Payna-AI/payna-meeting-note-releases/releases/latest) page:

- `Payna.Meeting.Note_<version>_x64-setup.exe`: standard build
- `Payna.Meeting.Note-cuda_<version>_x64-setup.exe`: NVIDIA (CUDA) build
- `Payna.Meeting.Note_<version>_x64_en-US.msi`: MSI package

Do not download the `-cuda` build on a computer without an NVIDIA graphics card and driver; use the standard build instead. Required models are downloaded from within the app on first use.

## Updates

The app checks for new versions on startup and shows a notification when one is available; you can download and install the update inside the app. You can also check manually from **About → Check for Updates**.

> **If you use the CUDA build:** on v0.5.x CUDA installs the in-app update may offer the standard build. In that case do not install the update from inside the app; reinstall the new version with the launcher instead.

## Privacy

- Recordings, transcripts and summaries are stored on your computer. With a local model, no content leaves your device.
- If you choose an external service such as Claude, Groq or OpenRouter for summaries, the text to be summarized is sent only to that service. The choice is yours.
- Anonymous usage analytics are **on by default**; you can turn them off at any time in **Settings**. They never include your meeting content (audio, transcripts, summaries).
- When you use the feedback button, only the message you write, your optional reply address, the app version and the operating system are sent.

For details see the [Privacy Policy](PRIVACY_POLICY.md).

## License and credits

Payna Meeting Note is derived from the MIT-licensed **Meetily** project by [Zackriya Solutions](https://github.com/Zackriya-Solutions/meeting-minutes). We thank the original authors and contributors. The license is MIT, and the original copyright and license notice (Copyright (c) 2024 Zackriya Solutions) are preserved.

We also thank:

- [Whisper.cpp](https://github.com/ggerganov/whisper.cpp), [Screenpipe](https://github.com/mediar-ai/screenpipe) and [transcribe-rs](https://crates.io/crates/transcribe-rs): projects whose code we build on.
- **NVIDIA:** for the Parakeet model.
- [istupakov](https://huggingface.co/istupakov/parakeet-tdt-0.6b-v3-onnx): for the ONNX conversion of the Parakeet model.

# CaddeGarage — Web Sitesi

**Sanal yollarda gerçek takım ruhu.** ETS2 dünyasında birlik, dostluk ve profesyonellik üzerine kurulu sanal lojistik ve konvoy topluluğunun resmi sitesi.

🔗 **Canlı:** https://caddegarage.com

## İçerik

| Dosya | Ne içerir |
|---|---|
| `index.html` | Tek sayfalık site: Ana Sayfa, Hakkımızda, Filo, Galeri, Konvoy Takvimi, Başvuru, İletişim |
| `css/style.css` | Tüm stiller (koyu tema, krom degrade metin, responsive) |
| `js/main.js` | Sayaç animasyonları, galeri lightbox, konvoy katılım (localStorage), başvuru + iletişim formları, sürücü paneli |
| `assets/img/` | Logo, favicon, hero fotoğrafı ve el yapımı SVG sahne görselleri |
| `tools/gen-scenes.js` | SVG sahne görsellerini yeniden üretmek için (Node 16+, `node tools/gen-scenes.js`) |

## Yerelde çalıştır

```bash
node -e "require('http').createServer((q,s)=>s.end(require('fs').readFileSync(q.url==='/'?'index.html':q.url.slice(1))).on('error',()=>s.end('404'))).listen(8123)"
```

veya herhangi bir statik sunucu ile `index.html`'i açın.

## Dağıtım

Cloudflare Pages'e GitHub deposu bağlanarak yayınlanır. `main` dalına her push, siteyi otomatik olarak günceller.

- **Build komutu:** yok (statik site)
- **Output dizini:** `/`
- **Özel alan adı:** `caddegarage.com`

## Varlıklar hakkında

Tır görselleri ve logo, topluluk için Gemini ile üretilmiş özgün görsellerdir. SVG sahneler `tools/gen-scenes.js` ile prosedürel olarak üretilir.

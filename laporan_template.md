# Laporan Mini Assignment — Universal Dependencies Bahasa Indonesia

**Nama / Kelompok:** Karl Erich Sihombing
**Kelas:** NLP 
**Tanggal:** 28 Oktober 2026

## A. Ringkasan hasil

Pada *dependemcy tree visualization* membandingkan 2 tree dengan makna yang sama namun memiliki perbedaan pada pola kalimat dimana yang satu merupakan kalimat aktif dan kaimat pasif. Pada tree kita bisa melihat kata mana yang menjadi head dan kata mana yang menjadi dependent, hal itu juga diperjelas pada bagian token inspector yang juga menyediakan informasi suatu kata seperti yang mana head nya DEPREL dsb. Di dalamnya juga terdapat informasi mengenai sifat kata mana yang berubah antara aktif dan pasif seperti contohnya kata *Siti* merupakan *nsubj* pada aktif namun berubah menjadi *obl* pada pasif

## B. Perbandingan *active–passive voice*

| Semantic role (interpretasi manual) | Active: token + `DEPREL` | Passive: token + `DEPREL` | Apa yang berubah? |
|---|---|---|---|
| Agent | Siti -> nsubj | Siti -> obl:agent | Peran kata yang sebelumnya dari sebagai subyek pada kalimat aktif berubah fungsi menjadi oblique sebagai informasi tambahan |
| Patient | buku -> obj | buku -> nsubj:pass | fungsi kata yang sebelumnya merupakan objek yang "dijelaskan" kini menjadi subjek yang "menjelaskan" pada kalimat pasif |
| Location | perpustakaan -> obl | perpustakaan -> obl | Tidak ada perubahan |

## C. Jawaban analisis (200–300 kata total)

**C1.** Mengapa `buku` berubah dari `obj` menjadi `nsubj:pass`?

Universal Dependency mencatat fungsi gramatikal. Pada kalimat aktif, bukuadalah objek langsung dari membaca. Pada kalimat pasif, argumen yang dikenal tindakan naik menjadi subjek gramatikal dari dibaca. Meskipun secara makna tetap sama namun hanya posisi dalam kalimat saja yang berubah.

**C2.** Mengapa `Siti` berubah dari `nsubj` menjadi `obl:agent`?

Siti tetap sebagai pelaku membaca secara makna, namun pada pasif ia bukan lagi subjek dan menjadi argumen diluar kalimat inti sehingga berlabel obl:agent. Dengan demikian secara tata berubah namun secara makna tidak

**C3.** Mengapa `di` di “di perpustakaan” menjadi token `case`, tetapi `di-` pada “dibaca” tidak menjadi node sintaksis tersendiri?

kata di pada "di perpustakaan" adalah kata terpisah (ADP), sehingga menjadi node sendiri dengan relasi case terhadap perpustakaan yang menjadi head. Namun kata di pada dibaca adalah prefiks satu kata. Karena Universal Dependency berbasis lexicalism, dibaca tetap satu node dan informasi pasifnya dicatat di FEATS

**C4.** Bagaimana temuan Anda terhubung dengan minimal satu bagian paper (§2.1, §2.2, §2.5, §2.7)?

Yang paling relevan adalah §2.5. Preposisi tidak menjadi head frasa, melainkan case dari kata isi. Contohnya case(perpustakaan, di) dan case(Siti, oleh). Akibatnya Siti dan perpustakaan tetap menjadi head frasa nominalnya, sehingga obl:agent dan obl terhubung langsung ke verba dibaca. Ini membuat struktur lebih mudah dibandingkan antarbahasa, termasuk bahasa yang memakai akhiran kasus, bukan preposisi.

## D. Modifikasi kode

**Fitur yang ditambahkan:** ...

**File dan bagian yang diubah:** ...

**Hasil pengujian:** ...

**Screenshot before/after:** (sertakan gambar dengan Markdown jika tersedia)

## E. Refleksi

Apa satu hal tentang Bahasa Indonesia atau UD yang baru Anda pahami setelah melihat visualisasi?

...

## F. Referensi

- de Marneffe et al. (2015 revision). [*Universal Dependencies: A cross-linguistic typology*](https://nlp.stanford.edu/~manning/papers/USD_LREC14_UD_revision.pdf).
- [Universal Dependencies — Indonesian-GSD](https://universaldependencies.org/treebanks/id_gsd/index.html).
- Dokumentasi UD v2 lain yang Anda gunakan: ...

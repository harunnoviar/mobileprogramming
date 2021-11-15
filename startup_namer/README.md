# Mobile Programming

Pertemuan ke-6 </br>
Latihan ke 2 </br>
NIM : 12201770 </br>
Nama : Harun Noviar </br>
Prodi : Informatika - B

## Project 2 startup_namer

Project ke-2 adalah contoh program sederhana menampilkan list daftar nama perusahaan yang diusulkan sebagai startup. Dalam program ini pengguna dapat memilih nama-nama perusahaan dan juga dapat membatalkan pilihannya. </br>
Beberapa hal keterangan dari kode baris program diatas antara lain:

- Merubah isi dari lib/main.dart dengan kode baris program dari [sini](https://github.com/flutter/codelabs/blob/master/startup_namer/step4_infinite_list/lib/main.dart)

- Melakukan penambahan import package pada baris awal yaitu:

```ruby
'package:english_words/english_words.dart';
```

- Sebelum melakukan import diharuskan menambahkan package <b>english_words</b> pada framework flutter dengan cara:

```ruby
$ flutter pub add english_words
```

- Menambahkan <b>\_saved</b> pada class <b>\_RandomWordsState</b> menggunakan keyword final, tujuannya adalah menyimpan WordPair yang difavoritkan oleh pengguna aplikasi.

```ruby
final _saved = <WordPair>{};
```

- Pada function <b>\_bulidRow</b> tambahkan dengan keyword final variable <b>alreadySaved</b>

```ruby
final alreadySaved = _saved.contains(pair);
```

- Tambahkan juga baris berikut pada function <b>\_bulidRow</b> dibagian <b>ListTile</b> untuk menambahakn icon "heart".

```ruby
trailing: Icon(
      alreadySaved ? Icons.favorite : Icons.favorite_border,
      color: alreadySaved ? Colors.red : null,
      semanticLabel: alreadySaved ? 'Remove from saved' : 'Save',
),
```

- Tambahkan <b>onTap</b> setelah <b>trailing</b> diatas pada function <b>\_bulidRow</b>, tujuannya agar icon "heart" dapat di-tap kemudian tersimpan ke favorited state dan apabila di-tap kembali dihapus dari favorited state.

```ruby
onTap: () {
        setState(() {
          if (alreadySaved) {
            _saved.remove(pair);
          } else {
            _saved.add(pair);
          }
        });
},
```

- Membuat navigator dengan menambahkan pada widget <b>build</b> action button.

```ruby
actions: [
          IconButton(
            icon: const Icon(Icons.list),
            onPressed: _pushSaved,
            tooltip: 'Saved Suggestions',
          ),
],
```

- Membuat function <b>\_pushSaved</b> dalam class <b>\_RandomWordsState</b> yang berisi Navigator dan MaterialPageRoute. pada function ini me-return <b>Scaffold</b> yang berisi bar aplikasi denga route baru <b>SavedSuggestions</b>. Sedangkan isi dari route baru tersebut adalah Listview yang terdiri dari baris ListTiles.

```ruby
void _pushSaved() {
    Navigator.of(context).push(
      MaterialPageRoute<void>(
        builder: (context) {
          final tiles = _saved.map(
            (pair) {
              return ListTile(
                title: Text(
                  pair.asPascalCase,
                  style: _biggerFont,
                ),
              );
            },
          );
          final divided = tiles.isNotEmpty
              ? ListTile.divideTiles(
                  context: context,
                  tiles: tiles,
                ).toList()
              : <Widget>[];

          return Scaffold(
            appBar: AppBar(
              title: const Text('Saved Suggestions'),
            ),
            body: ListView(children: divided),
          );
        },
    );
  }
```

- Melakukan modifikasi pada theme dengan menambahkan themeData pada class <b>MyApp</b>.

```ruby
theme: ThemeData(
        appBarTheme: const AppBarTheme(
          backgroundColor: Colors.white,
          foregroundColor: Colors.black,
        ),
),
```

## Sumber

https://codelabs.developers.google.com/codelabs/first-flutter-app-pt1#2

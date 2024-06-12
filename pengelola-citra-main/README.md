# Praktikum Pert13
| **Nama**            | **Muhamad Jati Wasesa** |
|---------------------|-------------------------|
| **NIM**             | **31210481**            |
| **Kelas**           | **TI.22.A5**            |

# Steganografi dengan Python

Repository ini berisi skrip Python yang memungkinkan Anda menyembunyikan dan mengekstrak teks rahasia dalam gambar menggunakan pustaka Pillow.

## Persyaratan

- Python 3.x
- Pustaka Pillow

## Instalasi

1. **Clone repository ini:**

    ```sh
    git clone https://github.com/Muhjat7/pengelola-citra.git
    ```

2. **Instal pustaka Python yang diperlukan:**

    ```sh
    pip install pillow
    ```

## Penggunaan

### Menyembunyikan Teks dalam Gambar

Untuk menyembunyikan teks rahasia dalam gambar, gunakan fungsi `hide_text`.

**Contoh:**

```python
from PIL import Image

def hide_text(image_path, secret_text, output_path):
    # Membuka gambar
    image = Image.open(image_path)

    # Mengonversi teks rahasia ke biner
    binary_secret_text = ''.join(format(ord(char), '08b') for char in secret_text)

    # Memeriksa apakah gambar dapat menampung teks rahasia
    image_capacity = image.width * image.height * 3
    if len(binary_secret_text) > image_capacity:
        raise ValueError("Gambar tidak memiliki kapasitas yang cukup untuk menyembunyikan teks rahasia.")

    # Menyembunyikan teks rahasia dalam gambar
    pixels = image.load()
    index = 0
    for i in range(image.width):
        for j in range(image.height):
            r, g, b = pixels[i, j]

            if index < len(binary_secret_text):
                r = (r & 0xFE) | int(binary_secret_text[index])
                index += 1
            if index < len(binary_secret_text):
                g = (g & 0xFE) | int(binary_secret_text[index])
                index += 1
            if index < len(binary_secret_text):
                b = (b & 0xFE) | int(binary_secret_text[index])
                index += 1

            pixels[i, j] = (r, g, b)

    # Menyimpan gambar dengan teks rahasia tersembunyi
    image.save(output_path)

image_path = 'C:/Users/ASUS/Pictures/anime.PNG'
secret_text = 'This is a secret message.'
output_path = 'C:/Users/ASUS/Downloads/web/anime_output.png'
hide_text(image_path, secret_text, output_path)
# Praktikum Pert13
| **Nama**            | **Muhamad Jati Wasesa** |
|---------------------|-------------------------|
| **NIM**             | **31210481**            |
| **Kelas**           | **TI.22.A5**            |

# Steganografi dengan Python

Repository ini berisi skrip Python yang memungkinkan Anda menyembunyikan dan mengekstrak teks rahasia dalam gambar menggunakan pustaka Pillow.

## Persyaratan

- Python 3.x
- Pustaka Pillow

## Instalasi

1. **Clone repository ini:**

    ```sh
    git clone https://github.com/usernameanda/steganografi.git
    cd steganografi
    ```

2. **Instal pustaka Python yang diperlukan:**

    ```sh
    pip install pillow
    ```

## Penggunaan

### Menyembunyikan Teks dalam Gambar

Untuk menyembunyikan teks rahasia dalam gambar, gunakan fungsi `hide_text`.

**Contoh:**

```python
from PIL import Image

def hide_text(image_path, secret_text, output_path):
    # Membuka gambar
    image = Image.open(image_path)

    # Mengonversi teks rahasia ke biner
    binary_secret_text = ''.join(format(ord(char), '08b') for char in secret_text)

    # Memeriksa apakah gambar dapat menampung teks rahasia
    image_capacity = image.width * image.height * 3
    if len(binary_secret_text) > image_capacity:
        raise ValueError("Gambar tidak memiliki kapasitas yang cukup untuk menyembunyikan teks rahasia.")

    # Menyembunyikan teks rahasia dalam gambar
    pixels = image.load()
    index = 0
    for i in range(image.width):
        for j in range(image.height):
            r, g, b = pixels[i, j]

            if index < len(binary_secret_text):
                r = (r & 0xFE) | int(binary_secret_text[index])
                index += 1
            if index < len(binary_secret_text):
                g = (g & 0xFE) | int(binary_secret_text[index])
                index += 1
            if index < len(binary_secret_text):
                b = (b & 0xFE) | int(binary_secret_text[index])
                index += 1

            pixels[i, j] = (r, g, b)

    # Menyimpan gambar dengan teks rahasia tersembunyi
    image.save(output_path)

image_path = 'C:/Users/ASUS/Pictures/anime.PNG'
secret_text = 'This is a secret message.'
output_path = 'C:/Users/ASUS/Downloads/web/anime_output.png'
hide_text(image_path, secret_text, output_path)
```
### hasil

![337191400-277a1492-33fd-456f-b96e-ad39f48a2c3e](https://github.com/Muhjat7/pengelola-citra/assets/129918243/00047f9b-e733-4c13-9c25-f1721ef1b036)



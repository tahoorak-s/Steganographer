# 🕵️‍♂️ Image Steganography with Google Colab

This project demonstrates how to hide and extract secret messages inside image files using **Least Significant Bit (LSB) steganography**. It is built using **Python** and runs entirely in a **Google Colab Notebook** — no installation required on your computer.

---

## 🔍 What is Steganography?

**Steganography** is the art of hiding information in plain sight — in this case, embedding secret messages into image files. By changing the least significant bits of pixels in an image, we can store data without changing how the image looks to the human eye.

---

## 📂 Features

✅ Hide secret messages inside PNG images  
✅ Decode hidden messages from images  
✅ No visible distortion in the image  
✅ Runs fully on Google Colab  
✅ Easy-to-understand Python code with comments

---

## 🛠 Requirements

- Python 3 (comes pre-installed in Colab)
- [Pillow](https://python-pillow.org/) for image manipulation

---

## 🚀 Getting Started

### 1. **Open the Colab Notebook**

> 🔗 [Click here to open in Google Colab](https://colab.research.google.com)  
> Create a new notebook and paste the provided code cells (or upload the `.ipynb` file).

### 2. **Upload an Image**

- Upload a **PNG** image using the `files.upload()` cell.
- Image must be named `test_image.png` (or update the filename in the code).

### 3. **Encode a Message**
Run:
```python
encode_message("test_image.png", "Your secret message here", "encoded_image.png")
````

### 4. **Decode a Message**

Run:

```python
decode_message("encoded_image.png")
```

### 5. **Download the Encoded Image**

Run:

```python
files.download("encoded_image.png")
```

---

## 💡 How It Works

Each pixel in an image is made of Red, Green, and Blue (RGB) channels, each stored as 8 bits (values from 0–255).
This project modifies the **last bit** of each channel to store message bits.
The change is too small to affect the image visually.

> Example:
>
> * Original Red value: `11001010` (202)
> * After encoding: `11001011` (203) → visually identical

---

## 📸 Input/Output

| Input            | Output              |
| ---------------- | ------------------- |
| `test_image.png` | `encoded_image.png` |
| `Hello world!`   | Hidden in the image |

---

## 🔐 Limitations

* Only works on **lossless formats** like PNG (not JPEG).
* Message length limited by number of pixels × 3 bits.
* No built-in encryption (can be added as an extension).

---

## 🧠 Future Improvements

* Add **password protection** using simple encryption
* Allow hiding **text files** instead of plain strings
* Add **GUI with Gradio or Streamlit**
* Extend support for video/audio steganography

---





<!-- Author: Samir Paul -->

<div align="center">
  <h1>Online PDF Compression Tool </h1>
</div>

### 💡About The Project:

An online PDF file compression tool to reduce the size of a .pdf file. Python Flask is used to upload the file to a temporary location on the server. 
In the backend, using the ```PDFNetPython``` library that file gets reduced and saved to its final location. After download, the files are automatically deleted from the server after 1 hour. Technologies used in this project: ```Python3```, ```Flask```, ```C```, ```Shell```, ```Nix```, ```Replit```, ```Git```, ```HTML```, ```CSS```, ```JavaScript```.


- [Demo 🚀 ](https://filecompressor.samirpaul1.repl.co)

## Video:
https://user-images.githubusercontent.com/77569653/172896703-9e4998c1-40da-46ae-810e-780e47a391f9.mp4




-[x] Landing Page:
![screenshot](https://raw.githubusercontent.com/SamirPaulb/assets/main/filecompressor-samirpaul1-repl-co-landing-page.png)


### How PDF is compressed in backend:
```python
import os
import sys
from PDFNetPython3.PDFNetPython import PDFDoc, Optimizer, SDFDoc, PDFNet

def compress_file(input_file: str, output_file: str):
    if not output_file:
        output_file = input_file
    try:
        PDFNet.Initialize()
        doc = PDFDoc(input_file)
        doc.InitSecurityHandler()
        Optimizer.Optimize(doc)
        doc.Save(output_file, SDFDoc.e_linearized)
        doc.Close()
    except Exception as e:
        doc.Close()
        return False
    return True

if __name__ == "__main__":
    input_file = sys.argv[1]
    output_file = sys.argv[2]
    compress_file(input_file, output_file)
```



## 🤔 How to contribute

-[x] Fork this repository;
-[x] Create a branch with your feature: `git checkout -b my-feature`;
-[x] Commit your changes: `git commit -m "feat: my new feature"`;
-[x] Push to your branch: `git push origin my-feature`.

Daftar Kata diekstrak dari xml.bz2 file (<LANG>wiki-latest-pages-articles.xml.bz2) wikimedia [https://dumps.wikimedia.org/idwiki/latest/]


```python
#load dataset
import pandas as pd
df = pd.read_csv('datasetnya')

#load daftar kata
file_path = 'file path'
with open(file_path, 'r') as file:
  daftar_kata = file.read()

#buat kolom kata yang tidak standar
def extract_unknown_words(text, list_kata):
  tokens = text.split()
  unknown_words = [word for word in tokens if word not in list_kata]
  return ' '.join(unknown_words)

df['unknown_words'] = df['text'].apply(lambda x: extract_unknown_words(x, list_kata))
```

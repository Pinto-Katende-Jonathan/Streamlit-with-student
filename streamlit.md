# Les bases de Streamlit

### Installation de Streamlit via cmd
```pip install streamlit```

### Tester streamlit via cmd
```streamlit hello```

### Les inputs de base
Parmi les inputs, nous avons :

- checkbox
- button
- selectbox
- slider
- radio
- time_input
- ...

## 1. Basiques
---
### Partie 1
```python
import streamlit as st

# Titre
st.title("Mon titre")

# Header
st.header("Header")

# Sub-Header
st.subheader("Sous titre")

# Information
st.info("Une information classique")

# Avertissement
st.warning("Attention")

# Erreur
st.error("Erreur")

# Toast
st.toast('Mr Stay-Puft')

# Succès
st.success("Envoyé avec succès")

# Pour Ecrire le markdown
st.write("Hello Markdown")
st.write("""
    # Titre dans le markdown
    **Bold in Markdown**
    ---
""")

# Markdown avec possiblité du Html
st.markdown("<h1>Hi Html in Markdown</h1>")

# Texte
st.text("Welcome")

# caption
st.caption("Caption test")

# Math
st.latex(r''' delta = b^2 - 4ac''')

# code
st.code('for i in range(8): foo()')
```

### Partie 2
```python
#image
st.image("img.png")
st.audio(data)
st.video(data) 
```
Idem pour les vidéos et les audios.

#### Les inputs
```python
# checkbox
st.checkbox("Accepter")

# Button
st.button("click")

# radio
st.radio("Genre", ["masculin", "feminin","neutre"])

# selectbox
st.selectbox("Genre", ["masculin", "feminin","neutre"])

# Multiselect
st.multiselect("Genre", ["masculin", "feminin","neutre"])

# slider (str, min, max, step)
st.slider("Genre", 0, 10, 2)

# select_slider
st.radio("Niveau", ["Primaire", "secondaire","supérieur"])

# nombre
st.number_input("choisi un nombre", 0, 12)

# Text
st.text_input("Entre un text")

# Textarea
st.text_area("Entre un commentaire")

# Date
st.date_input("choisi une date")

# Temps
st.time_input("Entre une date")

# Fichier
st.file_upload('Drag and drop')

# Color Picker
st.color_picker('color')

# Progress Bar
st.progress(90)

# Loader
st.spinner("Chargement...")

# Ballons
st.balloons()

# Snow
st.snow()

# Camera
st.camera_input("一二三,茄子!")
```

### Sidebar

Pour la sidebar, tous les champs sont identiques aux précédents, à la seule condition de précéder par ```st.sidebar.```

**Cas d'utilisation**

```python

# Sidebar title
st.sidebar.title("Bienvenue sur la sidebar")

st.sidebar.text_input("Sidebar text input")
st.sidebar.button("click")
# ...
```

```python
# Exemple 1
# ------------------------------
button1 = st.button("Envoyez")

if button1:
    st.write("Hello streamlit")

#-------------------------------

# Exemple 2
#-------------------------------
pref = st.checkbox("Aimez-vous python?")
button2 = st.button("Test")

if button2:
    st.write(pref)
#-------------------------------

# Exemple 3
#-------------------------------
if button2:
    if pref:
        st.write("J\'aime Python")
    else:
        st.write("Pas du tout")
#-------------------------------

# Exemple 4
#-------------------------------
radio = st.radio("Statut", ["M.", "Mme"], "Mme")

button = st.button("Test")

if button:
    if radio == "M.":
        st.write("Bonjour Monsieur")
    else:
        st.write("Bonjour Madame")
#-------------------------------

# Exemple 5
#-------------------------------
langages = st.multiselect("Quel langage avez-vous déjà utililisé?", ["PHP", "Python", "Ruby", "R", "Javascrit", "Html", "CSS"])

if st.button("Click"):
    langages
    st.write(langages[0])
#-------------------------------
```

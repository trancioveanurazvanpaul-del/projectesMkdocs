# Práctica 2: Fork y Pull Request

## Aplicaciones Web

---

### 1. Clonar el repositorio
Lo primero que tendríamos que hacer sería copiar (fork/clonar) el repositorio del profesor:

```bash
razvan@razvan-VirtualBox:~/razvan-iaw$ git clone https://github.com/trancioveanu/razvanpaul-del/exercici4
Clonando en 'exercici4'...
remote: Enumerating objects: 79, done.
remote: Counting objects: 100% (79/79), done.
remote: Compressing objects: 100% (63/63), done.
remote: Total 79 (delta 14), reused 59 (delta 11), pack-reused 0 (from 0)
Recibiendo objetos: 100% (79/79), 168.92 KiB | 1.21 MiB/s, listo.
Resolviendo deltas: 100% (14/14), listo.
razvan@razvan-VirtualBox:~/razvan-iaw$ 
```

---

### 2. Creación de una rama propia
Creamos una rama con mis iniciales (`rzv`):

```bash
razvan@razvan-VirtualBox:~$ cd razvan-iaw/
razvan@razvan-VirtualBox:~/razvan-iaw$ git checkout -b rzv
Cambiado a nueva rama 'rzv'
razvan@razvan-VirtualBox:~/razvan-iaw$ 
```

---

### 3. Creación de un fichero personal
Creo un fichero dentro de la carpeta `files`:

```text
GNU nano 8.7.1                        razvan *                   

Hola soy razvan
2 asix
22/9/2026
```

---

### 4. Modificación del README.md
Modificamos el archivo `README.md` apuntando a nuestro nuevo fichero:

```bash
razvan@razvan-VirtualBox:~/exercici4$ cat README.md
* [ABC](files/razvan)
# exercici4
## Marc Brines
- [FranSG](files/imgF.jpg)

Practica 2 fent fork
- [mvb](files/mvb.md)
- [Iker Patiño](files/perromolon.jpg)
- [DPD](files/dpd.md)
- [XGF](files/xgf.md)
- [Jonman Jimenez Mendoza](files/JJM.md)
- [Jesus Alvarez Olmo](files/jao.md)

razvan@razvan-VirtualBox:~/exercici4$ 
```

---

### 5. Confirmación de los cambios
Validamos y guardamos los cambios realizados localmente:

```bash
razvan@razvan-VirtualBox:~/exercici4$ git add .
razvan@razvan-VirtualBox:~/exercici4$ git commit -m "Nuevos cambios"
[main 762f998] Nuevos cambios
 2 files changed, 4 insertions(+)
 create mode 100644 files/razvan
razvan@razvan-VirtualBox:~/exercici4$ git push origin rzv
```
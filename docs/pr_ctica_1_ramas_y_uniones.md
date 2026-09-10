# Práctica 1: Ramas y uniones

## Aplicaciones Web

---

## ÍNDICE
* Práctica ramas

---

## Práctica ramas

### 1. Creación y verificación de rama
Creamos una rama y verificamos que se haya creado correctamente:

```bash
razvan@razvan-VirtualBox:~/razvan-iaw/pruebaRazvan$ git branch
* primera
```

---

### 2. Creación de fichero y cambio de rama
Creamos el fichero y posteriormente cambiamos de rama:

```bash
razvan@razvan-VirtualBox:~/razvan-iaw/pruebaRazvan$ echo "Fichero nuevo" > fichero1.txt
razvan@razvan-VirtualBox:~/razvan-iaw/pruebaRazvan$ git add fichero1.txt
razvan@razvan-VirtualBox:~/razvan-iaw/pruebaRazvan$ git commit "En nuevo fichero en la rama primera"
error: ruta especificada 'En nuevo fichero en la rama primera' no concordó con ningún archivo conocido por git
razvan@razvan-VirtualBox:~/razvan-iaw/pruebaRazvan$ git commit -m "El nuevo fichero en la rama primera"
[primera 5d83ef1] El nuevo fichero en la rama primera
 1 file changed, 1 insertion(+)
 create mode 100644 fichero1.txt
razvan@razvan-VirtualBox:~/razvan-iaw/pruebaRazvan$ git checkout main
Cambiado a rama 'main'
```

---

### 3. Fusión de rama
Intentamos fusionar la rama `primera` en `main`:

```bash
razvan@razvan-VirtualBox:~/razvan-iaw/pruebaRazvan$ git checkout main
Cambiado a rama 'main'
razvan@razvan-VirtualBox:~/razvan-iaw/pruebaRazvan$ git merge primera
Ya está actualizado.
```

---

### 4. Eliminación de rama
Eliminamos la rama `primera`:

```bash
razvan@razvan-VirtualBox:~/razvan-iaw/pruebaRazvan$ git branch -d primera
Eliminada la rama primera (era 5d83ef1).
```

---

### 5. Creación de segunda rama y archivo en main
Creamos la segunda rama (`segona`) y un fichero inicial para la rama `main`:

```bash
razvan@razvan-VirtualBox:~/razvan-iaw/pruebaRazvan$ echo "Linea nueva" > exemple.txt
razvan@razvan-VirtualBox:~/razvan-iaw/pruebaRazvan$ git add exemple.txt
razvan@razvan-VirtualBox:~/razvan-iaw/pruebaRazvan$ git commit -m "Fichero inicial a main"
[main aaaa6d8] Fichero inicial a main
 1 file changed, 1 insertion(+)
 create mode 100644 exemple.txt
razvan@razvan-VirtualBox:~/razvan-iaw/pruebaRazvan$ git checkout -b segona
Cambiado a nueva rama 'segona'
```

---

### 6. Modificación en la segunda rama
Modificamos el contenido desde la rama `segona`:

```bash
razvan@razvan-VirtualBox:~/razvan-iaw/pruebaRazvan$ echo "linea modificada" > exemple.txt
razvan@razvan-VirtualBox:~/razvan-iaw/pruebaRazvan$ git add exemple.txt
razvan@razvan-VirtualBox:~/razvan-iaw/pruebaRazvan$ git commit -m "Cambio a la rama segunda"
[segona 48737a4] Cambio a la rama segunda
 1 file changed, 1 insertion(+)
```

---

### 7. Generación del conflicto de fusión
Modificamos el mismo fichero desde la rama `main` y realizamos el merge para provocar un conflicto:

```bash
razvan@razvan-VirtualBox:~/razvan-iaw/pruebaRazvan$ git checkout main
Cambiado a rama 'main'
razvan@razvan-VirtualBox:~/razvan-iaw/pruebaRazvan$ echo "Linea modificada desde main" > exemple.txt
razvan@razvan-VirtualBox:~/razvan-iaw/pruebaRazvan$ git add exemple.txt
razvan@razvan-VirtualBox:~/razvan-iaw/pruebaRazvan$ git commit -m "Cambio main"
[main 333f482] Cambio main
 1 file changed, 1 insertion(+), 1 deletion(-)
razvan@razvan-VirtualBox:~/razvan-iaw/pruebaRazvan$ get merge segona
Orden «get» no encontrada, pero hay 16 similares.
razvan@razvan-VirtualBox:~/razvan-iaw/pruebaRazvan$ git merge segona
Auto-fusionando exemple.txt
CONFLICTO (contenido): Conflicto de fusión en exemple.txt
Fusión automática falló; arregle los conflictos y luego realice un commit con el resultado.
```

---

### 8. Edición del conflicto
En el fichero `exemple.txt` borramos las marcas del conflicto (`<<<<<<<`, `=======`, `>>>>>>>`):

```text
GNU nano 8.7.1                        exemple.txt *

HEAD
Linea modificada desde main

linea modificada
segona
```

---

### 9. Resolución del conflicto
Comprobamos y solucionamos la resolución guardando el cambio e intentando el commit de nuevo en `main`:

```bash
razvan@razvan-VirtualBox:~/razvan-iaw/pruebaRazvan$ git add exemple.txt
razvan@razvan-VirtualBox:~/razvan-iaw/pruebaRazvan$ git commit -m "Solucionamos el problema"
[main 00470b0] Solucionamos el problema
```
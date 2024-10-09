# Hashcat: Descifrado de Contraseñas

**Hashcat** es una herramienta de descifrado de contraseñas mediante ataques de fuerza bruta o diccionario, y permite trabajar con múltiples algoritmos de hash.

## Pasos para descifrar un hash

### 1. Obtener el hash cifrado

Primero, debes tener el código hash cifrado que deseas descifrar. Este hash puede haber sido extraído de alguna base de datos, archivo, etc.

### 2. Guardar el hash en un archivo

Crea un archivo de texto donde se guardará el hash cifrado. Por ejemplo, puedes usar `hash.txt` para este propósito.

```bash
echo "HASH_CIFRADO" > hash.txt
```

### 3. Identificar el tipo de cifrado del hash
Hashcat permite identificar el tipo de hash usando el siguiente comando:

hashcat --identify hash.txt

### 4. Descifrar el hash

Una vez identificado el tipo de cifrado, puedes proceder a descifrar el hash. En este caso, si el hash es de tipo MD5, debes usar el siguiente comando:

hashcat -a 0 -m 0 hash.txt diccionario.txt

### 5. Mostrar el resultado descifrado

Para mostrar el resultado del descifrado:

hashcat -a 0 -m 0 hash.txt diccionario.txt --show

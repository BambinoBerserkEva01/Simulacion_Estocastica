# LFSR MultiDegree y Operaciones en F₂

Este documento proporciona la documentación detallada para los módulos:

- **LFSR_MultiDegree.py**: Implementación optimizada de LFSR para grados 4, 8, 12, 16 y 20.
- **F2_Operations.py**: Operaciones en el cuerpo finito F₂, incluyendo matrices y conversiones.

## 1. LFSR_MultiDegree.py

### Descripción
Este módulo proporciona una implementación genérica y optimizada de un **Registro de Desplazamiento de Retroalimentación Lineal (LFSR)** en el cuerpo F₂, permitiendo la generación de secuencias pseudoaleatorias.

### Características
- Implementación modular para cualquier grado de LFSR.
- Uso de una **matriz de realimentación** para actualizar el estado.
- Conversión entre **representaciones binarias y enteras**.
- Permite definir polinomios de realimentación personalizados.

### Uso
```python
from LFSR_MultiDegree import LFSR

# Definir un LFSR de 8 bits con semilla 1 y taps adecuados
lfsr8 = LFSR(degree=8, seed=1, taps=[0, 2, 3, 4, 7])
numbers = lfsr8.generate_numbers(8)
print("LFSR 8-bit output:", numbers)
```

### Polinomios de Realimentación Implementados
| Grado | Polinomio |
|-------|------------------|
| 4     | x⁴ + x³ + 1 |
| 8     | x⁸ + x⁶ + x⁵ + x⁴ + 1 |
| 12    | x¹² + x¹¹ + x⁸ + x⁶ + 1 |
| 16    | x¹⁶ + x¹⁴ + x¹³ + x¹¹ + 1 |
| 20    | x²⁰ + x¹⁷ + 1 |

---

## 2. F2_Operations.py

### Descripción
Este módulo proporciona funciones esenciales para trabajar con **matrices y vectores en F₂**, útiles para criptografía y teoría de códigos.

### Funciones Implementadas

#### 1. Conversión entre decimal y binario en F₂
```python
def decimal_a_binario(n: int, k: int = None) -> str:
    """Convierte un número decimal a binario con longitud fija k."""
```

#### 2. Conversión de cadena binaria a vector en F₂
```python
def binario_a_f2(bin_str: str) -> np.ndarray:
    """Convierte una cadena binaria a un vector de valores en F₂."""
```

#### 3. Generación de matriz en F₂
```python
def matriz_f2(k: int) -> np.ndarray:
    """Genera una matriz aleatoria de tamaño k x k en F₂."""
```

#### 4. Multiplicación de matrices en F₂
```python
def multiplicar_matrices_f2(A: np.ndarray, B: np.ndarray) -> np.ndarray:
    """Multiplica dos matrices en el cuerpo F₂ utilizando operaciones XOR."""
```

#### 5. Cálculo de la inversa de una matriz en F₂
```python
def inversa_matriz_f2(A: np.ndarray) -> np.ndarray:
    """Calcula la inversa de una matriz en F₂ si existe."""
```

#### 6. Conversión de lista de números a matriz en F₂
```python
def lista_a_matriz_f2(lista: list, k: int) -> np.ndarray:
    """Convierte una lista de números en una matriz de tamaño k x k en F₂."""
```

### Uso
```python
from F2_Operations import matriz_f2, multiplicar_matrices_f2

# Crear dos matrices en F₂ y multiplicarlas
M1 = matriz_f2(4)
M2 = matriz_f2(4)
resultado = multiplicar_matrices_f2(M1, M2)
```

---

## Conclusión
Estos dos módulos proporcionan una implementación modular y clara para el uso de **LFSR y operaciones en F₂**, permitiendo aplicaciones en criptografía, simulaciones y generación de secuencias pseudoaleatorias. 🚀

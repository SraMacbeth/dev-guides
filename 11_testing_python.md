Guía de pruebas unitarias en Python

Objetivo

Construir tests confiables y profesionales.

---

Estructura recomendada

project/
├── app/
├── tests/
├── test_data/

---

Archivo de configuración de DB de prueba

test_db_setup.py

Responsabilidades:

- crear tablas
- limpiar datos
- destruir DB temporal

---

Ruta dinámica

BASE_DIR = os.path.dirname(
    os.path.abspath(__file__)
)

---

Crear conexión

sqlite3.connect(TEST_DB)

---

Métodos importantes

create_tables()

Crea estructura inicial.

---

clear_tables()

Borra datos.
No elimina tablas.

---

drop_database()

Elimina el archivo ".db" completo.

---

setUp y tearDown

setUp()

Se ejecuta antes de cada test.

Ideal para:

- limpiar DB
- insertar datos base

---

tearDown()

Se ejecuta después.

Ideal para:

- cerrar conexiones
- borrar temporales

---

AAA Pattern

Arrange

Preparar datos.

---

Act

Ejecutar acción.

---

Assert

Verificar resultado.

---

Ejemplo

def test_get_book():
    # Arrange
    Book.add_book(...)

    # Act
    result = Book.get_book_by_id(1)

    # Assert
    self.assertIsNotNone(result)

---

Assertions importantes

Las assertions permiten verificar si el resultado obtenido coincide con el esperado.

Son la parte más importante del test porque determinan si la prueba:

- pasa
- falla

---

assertEqual()

Verifica que dos valores sean iguales.

Sintaxis

self.assertEqual(valor_esperado, valor_obtenido)

Ejemplo

def test_suma():
    resultado = 2 + 2
    self.assertEqual(4, resultado)

Cuándo usarlo

Muy útil para:

- números
- strings
- listas
- resultados de funciones
- consultas SQL

---

assertTrue()

Verifica que el valor sea "True".

Sintaxis

self.assertTrue(condicion)

Ejemplo

def test_usuario_activo():
    usuario_activo = True
    self.assertTrue(usuario_activo)

Cuándo usarlo

Útil para:

- validaciones booleanas
- condiciones
- verificaciones simples

---

assertFalse()

Verifica que el valor sea "False".

Sintaxis

self.assertFalse(condicion)

Ejemplo

def test_usuario_bloqueado():
    usuario_bloqueado = False
    self.assertFalse(usuario_bloqueado)

Cuándo usarlo

Útil para:

- permisos
- validaciones negativas
- estados desactivados

---

assertIsNone()

Verifica que el valor sea "None".

Sintaxis

self.assertIsNone(valor)

Ejemplo

def test_busqueda_inexistente():
    resultado = None
    self.assertIsNone(resultado)

Cuándo usarlo

Muy útil cuando:

- una búsqueda no encuentra resultados
- una función devuelve "None"
- un dato no existe

---

assertIsNotNone()

Verifica que el valor NO sea "None".

Sintaxis

self.assertIsNotNone(valor)

Ejemplo

def test_get_book():
    resultado = Book.get_book_by_id(1)
    self.assertIsNotNone(resultado)

Cuándo usarlo

Útil para verificar:

- resultados de consultas
- objetos creados
- datos encontrados en DB

---

assertRaises()

Verifica que una función genere una excepción específica.

Sintaxis

with self.assertRaises(TipoError):
    funcion()

Ejemplo

def test_division():
    with self.assertRaises(ZeroDivisionError):
        10 / 0

Cuándo usarlo

Muy importante para:

- validar errores
- testing defensivo
- manejo de excepciones

---

assertIn()

Verifica que un valor exista dentro de otro.

Sintaxis

self.assertIn(valor, coleccion)

Ejemplo

def test_nombre():
    usuarios = ["Ana", "Luis", "Pedro"]
    self.assertIn("Ana", usuarios)

Cuándo usarlo

Útil para:

- listas
- diccionarios
- strings
- resultados SQL

---

assertNotIn()

Verifica que un valor NO exista.

Ejemplo

def test_usuario():
    usuarios = ["Ana", "Luis"]
    self.assertNotIn("Carlos", usuarios)

---

assertGreater()

Verifica que un valor sea mayor que otro.

Ejemplo

def test_stock():
    stock = 10
    self.assertGreater(stock, 0)

---

assertLess()

Verifica que un valor sea menor que otro.

Ejemplo

def test_limite():
    intentos = 2
    self.assertLess(intentos, 5)

---

Ejecutar tests

Archivo específico

python3 -m unittest discover -v -s tests -p "test_book_model.py" -t .

---

Todos los tests

python3 -m unittest discover -v

---

Detener en primer error

python3 -m unittest discover -v -f

---

Qué analizar cuando falla

AssertionError

La lógica es incorrecta.

---

NameError

Variable mal escrita.

---

OperationalError

Problema SQL o estructura.

---

Reglas profesionales

Los tests deben ser:

Independientes

Uno no depende de otro.

---

Deterministas

Deben dar el mismo resultado siempre.

---

Rápidos

No depender de internet o APIs reales.

---

Filosofía importante

Las assertions deben verificar:

- comportamiento esperado
- reglas importantes
- resultados críticos

No tiene sentido testear:

- cosas triviales
- comportamiento obvio de Python

La prioridad debe ser validar:

- lógica del proyecto
- reglas de negocio
- casos límite
- errores frecuentes

---

Qué valoran en entrevistas junior

Aunque el proyecto sea pequeño,
tener tests transmite:

- disciplina
- profesionalismo
- pensamiento estructurado
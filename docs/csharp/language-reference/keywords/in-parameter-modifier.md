---
title: 'Modificador del parámetro in: Referencia de C#'
ms.date: 03/26/2019
helpviewer_keywords:
- parameters [C#], in
- in parameters [C#]
ms.openlocfilehash: 10e7b91f9a6bf280c5f0654b243492bac8cde1e0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715253"
---
# <a name="in-parameter-modifier-c-reference"></a>Modificador del parámetro in (referencia de C#)

La palabra clave `in` hace que los argumentos se pasen por referencia. Hace que el parámetro formal sea un alias para el argumento, que debe ser una variable. En otras palabras, cualquier operación en el parámetro se realiza en el argumento. Es como las palabras clave [ref](ref.md) o [out](out-parameter-modifier.md), salvo que el método al que se llama no puede modificar los argumentos `in`. Mientras que los argumentos `ref` se pueden modificar, el método llamado debe modificar los argumentos `out` y esas modificaciones se pueden observar en el contexto de la llamada.

[!code-csharp-interactive[cs-in-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/InParameterModifier.cs#1)]  

En el ejemplo anterior se muestra que el modificador `in` no suele ser necesario en el sitio de llamada, sino que solo lo es en la declaración del método.

> [!NOTE] 
> Además, la palabra clave `in` puede usarse con un parámetro de tipo genérico para especificar que el parámetro de tipo es contravariante, parte de una instrucción `foreach` o de una cláusula `join` de una consulta de LINQ. Para más información sobre el uso de la palabra clave `in` en esos contextos, vea [in](in.md), que además incluye vínculos a todos estos usos.
  
Las variables que se han pasado como argumentos `in` deben inicializarse antes de pasarse en una llamada de método. Sin embargo, es posible que el método llamado no asigne ningún valor o modifique el argumento.  

El modificador de parámetro `in` está disponible en C# 7.2 y versiones posteriores. Las versiones anteriores generan el error del compilador `CS8107` ("Feature 'readonly references' is not available in C# 7.0. Please use language version 7.2 or greater.") (La característica "readonly references" no está disponible en C# 7.0. Use la versión de lenguaje 7.2 o superior"). Para configurar la versión del lenguaje de compilador, vea [Seleccionar la versión del lenguaje C#](../configure-language-version.md).

Las palabras clave `in`, `ref` y `out` no se consideran parte de la firma del método con el fin de resolver la sobrecarga. Por lo tanto, los métodos no pueden sobrecargarse si la única diferencia es que un método toma un argumento `ref` o `in` y el otro toma un argumento `out`. Por ejemplo, el código siguiente, no se compilará:  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on in, ref and out".
    public void SampleMethod(in int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
Está permitida la sobrecarga en función de la presencia de `in`:  
  
```csharp
class InOverloads
{
    public void SampleMethod(in int i) { }
    public void SampleMethod(int i) { }
}
```

## <a name="overload-resolution-rules"></a>Reglas de resolución de sobrecarga

Puede comprender las reglas de resolución de sobrecarga de métodos por valor frente a argumentos `in` mediante la comprensión de la motivación de argumentos `in`. Definir métodos usando parámetros `in` es una optimización del rendimiento potencial. Algunos argumentos de tipo `struct` pueden tener un gran tamaño y, cuando se llama a métodos en bucles de pequeñas dimensiones o rutas de acceso de código crítico, el costo de copiar esas estructuras resulta crucial. Los métodos declaran parámetros `in` para especificar qué argumentos pueden pasarse por referencia sin ningún riesgo porque el método llamado no modifica el estado de ese argumento. Al pasar esos argumentos por referencia se evita la copia (potencialmente) costosa. 

Especificar `in` en argumentos en el sitio de llamada suele ser opcional. No hay ninguna diferencia semántica entre pasar argumentos por valor y pasarlos por referencia mediante el modificador `in`. El modificador `in` en el sitio de llamada es opcional porque no es necesario indicar que podría cambiarse el valor del argumento. Se agrega explícitamente el modificador `in` en el sitio de llamada para garantizar que el argumento se pasa por referencia, y no por valor. Usar explícitamente `in` tiene los dos efectos siguientes:

El primero es que, al especificar `in` en el sitio de llamada, se fuerza al compilador a seleccionar un método definido con un parámetro `in` coincidente. En caso contrario, cuando dos métodos se diferencian solo en presencia de `in`, la sobrecarga por valor es una coincidencia mejor.

El segundo es que, al especificar `in` declara su intención para pasar un argumento por referencia. Los argumentos usados con `in` deben representar una ubicación a la que se pueda hacer referencia directamente. Se aplican las mismas reglas generales para los argumentos `out` y `ref`: no se pueden usar constantes, propiedades normales u otras expresiones que produzcan valores. En caso contrario, si se omite `in` en el sitio de llamada, se informa al compilador de que le permitirá crear una variable temporal para pasar por referencia de solo lectura para el método. El compilador crea una variable temporal para superar varias restricciones con argumentos `in`:

- Una variable temporal permite constantes en tiempo de compilación como parámetros `in`.
- Una variable temporal permite propiedades u otras expresiones para parámetros `in`.
- Una variable temporal permite argumentos en los que hay una conversión implícita desde el tipo de argumento hacia el tipo de parámetro.

En todas las instancias anteriores, el compilador crea una variable temporal que almacena el valor de la constante, la propiedad u otra expresión.

Estas reglas se muestran en este código:

```csharp
static void Method(in int argument)
{
    // implementation removed
}

Method(5); // OK, temporary variable created.
Method(5L); // CS1503: no implicit conversion from long to int
short s = 0;
Method(s); // OK, temporary int created with the value 0
Method(in s); // CS1503: cannot convert from in short to in int
int i = 42;
Method(i); // passed by readonly reference
Method(in i); // passed by readonly reference, explicitly using `in`
```

Supongamos ahora que hay disponible otro método que usa argumentos por valor. Los resultados cambian como se muestra en este código:

```csharp
static void Method(int argument)
{
    // implementation removed
}

static void Method(in int argument)
{
    // implementation removed
}

Method(5); // Calls overload passed by value
Method(5L); // CS1503: no implicit conversion from long to int
short s = 0;
Method(s); // Calls overload passed by value.
Method(in s); // CS1503: cannot convert from in short to in int
int i = 42;
Method(i); // Calls overload passed by value
Method(in i); // passed by readonly reference, explicitly using `in`
```

La única llamada de método donde se pasa el argumento por referencia es la última.

> [!NOTE]
> El código anterior usa `int` como el tipo de argumento para simplificar el trabajo. Como `int` no es más grande que una referencia en la mayoría de máquinas modernas, no supone ninguna ventaja pasar un único `int` como una referencia de solo lectura. 

## <a name="limitations-on-in-parameters"></a>Limitaciones de los parámetros `in`

Las palabras clave `in`, `ref` y `out` no pueden usarse para estos tipos de métodos:  
  
- Métodos asincrónicos, que se definen mediante el uso del modificador [async](async.md).  
- Métodos de iterador, que incluyen una instrucción [yield return](yield.md) o `yield break`.  

## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Parámetros de métodos](method-parameters.md)
- [Escritura de código seguro y eficaz](../../write-safe-efficient-code.md)

---
title: Semántica de referencia con tipos de valor
description: Conozca las características del lenguaje que reducen al mínimo la copia de las estructuras de manera segura.
author: billwagner
ms.author: wiwagn
ms.date: 11/10/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 8a0cfe83200d50eefa9b01ab51591a5fe0703ec0
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
---
# <a name="reference-semantics-with-value-types"></a>Semántica de referencia con tipos de valor

Una ventaja de utilizar tipos de valor es que a menudo evitan las asignaciones del montón.
La desventaja correspondiente es que se copian por valor. Este último aspecto dificulta la optimización de los algoritmos que funcionan en grandes cantidades de datos. Las nuevas características del lenguaje en C# 7.2 proporcionan mecanismos que habilitan la semántica de paso por referencia con tipos de valor. Si utiliza estas características acertadamente puede minimizar tanto las asignaciones como las operaciones de copia. En este artículo se exploran estas nuevas características.

Gran parte del código de ejemplo de este artículo muestra características agregadas en C# 7.2. Para poder usar esas características, tendrá que configurar el proyecto para que utilice C# 7.2 o una versión posterior en el proyecto. Puede usar Visual Studio para seleccionarlo. Para cada proyecto, seleccione **Proyecto** en el menú y, a continuación, **Propiedades**. Seleccione la pestaña **Compilar** y haga clic en **Opciones avanzadas**. Ahí podrá configurar la versión de lenguaje. Elija "7.2", o "más reciente".  O puede editar el proyecto *csproj* y agregar el nodo siguiente:

```XML
  <PropertyGroup>
    <LangVersion>7.2</LangVersion>
  </PropertyGroup>
```

Puede usar "7.2" o "más reciente" como valor.

## <a name="specifying-in-parameters"></a>Especificación de parámetros `in`

C# 7.2 agrega la palabra clave `in` para complementar las palabras clave `ref` y `out` existentes al escribir un método que pasa argumentos por referencia. La palabra clave `in` especifica que está pasando el parámetro por referencia y el método llamado no modifica el valor que se le pasa. 

Esta novedad proporciona un vocabulario completo para expresar la intención del diseño. Los tipos de valor se copian al pasarlos a un método llamado cuando no se especifica ninguno de los siguientes modificadores. Cada uno de estos modificadores especifica que un tipo de valor se pasa por referencia, evitando la copia. Cada modificador expresa un propósito diferente:

- `out`: este método establece el valor del argumento utilizado como este parámetro.
- `ref`: este método puede establecer el valor del argumento utilizado como este parámetro.
- `in`: este método no modifica el valor del argumento utilizado como este parámetro.

Cuando se agrega el modificador `in` para pasar un argumento por referencia, se declara que la intención del diseño consiste en pasar argumentos por referencia para evitar la copia innecesaria. No pretende modificar el objeto usado como ese argumento. El código siguiente muestra un ejemplo de un método que calcula la distancia entre dos puntos en un espacio 3D. 

[!code-csharp[InArgument](../../samples/csharp/reference-semantics/Program.cs#InArgument "Specifying an In argument")]

Los argumentos son dos estructuras que contienen cada una de ellas tres valores dobles. Un valor doble tiene 8 bytes, por lo que cada argumento es de 24 bytes. Al especificar el modificador `in`, se pasa una referencia de 4 bytes o 8 bytes a esos argumentos, dependiendo de la arquitectura de la máquina. La diferencia de tamaño es pequeña; sin embargo, puede crecer rápidamente cuando la aplicación llama a este método en un bucle ajustado con muchos valores diferentes.
 
El modificador `in` complementa también a `out` y `ref` de otras maneras. No puede crear sobrecargas de un método que difiere solo en cuanto a la presencia de `in`, `out` o `ref`. Estas nuevas reglas extienden el mismo comportamiento que siempre se ha definido para los parámetros `out` y `ref`.

El modificador `in` se puede aplicar a cualquier miembro que toma parámetros: métodos, delegados, expresiones lambda, funciones locales, indexadores u operadores.

A diferencia de los argumentos `ref` y `out`, puede usar los valores literales o constantes para el argumento en un parámetro `in`. Además, a diferencia de un parámetro `ref` o `out`, no es necesario aplicar el modificador `in` en el sitio de llamada. El código siguiente muestra dos ejemplos de llamada al método `CalculateDistance`. El primero usa dos variables locales pasadas por referencia. El segundo incluye una variable temporal creada como parte de la llamada al método. 

[!code-csharp[UseInArgument](../../samples/csharp/reference-semantics/Program.cs#UseInArgument "Specifying an In argument")]

El compilador tiene varias maneras de asegurarse de que se aplica la naturaleza de solo lectura de un argumento `in`.  En primer lugar, el método llamado no se puede asignar directamente a un parámetro `in`. No se puede asignar directamente a ningún campo de un parámetro `in`. Además, no puede pasar un parámetro `in` a ningún método que exija el modificar `ref` o `out`.
El compilador exige que el argumento `in` sea una variable de solo lectura. Puede llamar a cualquier método de instancia que utilice la semántica de paso por valor. En esos casos, se crea una copia del parámetro `in`. Dado que el compilador puede crear una variable temporal para cualquier parámetro `in`, también puede especificar valores predeterminados para cualquier parámetro `in`. El código siguiente utiliza esto para especificar el origen (punto 0,0) como valor predeterminado para el segundo punto:

[!code-csharp[InArgumentDefault](../../samples/csharp/reference-semantics/Program.cs#InArgumentDefault "Specifying defaults for an in parameter")]

La designación del parámetro `in` también se puede usar con tipos de referencia o integrarse en valores numéricos. Sin embargo, las ventajas de ambos casos son mínimas, si las hay.

## <a name="ref-readonly-returns"></a>Devoluciones de `ref readonly`

También puede querer devolver un tipo de valor por referencia, pero no permitir que el llamador modifique ese valor. Use el modificador `ref readonly` para expresar la intención del diseño. Esto notifica a los lectores que devuelve una referencia a los datos existentes, pero no permite la modificación. 

El compilador exige que el llamador no pueda modificar la referencia. Los intentos de asignar al valor directamente generan un error en tiempo de compilación. Sin embargo, el compilador no puede saber si algún método de miembro modifica el estado de la estructura.
Para asegurarse de que el objeto no se modifica, el compilador crea una copia y llama a las referencias de miembro usando esa copia. Las modificaciones se realizan sobre esa copia defensiva. 

Es probable que la biblioteca con `Point3D` utilice a menudo el origen en todo el código. Cada instancia crea un nuevo objeto en la pila. Puede ser conveniente crear una constante y devolverla por referencia. Sin embargo, si se devuelve una referencia al almacenamiento interno, es posible que desee exigir que el llamador no pueda modificar el almacenamiento al que se hace referencia. El código siguiente define una propiedad de solo lectura que devuelve `readonly ref` a `Point3D` que especifica el origen.

[!code-csharp[OriginReference](../../samples/csharp/reference-semantics/Point3D.cs#OriginReference "Creating a readonly Origin reference")]

La creación de una copia de una devolución de solo lectura de referencia es fácil: basta con asignarla a una variable no declarada con el modificador `ref readonly`. El compilador genera código para copiar el objeto como parte de la asignación. 

Al asignar una variable a `ref readonly return`, puede especificar una variable `ref readonly` o una copia por valor de la referencia de solo lectura:

[!code-csharp[AssignRefReadonly](../../samples/csharp/reference-semantics/Program.cs#AssignRefReadonly "Assigning a ref readonly")]

La primera asignación en el código anterior realiza una copia de la constante `Origin` y asigna esa copia. La segunda asigna una referencia. Tenga en cuenta que el modificador `readonly` debe formar parte de la declaración de la variable. No se puede modificar la referencia a la que alude. Los intentos de hacerlo generarán un error en tiempo de compilación.

## <a name="readonly-struct-type"></a>Tipo de `readonly struct`

La aplicación de `ref readonly` a usos de tráfico elevado de una estructura puede ser suficiente.
En otras ocasiones, quizá desee crear una estructura inmutable. Así puede pasar siempre por referencia de solo lectura. Esa práctica quita las copias defensivas que tienen lugar cuando se tiene acceso a métodos de una estructura que se utiliza como un parámetro `in`.

Puede hacerlo mediante la creación de un tipo `readonly struct`. Puede agregar el modificador `readonly` en una declaración de estructura. El compilador exige que todos los miembros de instancia de la estructura sean `readonly`; `struct` debe ser inmutable.

Hay otras optimizaciones para `readonly struct`. Puede usar el modificador `in` en todas las ubicaciones donde `readonly struct` es un argumento. Además, puede devolver `readonly struct` como `ref return` cuando devuelva un objeto cuya duración se extiende más allá del ámbito del método que devuelve del objeto.

Por último, el compilador genera código más eficaz cuando se llama a los miembros de `readonly struct`: la referencia `this`, en lugar de una copia del receptor, siempre es un parámetro `in` pasado por referencia al método de miembro. Esta optimización ahorra más procesos de copia cuando utiliza `readonly struct`. Este valor `Point3D` es un excelente candidato para este cambio. El código siguiente muestra una estructura actualizada de `ReadonlyPoint3D`:

[!code-csharp[ReadonlyOnlyPoint3D](../../samples/csharp/reference-semantics/Point3D.cs#ReadonlyOnlyPoint3D "Defining an immutable structure")]

## <a name="ref-struct-type"></a>Tipo de `ref struct`

Otra característica de lenguaje relacionada es la capacidad de declarar un tipo de valor que debe estar asignado a la pila. En otras palabras, estos tipos no se pueden crear nunca en el montón como miembro de otra clase. La principal motivación para esta característica era <xref:System.Span%601> y las estructuras relacionadas. <xref:System.Span%601> puede contener un puntero administrado como uno de sus miembros, siendo el otro la longitud del intervalo. En realidad se implementa de manera un poco diferente porque C# no admite punteros a la memoria administrada fuera de un contexto no seguro. Cualquier escritura que cambie el puntero y la longitud no es atómica. Es decir, un valor de <xref:System.Span%601> estaría sujeto a errores de fuera de intervalo o infracciones de seguridad de otro tipo cuando no se limita a un único marco de pila. Además, la colocación de un puntero administrado en el montón de GC normalmente se bloquea en tiempo JIT.

Puede tener requisitos similares al trabajar con memoria creada mediante [`stackalloc`](language-reference/keywords/stackalloc.md) o al usar memoria de las API de interoperabilidad. Puede definir sus propios tipos de `ref struct` para esas necesidades. En este artículo, verá ejemplos del uso de `Span<T>` por hacerlo más sencillo.

La declaración `ref struct` declara que un estructura de este tipo debe estar en la pila. Las reglas de lenguaje garantizan el uso seguro de estos tipos. Entre otros tipos declarados como `ref struct` se encuentra <xref:System.ReadOnlySpan%601>. 

El objetivo de mantener un tipo `ref struct` como una variable asignada a la pila presenta varias reglas que el compilador exige para todos los tipos `ref struct`.

- No puede encerrar un valor de `ref struct`. No puede asignar un tipo `ref struct` a una variable de tipo `object`, `dynamic` o cualquier tipo de interfaz.
- No puede declarar un `ref struct` como miembro de una clase o una estructura normal.
- No puede declarar variables locales que sean tipos `ref struct` en métodos asincrónicos. Pueden declararlas en los métodos sincrónicos que devuelven `Task`, `Task<T>` o tipos similares a la tarea.
- No puede declarar las variables locales de `ref struct` en iteradores.
- No puede capturar variables `ref struct` en expresiones lambda o funciones locales.

Estas restricciones aseguran que no use por error un valor `ref struct` de manera que pueda promoverlo al montón administrado.

## <a name="readonly-ref-struct-type"></a>Tipo de `readonly ref struct`

Si declara una estructura como `readonly ref` se combinan las ventajas y las restricciones de las declaraciones `ref struct` y `readonly struct`. 

En el siguiente ejemplo se muestra la declaración de `readonly ref struct`.

```csharp
readonly ref struct ReadOnlyRefPoint2D
{
    public int X { get; }
    public int Y { get; }
    
    ReadOnlyRefPoint2D(int x, int y) => (X, Y) = (x, y);
}
```

## <a name="conclusions"></a>Conclusiones

Estas mejoras del lenguaje C# están diseñadas para algoritmos críticos de rendimiento donde las asignaciones de memoria pueden resultar fundamentales para lograr el rendimiento necesario. Es posible que no use a menudo estas características en el código que escribe. Sin embargo, estas mejoras se adoptaron en muchas ubicaciones en .NET Framework. Dado que cada vez son más las API que utilizan estas características, comprobará que mejora el rendimiento de sus propias aplicaciones.

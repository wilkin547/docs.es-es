---
title: "Semántica de referencia con tipos de valor"
description: "Comprender las características del lenguaje que minimizan las estructuras de copias de forma segura"
author: billwagner
ms.author: wiwagn
ms.date: 11/10/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 9eeaf201c1f5a58044db62e356199b609c4c035a
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2017
---
# <a name="reference-semantics-with-value-types"></a>Semántica de referencia con tipos de valor

Una ventaja de utilizar tipos de valor es que a menudo evitar las asignaciones del montón.
La desventaja correspondiente es que se copian por valor. Esta compensación hace más difícil optimizar los algoritmos que funcionan en grandes cantidades de datos. Nuevas características del lenguaje en C# 7.2 proporcionan mecanismos que habilitan la semántica de paso por referencia con tipos de valor. Si utiliza estas características con sabiduría puede minimizar ambas asignaciones y las operaciones de copia. Este artículo exploran las nuevas características.

Gran parte del código de ejemplo en este artículo muestra características agregadas en C# 7.2. Para poder usar esas características, tendrá que configurar el proyecto para usar C# 7.2 o posterior en el proyecto. Puede usar Visual Studio para seleccionarlo. Para cada proyecto, seleccione **proyecto** en el menú, a continuación, **propiedades**. Seleccione el **generar** ficha y haga clic en **avanzadas**. Desde allí, puede configurar la versión de idioma. Elegir "7.2", o "más reciente".  También puede editar la *csproj* de archivos y agregue el siguiente nodo:

```XML
  <PropertyGroup>
    <LangVersion>7.2</LangVersion>
  </PropertyGroup>
```

Puede usar "7,2" o "más reciente" para el valor.

## <a name="specifying-in-parameters"></a>Especificar `in` parámetros

7.2 C# agrega los `in` palabra clave para complementar las existentes `ref` y `out` palabras clave al escribir un método que pasa argumentos por referencia. El `in` palabra clave especifica que está pasando el parámetro por referencia y el método llamado no modifica el valor pasado a él. 

Esta adición proporciona un vocabulario completo para expresar la intención del diseño. Tipos de valor se copian cuando se pasan a un método llamado cuando no se especifica ninguno de los siguientes modificadores. Cada uno de estos modificadores especifica que un tipo de valor se pasa por referencia, evitando la copia. Cada modificador expresa un propósito diferente:

- `out`: Este método establece el valor de los argumentos utilizados como este parámetro.
- `ref`: Este método puede establecer el valor de los argumentos utilizados como este parámetro.
- `in`: Este método no modifica el valor de los argumentos utilizados como este parámetro.

Cuando se agrega el `in` modificador para pasar un argumento por referencia, se declara la intención del diseño consiste en pasar argumentos por referencia para evitar la copia innecesaria. No se intenta modificar el objeto usado como ese argumento. El código siguiente muestra un ejemplo de un método que calcula la distancia entre dos puntos en un espacio 3D. 

[!code-csharp[InArgument](../../samples/csharp/reference-semantics/Program.cs#InArgument "Specifying an In argument")]

Los argumentos son dos estructuras que contienen tres valores Double. Un valor doble que tiene 8 bytes, por lo que cada argumento es de 24 bytes. Especificando el `in` modificador, se puede pasar una referencia 4 bytes o de 8 bits a esos argumentos, según la arquitectura de la máquina. La diferencia de tamaño es pequeña, pero puede agregar rápidamente cuando la aplicación llama a este método en un bucle ajustado con muchos valores diferentes.
 
El `in` modificador complementa `out` y `ref` de otras maneras. No se puede crear las sobrecargas de un método que se diferencian solo en presencia de `in`, `out` o `ref`. Estas nuevas reglas de extienden el mismo comportamiento que tenía que siempre se han definido para `out` y `ref` parámetros.

El `in` modificador se puede aplicar a cualquier miembro que toma parámetros: métodos, delegados, expresiones lambda, funciones locales, los indizadores, operadores.

A diferencia de `ref` y `out` argumentos, puede usar los valores literales o constantes para el argumento en un `in` parámetro. Además, a diferencia de un `ref` o `out` parámetro, no es necesario aplicar el `in` modificador en el sitio de llamada. El código siguiente muestra dos ejemplos de llamar al método el `CalculateDistance` método. El primero usa dos variables locales que se pasa por referencia. La segunda incluye una variable temporal que se crea como parte de la llamada al método. 

[!code-csharp[UseInArgument](../../samples/csharp/reference-semantics/Program.cs#UseInArgument "Specifying an In argument")]

Hay varias maneras en que el compilador se asegura de que la naturaleza de solo lectura de un `in` se aplica el argumento.  En primer lugar, el método llamado no se puede asignar directamente a un `in` parámetro. No se puede asignar directamente a cualquier campo de un `in` parámetro. Además, no puede pasar un `in` parámetro a cualquier método exigir la `ref` o `out` modificador.
El compilador exige que el `in` argumento es una variable de solo lectura. Puede llamar a cualquier método de instancia que utiliza la semántica de paso por valor. En esos casos, una copia de la `in` se crea el parámetro. Dado que el compilador puede crear una variable temporal para cualquier `in` parámetro, también puede especificar valores predeterminados para cualquier `in` parámetro. El código de seguimiento utiliza para especificar el origen (punto 0,0) como el valor predeterminado para el segundo punto:

[!code-csharp[InArgumentDefault](../../samples/csharp/reference-semantics/Program.cs#InArgumentDefault "Specifying defaults for an in parameter")]

El `in` designación de parámetro también se puede usar con tipos de referencia o integrado en valores numéricos. Sin embargo, las ventajas de ambos casos son mínimas, si lo hay.

## <a name="ref-readonly-returns"></a>`ref readonly`Devuelve

También puede devolver un tipo de valor por referencia, pero no permitir el llamador de modificar ese valor. Use la `ref readonly` modificador para expresar la intención de diseño. Notifica a los lectores que se devuelve una referencia a los datos existentes, pero no permite la modificación. 

El compilador exige que el autor de llamada no puede modificar la referencia. Intenta asignar directamente al valor genera un error de tiempo de compilación. Sin embargo, el compilador no puede saber si cualquier método de miembro modifica el estado de la estructura.
Para asegurarse de que el objeto no se modifica, el compilador crea una copia y llama a miembro referencias usando esa copia. Las modificaciones son a dicha copia estable. 

Es probable que la biblioteca con `Point3D` a menudo utilizaría el origen en todo el código. Cada instancia crea un nuevo objeto en la pila. Puede ser conveniente crear una constante y se devuelve por referencia. Sin embargo, si se devuelve una referencia al almacenamiento interno, puede querer exigir que el autor de llamada no puede modificar el almacenamiento que se hace referencia. El código siguiente define una propiedad de solo lectura que devuelve una `readonly ref` a un `Point3D` que especifica el origen.

[!code-csharp[OriginReference](../../samples/csharp/reference-semantics/Point3D.cs#OriginReference "Creating a readonly Origin reference")]

Crear una copia de una operación readonly ref devuelto es fácil: solo se asigna a una variable no declarada con la `ref readonly` modificador. El compilador genera código para copiar el objeto como parte de la asignación. 

Al asignar una variable a un `ref readonly return`, puede especificar un `ref readonly` variable o una copia por valor de la referencia de solo lectura:

[!code-csharp[AssignRefReadonly](../../samples/csharp/reference-semantics/Program.cs#AssignRefReadonly "Assigning a ref readonly")]

La primera asignación en el código anterior realiza una copia de la `Origin` constante y asigna ese copia. La segunda asigna una referencia. Tenga en cuenta que el `readonly` modificador debe formar parte de la declaración de la variable. No se puede modificar la referencia al que hace referencia. Intenta hacer esto producirá un error en tiempo de compilación.

## <a name="readonly-struct-type"></a>Tipo de `readonly struct`

Aplicar `ref readonly` a tráfico elevado entre los usos de un struct puede ser suficiente.
En otras ocasiones, puede que desee crear un struct inmutable. A continuación, siempre se puede pasar por referencia de solo lectura. Que el procedimiento quita la defensiva copia que tienen lugar cuando se tiene acceso a métodos de una estructura que se utiliza como un `in` parámetro.

Puede hacerlo mediante la creación de un `readonly struct` tipo. Puede agregar el `readonly` modificador en una declaración de estructura. El compilador exige que todos los miembros de la estructura son `readonly`; el `struct` deben ser inmutables.

Hay otras optimizaciones para una `readonly struct`. Puede usar el `in` modificador en todas las ubicaciones donde un `readonly struct` es un argumento. Además, puede devolver un `readonly struct` como un `ref return` cuando se devuelve un objeto cuya duración se extiende más allá del ámbito del método de devolución del objeto.

Por último, el compilador genera código más eficaz cuando se llama a los miembros de un `readonly struct`: el `this` referencia, en lugar de una copia del receptor, siempre es un `in` parámetro pasado por referencia al método de miembro. Esta optimización guarda la copia más cuando se usa un `readonly struct`. El `Point3D` es un excelente candidato para que este cambio. El código siguiente muestra un controlador actualizado, `ReadonlyPoint3D` estructura:

[!code-csharp[ReadonlyOnlyPoint3D](../../samples/csharp/reference-semantics/Point3D.cs#ReadonlyOnlyPoint3D "Defining an immutable structure")]

## <a name="ref-struct-type"></a>Tipo de `ref struct`

Otra característica del lenguaje relacionadas es la capacidad para declarar un tipo de valor que debe estar asignado a la pila. En otras palabras, nunca se puede crear estos tipos en el montón como miembro de otra clase. La principal motivación para esta característica estaba <xref:System.Span%601> y las estructuras relacionadas. <xref:System.Span%601>puede contener un puntero administrado como uno de sus miembros, el otro en la longitud del intervalo. En realidad se implementa un poco diferente porque C# no es compatible con punteros a la memoria administrada fuera de un contexto no seguro. Cualquier escritura que cambia el puntero y la longitud no es atómica. Es decir, un <xref:System.Span%601> sería sujeto a errores de intervalo insuficiente u otras infracciones de seguridad de tipo estaban no restringido a un marco de pila único. Además, colocar un puntero administrado en el montón del GC normalmente se bloquea en tiempo de JIT.

Puede tener requisitos similares, trabajar con memoria creado con [ `stackalloc` ](language-reference/keywords/stackalloc.md) o al uso de memoria de API de interoperabilidad. Puede definir sus propios `ref struct` tipos para esas necesidades. En este artículo, consulte Ver ejemplos de uso `Span<T>` para simplificar el trabajo.

El `ref struct` declaración declara que un struct de este tipo debe estar en la pila. Las reglas de lenguaje garantizan el uso seguro de estos tipos. Otros tipos declaran como `ref struct` incluir <xref:System.ReadOnlySpan%601>. 

El objetivo de mantener un `ref struct` escriba como una variable asignada a la pila presenta varias reglas que el compilador exige para todos los `ref struct` tipos.

- No se cuadro un `ref struct`. No se puede asignar un `ref struct` tipo a una variable de tipo `object`, `dynamic`, o cualquier tipo de interfaz.
- No se puede declarar un `ref struct` como un miembro de una clase o un struct normal.
- No se puede declarar variables locales que están `ref struct` tipos en métodos asincrónicos. Se pueden declarar en los métodos sincrónicos que devuelven `Task`, `Task<T>` o tipos similares de la tarea.
- No se puede declarar `ref struct` variables locales en iteradores.
- No se puede capturar `ref struct` variables en expresiones lambda o funciones locales.

Estas restricciones aseguran que se no usa accidentalmente una `ref struct` de manera que puede promoverlo al montón administrado.

## <a name="conclusions"></a>Conclusiones

Estas mejoras del lenguaje C# están diseñadas para algoritmos críticos de rendimiento donde las asignaciones de memoria pueden resultar fundamentales para lograr el rendimiento necesario. Es posible que no use a menudo estas características en el código que escribe. Sin embargo, estas mejoras fueron adoptadas en muchas ubicaciones en .NET Framework. Como cada vez más las API que simplifican el uso de estas características, podrá ver el rendimiento de sus propias aplicaciones mejorar.

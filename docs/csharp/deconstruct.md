---
title: Deconstruir tuplas y otros tipos
description: Obtenga información sobre cómo deconstruir tuplas y otros tipos.
ms.technology: csharp-fundamentals
ms.date: 07/18/2016
ms.assetid: 0b0c4b0f-4a47-4f66-9b8e-f5c63b195960
ms.openlocfilehash: 23d193faf9702628698fe558f6667aeb130e8916
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "73100664"
---
# <a name="deconstructing-tuples-and-other-types"></a>Deconstruir tuplas y otros tipos

Una tupla proporciona una manera ligera de recuperar varios valores de una llamada de método. Pero una vez que recupere la tupla, deberá controlar sus elementos individuales. Como se muestra en el ejemplo siguiente, es complicado hacerlo elemento a elemento. El método `QueryCityData` devuelve una tupla de 3, y cada uno de sus elementos se asigna a una variable en una operación independiente.

[!code-csharp[WithoutDeconstruction](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-tuple1.cs)]

También puede ser complicado recuperar varios valores de campo y propiedad de un objeto, ya que tendrá que asignar un valor de campo o propiedad a una variable miembro a miembro.

A partir de C# 7.0, puede recuperar varios elementos de una tupla o recuperar varios valores de campo, de propiedad y calculados de un objeto en una sola operación *deconstruct*. Cuando se deconstruye una tupla, sus elementos se asignan a variables individuales. Cuando se deconstruye un objeto, los valores seleccionados se asignan a variables individuales.

## <a name="deconstructing-a-tuple"></a>Deconstruir una tupla

C# incluye compatibilidad integrada para deconstruir tuplas, lo que permite desempaquetar todos los elementos de una tupla en una sola operación. La sintaxis general para deconstruir una tupla es parecida a la sintaxis para definirla, ya que las variables a las que se va a asignar cada elemento se escriben entre paréntesis en el lado izquierdo de una instrucción de asignación. Por ejemplo, la instrucción siguiente asigna los elementos de una tupla de 4 a cuatro variables independientes:

```csharp
var (name, address, city, zip) = contact.GetAddressInfo();
```

Hay tres formas de deconstruir una tupla:

- Se puede declarar explícitamente el tipo de cada campo entre paréntesis. En el ejemplo siguiente se usa este enfoque para deconstruir la tupla de 3 devuelta por el método `QueryCityData`.

    [!code-csharp[Deconstruction-Explicit](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-tuple2.cs#1)]

- Puede usar la palabra clave `var` para que C# deduzca el tipo de cada variable. Debe colocar la palabra clave `var` fuera de los paréntesis. En el ejemplo siguiente se usa la inferencia de tipos al deconstruir la tupla de 3 devuelta por el método `QueryCityData`.

    [!code-csharp[Deconstruction-Infer](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-tuple3.cs#1)]

    También se puede usar la palabra clave `var` individualmente con alguna de las declaraciones de variable, o todas, dentro de los paréntesis.

    [!code-csharp[Deconstruction-Infer-Some](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-tuple4.cs#1)]

    Esto es complicado y no se recomienda.

- Por último, puede deconstruir la tupla en variables que ya se hayan declarado.

    [!code-csharp[Deconstruction-Declared](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-tuple5.cs#1)]

Tenga en cuenta que no se puede especificar un tipo determinado fuera de los paréntesis, aunque todos los campos de la tupla tengan el mismo tipo. Esto genera el error del compilador CS8136: “El formato de desconstrucción ‘var (...)’ no permite especificar un tipo determinado para ‘var’”.

Tenga en cuenta que también debe asignar cada elemento de la tupla a una variable. Si se omite algún elemento, el compilador genera el error CS8132: "No se puede deconstruir una tupla de 'x' elementos en 'y' variables".

Tenga en cuenta que no se pueden mezclar declaraciones y asignaciones en variables existentes en el lado izquierdo de una deconstrucción. El compilador genera el error CS8184: "Una deconstrucción no puede mezclar declaraciones y expresiones en el lado izquierdo", cuando los miembros incluyen variables existentes recién declaradas.

## <a name="deconstructing-tuple-elements-with-discards"></a>Deconstruir elementos de tupla con descartes

A menudo, cuando se deconstruye una tupla, solo interesan los valores de algunos elementos. A partir de C# 7.0, puede aprovechar la compatibilidad de C# con los *descartes*, que son variables de solo escritura cuyos valores se decide omitir. Los descartes suelen designarse mediante un carácter de guion bajo ("\_") en una asignación. Puede descartar tantos valores como quiera; todos se representan mediante el descarte único `_`.

En el ejemplo siguiente se muestra el uso de tuplas con descartes. El método `QueryCityDataForYears` devuelve una tupla de 6 con el nombre de una ciudad, su superficie, un año, la población de la ciudad en ese año, un segundo año y la población de la ciudad en ese segundo año. En el ejemplo se muestra la evolución de la población entre esos dos años. De los datos disponibles en la tupla, no nos interesa la superficie de la ciudad, y conocemos el nombre de la ciudad y las dos fechas en tiempo de diseño. Como resultado, solo nos interesan los dos valores de población almacenados en la tupla, y podemos controlar los valores restantes como descartes.  

[!code-csharp[Tuple-discard](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]

## <a name="deconstructing-user-defined-types"></a>Deconstruir tipos definidos por el usuario

C# no ofrece compatibilidad integrada para deconstruir tipos que no son de tupla. A pesar de ello, como autor de una clase, una estructura o una interfaz, puede permitir que las instancias del tipo se deconstruyan mediante la implementación de uno o varios métodos `Deconstruct`. El método no devuelve ningún valor, y cada valor que se va a deconstruir se indica mediante un parámetro [out](language-reference/keywords/out-parameter-modifier.md) en la firma del método. Por ejemplo, el siguiente método `Deconstruct` de una clase `Person` devuelve el nombre de pila, el segundo nombre y los apellidos:

[!code-csharp[Class-deconstruct](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-class1.cs#1)]

Después, puede deconstruir una instancia de la clase `Person` denominada `p` con una asignación similar a la siguiente:

[!code-csharp[Class-deconstruct](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-class1.cs#2)]

En el ejemplo siguiente se sobrecarga el método `Deconstruct` para devolver varias combinaciones de las propiedades de un objeto `Person`. Las sobrecargas individuales devuelven lo siguiente:

- El nombre de pila y los apellidos.
- El nombre de pila, los apellidos y el segundo nombre.
- El nombre de pila, los apellidos, el nombre de la ciudad y el nombre del estado.

[!code-csharp[Class-deconstruct](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-class2.cs)]

Dado que se puede sobrecargar el método `Deconstruct` para reflejar los grupos de datos que se suelen extraer de un objeto, debe tener cuidado y definir métodos `Deconstruct` con firmas que sean distintivas y no resulten ambiguas. Puede resultar confuso usar varios métodos `Deconstruct` que tengan el mismo número de parámetros `out` o el mismo número y tipo de parámetros `out` en un orden diferente.

El método `Deconstruct` sobrecargado del ejemplo siguiente muestra un posible motivo de confusión. La primera sobrecarga devuelve el nombre de pila, el segundo nombre, los apellidos y la edad de un objeto `Person`, en ese orden. La segunda sobrecarga devuelve información sobre el nombre acompañada únicamente de los ingresos anuales, pero el nombre de pila, el segundo nombre y los apellidos están en un orden diferente. Esto hace que se pueda confundir fácilmente el orden de los argumentos cuando se deconstruye una instancia `Person`.

[!code-csharp[Deconstruct-ambiguity](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-ambiguous.cs)]

## <a name="deconstructing-a-user-defined-type-with-discards"></a>Deconstruir un tipo definido por el usuario con descartes

Tal como haría con las [tuplas](#deconstructing-tuple-elements-with-discards), puede usar descartes para omitir los elementos seleccionados que haya devuelto un método `Deconstruct`. Cada descarte se define mediante una variable denominada "\_". Una operación de deconstrucción única puede incluir varios descartes.

En el siguiente ejemplo se deconstruye un objeto `Person` en cuatro cadenas (el nombre propio, los apellidos, la ciudad y el estado), pero se descartan los apellidos y el estado.

[!code-csharp[Class-discard](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/class-discard1.cs#1)]

## <a name="deconstructing-a-user-defined-type-with-an-extension-method"></a>Deconstruir un tipo definido por el usuario con un método de extensión

Aunque no haya creado una clase, una estructura o una interfaz por sí mismo, puede igualmente deconstruir objetos de ese tipo. Para ello, implemente uno o varios [métodos de extensión](programming-guide/classes-and-structs/extension-methods.md) `Deconstruct` que devuelvan los valores que le interesen.

En el ejemplo siguiente se definen dos métodos de extensión `Deconstruct` para la clase <xref:System.Reflection.PropertyInfo?displayProperty=nameWithType>. El primero devuelve un conjunto de valores que indican las características de la propiedad, incluido su tipo, si es estática o de instancia, si es de solo lectura y si está indexada. El segundo indica la accesibilidad de la propiedad. Dado que la accesibilidad de los descriptores de acceso get y set puede diferir, los valores booleanos indican si la propiedad tiene descriptores de acceso get y set independientes y, si es así, si tienen la misma accesibilidad. Si solo hay un descriptor de acceso, o si los descriptores de acceso get y set tienen la misma accesibilidad, la variable `access` indica la accesibilidad de la propiedad en conjunto. En caso contrario, la accesibilidad de los descriptores de acceso get y set se indica mediante las variables `getAccess` y `setAccess`.

[!code-csharp[Extension-deconstruct](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-extension1.cs)]

## <a name="see-also"></a>Vea también

- [Descartes](discards.md)
- [Tuplas](tuples.md)

---
title: Registros
description: 'Obtenga información sobre cómo los registros de F # representan agregados simples de valores con nombre, opcionalmente con miembros.'
ms.date: 08/15/2020
ms.openlocfilehash: 2da31da0ec830d458a370e64ca105048181f5d74
ms.sourcegitcommit: 88fbb019b84c2d044d11fb4f6004aec07f2b25b1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "97899644"
---
# <a name="records"></a>Registros

Los registros representan agregados simples de valores con nombre, opcionalmente con miembros. Pueden ser Structs o tipos de referencia.  Son tipos de referencia de forma predeterminada.

## <a name="syntax"></a>Sintaxis

```fsharp
[ attributes ]
type [accessibility-modifier] typename =
    { [ mutable ] label1 : type1;
      [ mutable ] label2 : type2;
      ... }
    [ member-list ]
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, *TypeName* es el nombre del tipo de registro, *Label1* y *Label2* son nombres de valores, denominados *etiquetas*, y *Type1* y *tipo2* son los tipos de estos valores. *member-List* es la lista opcional de miembros del tipo.  Puede usar el `[<Struct>]` atributo para crear un registro struct en lugar de un registro que sea un tipo de referencia.

A continuación se muestran algunos ejemplos.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1901.fs)]

Cuando cada etiqueta está en una línea independiente, el punto y coma es opcional.

Puede establecer valores en expresiones conocidas como *expresiones de registro*. El compilador deduce el tipo a partir de las etiquetas utilizadas (si las etiquetas son suficientemente distintas de las de otros tipos de registro). Las llaves ({}) incluyen la expresión de registro. En el código siguiente se muestra una expresión de registro que inicializa un registro con tres elementos Float con etiquetas `x` , `y` y `z` .

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1907.fs)]

No utilice la forma abreviada si puede haber otro tipo que también tenga las mismas etiquetas.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1903.fs)]

Las etiquetas del tipo declarado más recientemente tienen prioridad sobre las del tipo declarado previamente, por lo que en el ejemplo anterior, `mypoint3D` se deduce que es `Point3D` . Puede especificar explícitamente el tipo de registro, como en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1908.fs)]

Los métodos se pueden definir para tipos de registro del mismo modo que para los tipos de clase.

## <a name="creating-records-by-using-record-expressions"></a>Crear registros mediante expresiones de registro

Puede inicializar los registros mediante las etiquetas definidas en el registro. Una expresión que hace esto se conoce como una *expresión de registro*. Use llaves para encerrar la expresión de registro y use el punto y coma como delimitador.

En el ejemplo siguiente se muestra cómo crear un registro.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1904.fs)]

Los signos de punto y coma después del último campo de la expresión de registro y de la definición de tipo son opcionales, independientemente de si todos los campos están en una sola línea.

Al crear un registro, debe proporcionar valores para cada campo. No se puede hacer referencia a los valores de otros campos de la expresión de inicialización de ningún campo.

En el código siguiente, el tipo de `myRecord2` se deduce de los nombres de los campos. Opcionalmente, puede especificar el nombre del tipo explícitamente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

Otra forma de construcción de registros puede ser útil si tiene que copiar un registro existente y, posiblemente, cambiar algunos de los valores de los campos. La siguiente línea de código ilustra esto.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

Esta forma de la expresión de registro se denomina *expresión de registro de copia y actualización*.

Los registros son inmutables de forma predeterminada; sin embargo, puede crear fácilmente registros modificados mediante una expresión de copia y actualización. También puede especificar explícitamente un campo mutable.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1909.fs)]

No use el atributo DefaultValue con campos de registro. Un mejor enfoque es definir instancias predeterminadas de registros con campos que se inicializan con valores predeterminados y, a continuación, usar una expresión de registro de copia y actualización para establecer los campos que difieren de los valores predeterminados.

```fsharp
// Rather than use [<DefaultValue>], define a default record.
type MyRecord =
    { Field1 : int
      Field2 : int }

let defaultRecord1 = { Field1 = 0; Field2 = 0 }
let defaultRecord2 = { Field1 = 1; Field2 = 25 }

// Use the with keyword to populate only a few chosen fields
// and leave the rest with default values.
let rr3 = { defaultRecord1 with Field2 = 42 }
```

## <a name="creating-mutually-recursive-records"></a>Crear registros recursivos mutuamente

En algún momento al crear un registro, puede que desee que dependa de otro tipo que le gustaría definir después. Se trata de un error de compilación a menos que defina los tipos de registro para que sean recursivos mutuamente.

La definición de registros recursivos mutuamente se realiza con la `and` palabra clave. Esto le permite vincular 2 o más tipos de registro juntos.

Por ejemplo, el código siguiente define un `Person` `Address` tipo y como recursivo mutuamente:

```fsharp
// Create a Person type and use the Address type that is not defined
type Person =
  { Name: string
    Age: int
    Address: Address }
// Define the Address type which is used in the Person record
and Address =
  { Line1: string
    Line2: string
    PostCode: string
    Occupant: Person }
```

Si fuera a definir el ejemplo anterior sin la `and` palabra clave, no se compilaría. La `and` palabra clave es necesaria para las definiciones mutuamente recursivas.

## <a name="pattern-matching-with-records"></a>Coincidencia de patrones con registros

Los registros se pueden usar con la coincidencia de patrones. Puede especificar algunos campos explícitamente y proporcionar variables para otros campos que se asignarán cuando se produzca una coincidencia. En el siguiente ejemplo código se muestra cómo hacerlo.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1910.fs)]

El resultado de este código es el siguiente.

```console
Point is at the origin.
Point is on the x-axis. Value is 100.000000.
Point is at (10.000000, 0.000000, -1.000000).
```

## <a name="records-and-members"></a>Registros y miembros

Puede especificar miembros en registros de forma muy parecida a como se hace con las clases. No se admiten los campos. Un enfoque común consiste en definir un `Default` miembro estático para facilitar la construcción de registros:

```fsharp
type Person =
  { Name: string
    Age: int
    Address: string }

    static member Default =
        { Name = "Phillip"
          Age = 12
          Address = "123 happy fun street" }

let defaultPerson = Person.Default
```

Si utiliza un identificador propio, ese identificador hace referencia a la instancia del registro cuyo miembro se llama:

```fsharp
type Person =
  { Name: string
    Age: int
    Address: string }

    member this.WeirdToString() =
        this.Name + this.Address + string this.Age

let p = { Name = "a"; Age = 12; Address = "abc123" }
let weirdString = p.WeirdToString()
```

## <a name="differences-between-records-and-classes"></a>Diferencias entre los registros y las clases

Los campos de registro se diferencian de los campos de clase en que se exponen automáticamente como propiedades, y se usan en la creación y copia de registros. La construcción de registros también difiere de la construcción de clases. En un tipo de registro, no se puede definir un constructor. En su lugar, se aplica la sintaxis de construcción que se describe en este tema. Las clases no tienen ninguna relación directa entre los parámetros de constructor, los campos y las propiedades.

Al igual que los tipos de estructura y Unión, los registros tienen una semántica estructural de igualdad. Las clases tienen semántica de igualdad de referencia. El siguiente ejemplo de código muestra esto.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1911.fs)]

El resultado de este código es el siguiente:

```console
The records are equal.
```

Si escribe el mismo código con clases, los dos objetos de clase no serían iguales porque los dos valores representarían dos objetos en el montón y solo se compararían las direcciones (a menos que el tipo de clase invalide el `System.Object.Equals` método).

Si necesita igualdad de referencia para los registros, agregue el atributo `[<ReferenceEquality>]` encima del registro.

## <a name="see-also"></a>Consulte también

- [Tipos en F#](fsharp-types.md)
- [Clases](classes.md)
- [Referencia del lenguaje F#](index.md)
- [Igualdad de referencia](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-referenceequalityattribute.html)
- [Coincidencia de patrones](pattern-matching.md)

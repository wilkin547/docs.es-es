---
title: Registros
description: Obtenga información sobre cómo F# registros representan agregados simples de valores con nombre, opcionalmente con miembros.
ms.date: 06/09/2019
ms.openlocfilehash: cfb8de8272b479571119ae4cf91ea1d6fd5db73c
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816191"
---
# <a name="records"></a>Registros

Los registros representan agregados simples de valores con nombre, opcionalmente con miembros. O bien pueden ser tipos de referencia o structs.  Son tipos de referencia de forma predeterminada.

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

En la sintaxis anterior, *typename* es el nombre del tipo de registro, *label1* y *label2* son nombres de valores, que se conoce como *etiquetas*, y *type1* y *type2* son los tipos de estos valores. *lista de miembros* es la lista opcional de miembros para el tipo.  Puede usar el `[<Struct>]` atributo para crear un registro de struct en lugar de un registro que es un tipo de referencia.

Estos son algunos ejemplos.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1901.fs)]

Una vez cada etiqueta en una línea independiente, el punto y coma es opcional.

Puede establecer los valores en expresiones que se conoce como *grabar expresiones*. El compilador deduce el tipo de las etiquetas que se usa (si las etiquetas son suficientemente distintas de los de otros tipos de registros). Llaves ({}) contienen la expresión de registro. El código siguiente muestra una expresión de registro que inicializa un registro con tres elementos float con etiquetas `x`, `y` y `z`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1907.fs)]

No utilice la forma abreviada si podría haber otro tipo que también tiene las mismas etiquetas.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1903.fs)]

Las etiquetas del tipo declarado más recientemente tienen prioridad sobre las del tipo declarado previamente, por lo tanto en el ejemplo anterior, `mypoint3D` se infiere para ser `Point3D`. Puede especificar explícitamente el tipo de registro, como se muestra en el código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1908.fs)]

Los métodos se pueden definir para los tipos de registros, como ocurre con los tipos de clase.

## <a name="creating-records-by-using-record-expressions"></a>Creación de registros mediante el uso de expresiones de registro

Puede inicializar los registros mediante el uso de las etiquetas que se definen en el registro. Una expresión que hace esto se conoce como un *grabar expresión*. Use llaves para incluir la expresión de registro y utilice el punto y coma como delimitador.

El ejemplo siguiente muestra cómo crear un registro.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1904.fs)]

El punto y coma después del último campo en la expresión de registro y en la definición de tipo es opcional, independientemente de si los campos están todas en una sola línea.

Cuando se crea un registro, debe proporcionar valores para cada campo. Los valores de otros campos en la expresión de inicialización para cualquier campo, no se puede consultar.

En el código siguiente, el tipo de `myRecord2` se deduce de los nombres de los campos. Si lo desea, puede especificar el nombre de tipo explícitamente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

Otra forma de construcción de registro puede ser útil cuando tiene que copiar un registro existente y posiblemente cambiar algunos de los valores de campo. Esto ilustra en la siguiente línea de código:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

Este formulario de la expresión de registro se denomina el *copiar y actualizar la expresión de registro*.

Los registros son inmutables de manera predeterminada; Sin embargo, puede crear fácilmente los registros modificados mediante el uso de una expresión de copia y actualización. Puede especificar explícitamente un campo mutable.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1909.fs)]

No use el atributo DefaultValue con campos de registro. Un mejor enfoque consiste en definir las instancias predeterminadas de los registros con campos que se inicializan en valores predeterminados y, a continuación, usar una copia y actualizar la expresión de registro para establecer los campos que difieren de los valores predeterminados.

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

## <a name="creating-mutually-recursive-records"></a>Crear mutuamente recursivas registros

En algún momento al crear un registro, desea hacer que dependen de otro tipo que le gustaría definir posteriormente. Se trata de un error de compilación a menos que defina los tipos de registro para ser mutuamente recursivas.

Definición mutuamente recursivas registros se realiza con el `and` palabra clave. Esto le permite vincular los tipos de 2 o más registros.

Por ejemplo, el código siguiente define un `Person` y `Address` tipo como mutuamente recursivas:

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
    PostCode: string }
```

Si tuviera que definir en el ejemplo anterior sin los `and` palabra clave, entonces no se compilará. El `and` palabra clave es necesaria para mutuamente recursivas definiciones.

## <a name="pattern-matching-with-records"></a>Coincidencia de patrones con registros

Registros pueden utilizarse con coincidencia de patrones. Puede especificar algunos campos explícitamente y proporcionar variables para otros campos que se asignará cuando se produce una coincidencia. En el siguiente ejemplo código se muestra cómo hacerlo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1910.fs)]

El resultado de este código es como sigue.

```
Point is at the origin.
Point is on the x-axis. Value is 100.000000.
Point is at (10.000000, 0.000000, -1.000000).
```

## <a name="differences-between-records-and-classes"></a>Diferencias entre clases y los registros

Campos de registro difieren de las clases que automáticamente se exponen como propiedades, y se usan en la creación y copia de registros. Construcción de registro también difiere de la construcción de la clase. En un tipo de registro, no se puede definir un constructor. En su lugar, se aplica la sintaxis de construcción descrita en este tema. Las clases no tienen ninguna relación directa entre los parámetros del constructor, campos y propiedades.

Al igual que los tipos de estructura y unión, los registros tienen semántica de igualdad estructural. Las clases tienen referencia semántica de igualdad. El siguiente ejemplo de código muestra esto.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1911.fs)]

El resultado de este código es como sigue:

```
The records are equal.
```

Si escribe el mismo código con clases, los dos objetos de clase sería desiguales porque los dos valores representarían dos objetos en el montón y se comparan solo las direcciones (a menos que el tipo de clase invalida el `System.Object.Equals` método).

Si necesita hacer referencia a la igualdad para los registros, agregue el atributo `[<ReferenceEquality>]` anteriormente el registro.

## <a name="see-also"></a>Vea también

- [Tipos en F#](fsharp-types.md)
- [Clases](classes.md)
- [Referencia del lenguaje F#](index.md)
- [Igualdad de referencia](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.referenceequalityattribute-class-%5bfsharp%5d)
- [Coincidencia de patrones](pattern-matching.md)

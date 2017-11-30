---
title: Tuplas en Visual Basic
ms.custom: 
ms.date: 04/23/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: tuples [Visual Basic]
ms.assetid: 3e66cd1b-3432-4e1d-8c37-5ebacae8f53f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be50b22e9acca9ff8cfbde798d78869ee1c72634
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="tuples-visual-basic"></a>Tuplas (Visual Basic)

A partir de Visual Basic de 2017, el lenguaje Visual Basic ofrece compatibilidad integrada para las tuplas que permite crear tuplas y acceder a los elementos de tuplas que sea más fácil. Una tupla es una estructura de datos ligero que tiene un número específico y la secuencia de valores. Al crear una instancia de la tupla, puede definir el número y el tipo de datos de cada valor (o elemento). Por ejemplo, una tupla de 2 (o un par) tiene dos elementos. Podría ser el primero un `Boolean` valor, mientras que el segundo es un `String`. Porque tuplas resulte sencillo almacenar varios valores en un único objeto, se usan a menudo como una forma sencilla de devolver varios valores de un método.

> [!IMPORTANT]
> La compatibilidad de tupla requiere el <xref:System.ValueTuple> tipo. Si no está instalado el 4.7 de .NET Framework, debe agregar el paquete de NuGet `System.ValueTuple`, que se encuentra disponible en la Galería de NuGet. Sin este paquete, puede obtener un error de compilación similar a "Tipo predefinido 'ValueTuple(Of,,,)' no está definido o importado."

## <a name="instantiating-and-using-a-tuple"></a>Creación de instancias y utilizando una tupla

Para crear instancias de una tupla envolvente sus paréntesis de mensajería instantánea de valores delimitada por comas. Cada uno de esos valores, a continuación, se convierte en un campo de la tupla. Por ejemplo, el código siguiente define un triple (o una tupla de 3) con un `Date` como su primer valor, un `String` como su segundo y un `Boolean` como su tercer.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#1)]

De forma predeterminada, el nombre de cada campo de una tupla consta de la cadena `Item` junto con la posición del campo basado en uno en la tupla. Para esta tupla de 3, el `Date` campo es `Item1`, `String` campo es `Item2`y el `Boolean` campo es `Item3`. El ejemplo siguiente muestra los valores de campos de la tupla que se crea una instancia en la línea anterior de código

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#2)]

Los campos de una tupla de Visual Basic son de lectura y escritura; una vez haya creado la instancia de una tupla, puede modificar sus valores. En el ejemplo siguiente se modifica dos de los tres campos de la tupla creada en el ejemplo anterior y muestra el resultado.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#3)]

## <a name="instantiating-and-using-a-named-tuple"></a>Creación de instancias y utilizando una tupla con nombre

En lugar de usar los nombres predeterminados para los campos de la tupla, puede crear instancias de un *denominado tupla* mediante la asignación de sus propios nombres de elementos de la tupla. Campos de la tupla pueden tener acceso por sus nombres asignados *o* por sus nombres de forma predeterminada. En el ejemplo siguiente se crea una instancia de la misma tupla de 3 como anteriormente, salvo que nombra explícitamente el primer campo `EventDate`, el segundo `Name`y el tercero `IsHoliday`. A continuación, muestra los valores de campo, modifica y muestra los valores de campo nuevo.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#4)]

## <a name="tuples-versus-structures"></a>Tuplas frente a las estructuras

Una tupla de Visual Basic es un tipo de valor que es una instancia de uno de los una **System.ValueTuple** tipos genéricos. Por ejemplo, el `holiday` tupla definida en el ejemplo anterior es una instancia de la <xref:System.ValueTuple%603> estructura. Está diseñado para ser un contenedor ligero para los datos. Puesto que tiene como objetivo la tupla que resulte sencillo crear un objeto con varios elementos de datos, carece de algunas de las características que puede tener una estructura personalizada. Se incluyen los siguientes:

- Miembros de cliente. No se puede definir sus propias propiedades, métodos o eventos de una tupla.

- Validación. No se puede validar los datos asignados a los campos.

- Inmutabilidad. Visual Basic tuplas son mutables. En cambio, una estructura personalizada le permite controlar si una instancia es mutable o no.

Si los miembros personalizados, propiedades y validación de campos o inmutabilidad es importante, debe usar Visual Basic [estructura](../../../language-reference/statements/structure-statement.md) instrucción para definir un tipo de valor personalizado.

Una tupla de Visual Basic heredan los miembros de su **ValueTuple** tipo. Además de sus campos, incluyen los siguientes métodos:

| Miembro | Descripción |
| ---|---|
| CompareTo | Compara la tupla actual a otro tupla con el mismo número de elementos. |
| Es igual a | Determina si la tupla actual es igual que otro objeto o tupla. |
| GetHashCode | Calcula el código hash de la instancia actual. |
| ToString | Devuelve la representación de cadena de este tupla, que tiene la forma `(Item1, Item2...)`, donde `Item1` y `Item2` representan los valores de campos de la tupla. |

Además, el **ValueTuple** tipos implementan <xref:System.Collections.IStructuralComparable> y <xref:System.Collections.IStructuralEquatable> , las interfaces que le permiten definir comparadores de cliente.

## <a name="assignment-and-tuples"></a>Asignación y tuplas

Visual Basic admite la asignación entre los tipos de tupla que tienen el mismo número de campos. Los tipos de campo se pueden convertir si se cumple alguna de las siguientes acciones:

- El campo de origen y destino son del mismo tipo.

- Se define una conversión de ampliación (o implícita) del tipo de origen al tipo de destino. 

- `Option Strict`es `On`, y se define una conversión de restricción (o explícita) del tipo de origen al tipo de destino. Esta conversión puede producir una excepción si el valor de origen está fuera del intervalo del tipo de destino.

Otras conversiones no se tienen en cuenta para las asignaciones. Echemos un vistazo a los tipos de asignaciones que se permiten entre los tipos de tupla.

Tenga en cuenta estas variables que se usan en los ejemplos siguientes:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

Las dos primeras variables, `unnamed` y `anonymous`, no tiene semántica nombres proporcionados para los campos. Sus nombres de campo están el valor predeterminado `Item1` y `Item2`. Las dos últimas variables, `named` y `differentName` tienen nombres de campo semántico. Tenga en cuenta que estas dos tuplas tienen nombres diferentes para los campos.

Los cuatro de estos tuplas tienen el mismo número de campos (denominados 'aridad') y los tipos de esos campos son idénticos. Por consiguiente, todas estas asignaciones funcionan:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

Observe que los nombres de las tuplas no se asignan. Los valores de los campos se asignan según el orden de los campos de la tupla.

Por último, tenga en cuenta que se puede asignar la `named` tupla para el `conversion` tupla, aunque el primer campo de `named` es un `Integer`y el primer campo de `conversion` es una `Long`. Esta asignación se realiza correctamente porque la conversión de un `Integer` a una `Long` es una conversión de ampliación.

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#3)]

No son asignables tuplas con un número diferente de campos:

```vb
' Does not compile.
' VB30311: Value of type '(Integer, Integer, Integer)' cannot be converted
'          to '(Answer As Integer, Message As String)'
var differentShape = (1, 2, 3)
named = differentShape
```

## <a name="tuples-as-method-return-values"></a>Tuplas como valores devueltos del método

Un método puede devolver un solo valor. Sin embargo, con frecuencia, desea que una llamada al método para devolver varios valores. Hay varias formas de evitar esta limitación:

- Puede crear una clase o estructura personalizada cuyas propiedades o campos representan los valores devueltos por el método. Por lo tanto, es una solución pesado; requiere que se defina un tipo personalizado cuyo único propósito es recuperar los valores de una llamada al método.

- Puede devolver un solo valor desde el método y devolver los valores restantes pasando por referencia al método. Esto implica la sobrecarga de crear instancias de una variable y los riesgos que se sobrescriba accidentalmente el valor de la variable que se pasa por referencia.

- Puede utilizar una tupla, que proporciona una solución ligera para recuperar varios valores devueltos.

Por ejemplo, el **TryParse** métodos de devolución de .NET un `Boolean` valor que indica si la operación de análisis se realizó correctamente. El resultado de la operación de análisis se devuelve en una variable que se pasa por referencia al método. Normalmente, una llamada a la un método de análisis como <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> el siguiente aspecto:

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#1)]

Podemos devolvemos una tupla de la operación de análisis si se incluyen la llamada a la <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> método en el propio método. En el ejemplo siguiente, `NumericLibrary.ParseInteger` llamadas el <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> método y devuelve una tupla con dos elementos con nombre. 

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

A continuación, puede llamar al método con un código como el siguiente:

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

## <a name="visual-basic-tuples-and-tuples-in-the-net-framework"></a>Tuplas de Visual Basic y las tuplas en .NET Framework

Una tupla de Visual Basic es una instancia de uno de los **System.ValueTuple** tipos genéricos, que se introdujeron en la 4.7 de .NET Framework. .NET Framework también incluye un conjunto de genérico **System.Tuple** clases. Estas clases, no obstante, difieren de las tuplas de Visual Basic y **System.ValueTuple** tipos genéricos en una de varias maneras:

- Los elementos de la **tupla** clases son propiedades denominadas `Item1`, `Item2`, y así sucesivamente. En Visual Basic tuplas y **ValueTuple** tipos de elementos de tupla son campos.

- No se puede asignar nombres descriptivos a los elementos de un **tupla** instancia o de un **ValueTuple** instancia. Visual Basic permite asignar nombres a los que se comunican el significado de los campos.

- Las propiedades de un **tupla** instancia son de solo lectura; las tuplas son inmutables. En Visual Basic tuplas y **ValueTuple** tipos, campos de tupla son de lectura y escritura; las tuplas son mutables.

- La interfaz genérica **tupla** tipos son tipos de referencia. Uso de estas **tupla** significa asignar objetos de tipos. En rutas de acceso activas, esto puede suponer un importante impacto en el rendimiento de la aplicación. Tuplas de Visual Basic y **ValueTuple** tipos son tipos de valor.

Métodos de extensión en la <xref:System.TupleExtensions> clase que sean fáciles de convertir entre tuplas de Visual Basic y .NET **tupla** objetos. El **ToTuple** método convierte una tupla de Visual Basic .NET **tupla** objeto y el **ToValueTuple** método convierte .NET **tupla** objeto de una tupla de Visual Basic.

En el ejemplo siguiente se crea una tupla, lo convierte en .NET **tupla** objeto y lo vuelve a convertir una tupla de Visual Basic. En el ejemplo a continuación, compara este tupla con el original para asegurarse de que son iguales.

[!code-vb[Convert](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple2.vb#1)]

## <a name="see-also"></a>Vea también

[Referencia del lenguaje Visual Basic](index.md)  

---
title: Tuplas en Visual Basic
ms.custom: 
ms.date: 04/23/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- tuples [Visual Basic]
ms.assetid: 3e66cd1b-3432-4e1d-8c37-5ebacae8f53f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2653b9dc8a6ecbcb718c20be8bd6275edf4cfb6e
ms.sourcegitcommit: be1fb5d9447ad459bef22b91a91c72e3e0b2d916
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2018
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

## <a name="inferred-tuple-element-names"></a>Nombres de elementos de tupla deducido

A partir de 15.3 de Visual Basic, Visual Basic puede deducir los nombres de elementos de tupla; no tienes que volver a asignarlos explícitamente. Los nombres de tupla deducidos son útiles al inicializar una tupla a partir de un conjunto de variables y desea que el nombre del elemento de tupla para ser el mismo que el nombre de variable. 

En el ejemplo siguiente se crea un `stateInfo` tupla que contiene tres explícitamente denominado elementos, `state`, `stateName`, y `capital`. Tenga en cuenta que, en el nombre de los elementos, la instrucción de inicialización de tupla simplemente asigna los elementos nombrados los valores de las variables con el mismo nombre.

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#1)]
 
Dado que los elementos y las variables tienen el mismo nombre, el compilador de Visual Basic puede deducir los nombres de los campos, como se muestra en el ejemplo siguiente.

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#2)]

Para habilitar los nombres de elementos de tupla interred, debe definir la versión del compilador de Visual Basic para usar en su proyecto de Visual Basic (\*.vbproj) archivo: 

```xml 
<PropertyGroup> 
  <LangVersion>15.3</LangVersion> 
</PropertyGroup> 

The version number can be any version of the Visual Basic compiler starting with 15.3. Rather than hard-coding a specific compiler version, you can also specify "Latest" as the value of `LangVersion` to compile with the most recent version of the Visual Basic compiler installed on your system.

In some cases, the Visual Basic compiler cannot infer the tuple element name from the candidate name, and the tuple field can only be referenced using its default name, such as `Item1`, `Item2`, etc. These include:

- The candidate name is the same as the name of a tuple member, such as `Item3`, `Rest`, or `ToString`.

- The candidate name is duplicated in the tuple.
 
When field name inference fails, Visual Basic does not generate a compiler error, nor is an exception thrown at runtime. Instead, tuple fields must be referenced by their predefined names, such as `Item1` and `Item2`. 
  
## Tuples versus structures

A Visual Basic tuple is a value type that is an instance of one of the a **System.ValueTuple** generic types. For example, the `holiday` tuple defined in the previous example is an instance of the <xref:System.ValueTuple%603> structure. It is designed to be a lightweight container for data. Since the tuple aims to make it easy to create an object with multiple data items, it lacks some of the features that a custom structure might have. These include:

- Customer members. You cannot define your own properties, methods, or events for a tuple.

- Validation. You cannot validate the data assigned to fields.

- Immutability. Visual Basic tuples are mutable. In contrast, a custom structure allows you to control whether an instance is mutable or immutable.

If custom members, property and field validation, or immutability are important, you should use the Visual Basic [Structure](../../../language-reference/statements/structure-statement.md) statement to define a custom value type.

A Visual Basic tuple does inherit the members of its **ValueTuple** type. In addition to its fields, these include the following methods:

| Member | Description |
| ---|---|
| CompareTo | Compares the current tuple to another tuple with the same number of elements. |
| Equals | Determines whether the current tuple is equal to another tuple or object. |
| GetHashCode | Calculates the hash code for the current instance. |
| ToString | Returns the string representation of this tuple, which takes the form `(Item1, Item2...)`, where `Item1` and `Item2` represent the values of the tuple's fields. |

In addition, the **ValueTuple** types implement <xref:System.Collections.IStructuralComparable> and <xref:System.Collections.IStructuralEquatable> interfaces, which allow you to define customer comparers.

## Assignment and tuples

Visual Basic supports assignment between tuple types that have the same number of fields. The field types can be converted if one of the following is true:

- The source and target field are of the same type.

- A widening (or implicit) conversion of the source type to the target type is defined. 

- `Option Strict` is `On`, and a narrowing (or explicit) conversion of the source type to the target type is defined. This conversion can throw an exception if the source value is outside the range of the target type.

Other conversions are not considered for assignments. Let's look at the kinds of assignments that are allowed between tuple types.

Consider these variables used in the following examples:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

The first two variables, `unnamed` and `anonymous`, do not have semantic names provided for the fields. Their field names are the default `Item1` and `Item2`. The last two variables, `named` and `differentName` have semantic field names. Note that these two tuples have different names for the fields.

All four of these tuples have the same number of fields (referred to as 'arity'), and the types of those fields are identical. Therefore, all of these assignments work:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

Notice that the names of the tuples are not assigned. The values of the fields are assigned following the order of the fields in the tuple.

Finally, notice that we can assign the `named` tuple to the `conversion` tuple, even though the first field of `named` is an `Integer`, and the first field of `conversion` is a `Long`. This assignment succeeds because converting an `Integer` to a `Long` is a widening conversion.

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#3)]

Tuples with different numbers of fields are not assignable:

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

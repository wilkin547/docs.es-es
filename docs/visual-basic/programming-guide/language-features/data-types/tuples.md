---
title: Tuplas en Visual Basic
ms.date: 04/23/2017
helpviewer_keywords:
- tuples [Visual Basic]
ms.assetid: 3e66cd1b-3432-4e1d-8c37-5ebacae8f53f
ms.openlocfilehash: c0198cde88b66f5e115c82b5454bd8a32db7ef96
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143719"
---
# <a name="tuples-visual-basic"></a>Tuplas (Visual Basic)

A partir de Visual Basic 2017, el lenguaje Visual Basic ofrece asistencia integrada para las tuplas que permite crear tuplas y acceder a los elementos de tuplas que sea más fácil. Una tupla es una estructura de datos ligero que tiene un número específico y la secuencia de valores. Al crear una instancia de la tupla, se definen el número y el tipo de datos de cada valor (o elemento). Por ejemplo, una tupla de 2 (o un par) tiene dos elementos. Podría ser el primero un `Boolean` valor, mientras que el segundo es un `String`. Dado que las tuplas que sea fácil almacenar varios valores en un único objeto, se utilizan a menudo una forma ligera para devolver varios valores de un método.

> [!IMPORTANT]
> Compatibilidad con tupla requiere el <xref:System.ValueTuple> tipo. Si no está instalado .NET Framework 4.7, debe agregar el paquete NuGet `System.ValueTuple`, que está disponible en la Galería de NuGet. Sin este paquete, puede aparecer un error de compilación similar a "Tipo predefinido 'ValueTuple(Of,,,)' no está definido o importado."

## <a name="instantiating-and-using-a-tuple"></a>Creación de instancias y uso de una tupla

Crear una instancia de una tupla, incluya sus paréntesis de mensajería instantánea de valores delimitada por comas. Cada uno de esos valores, a continuación, se convierte en un campo de la tupla. Por ejemplo, el código siguiente define un triple (o una tupla de 3) con un `Date` como su primer valor, un `String` como el segundo y un `Boolean` como su tercer.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#1)]

De forma predeterminada, el nombre de cada campo de una tupla consta de la cadena `Item` junto con la posición del campo basado en uno de la tupla. De esta tupla de 3, el `Date` campo es `Item1`, el `String` campo es `Item2`y el `Boolean` campo es `Item3`. El ejemplo siguiente muestra los valores de campos de la tupla que se crea una instancia de la línea de código anterior

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#2)]

Los campos de una tupla de Visual Basic son de lectura y escritura; una vez que haya creado la instancia de una tupla, puede modificar sus valores. El ejemplo siguiente modifica dos de los tres campos de la tupla creada en el ejemplo anterior y muestra el resultado.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#3)]

## <a name="instantiating-and-using-a-named-tuple"></a>Creación de instancias y uso de una tupla con nombre

En lugar de usar nombres predeterminados para los campos de la tupla, puede crear una instancia de un *tupla con nombre* mediante la asignación de sus propios nombres a los elementos de la tupla. Campos de la tupla, a continuación, pueden obtenerse por sus nombres asignados *o* por sus nombres de forma predeterminada. El ejemplo siguiente se crea una instancia de la tupla de 3 misma como anteriormente, salvo que nombra explícitamente el primer campo `EventDate`, el segundo `Name`y el tercero `IsHoliday`. A continuación, muestra los valores de campo, modifica y muestra los valores de campo nuevo.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#4)]

## <a name="inferred-tuple-element-names"></a>Nombres de elementos de tupla inferidos

Comenzando con la versión 15.3 de Visual Basic, Visual Basic puede deducir los nombres de elementos de tupla; no es necesario que los asigne explícitamente. Los nombres de tupla deducidos son útiles al inicializar una tupla a partir de un conjunto de variables y desea que el nombre del elemento de tupla para ser el mismo que el nombre de variable. 

En el ejemplo siguiente se crea un `stateInfo` tupla que contiene tres explícitamente denominado elementos, `state`, `stateName`, y `capital`. Tenga en cuenta que, en la nomenclatura de los elementos, la instrucción de inicialización de tupla simplemente asigna los elementos con los valores de las variables con el mismo nombre.

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#1)]
 
Dado que los elementos y las variables tienen el mismo nombre, el compilador de Visual Basic puede deducir los nombres de los campos, como se muestra en el ejemplo siguiente.

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#2)]

Para permitir que los nombres de elementos de tupla deducidos, debe definir la versión del compilador de Visual Basic para usar en su proyecto de Visual Basic (\*.vbproj) archivo: 

```xml 
<PropertyGroup> 
  <LangVersion>15.3</LangVersion> 
</PropertyGroup> 
```

El número de versión puede ser cualquier versión del compilador de Visual Basic, comenzando con la versión 15.3. En lugar de codificar una versión específica del compilador, también puede especificar "Latest" como el valor de `LangVersion` para compilar con la versión más reciente del compilador de Visual Basic instalada en el sistema.

Para obtener más información, consulte [configuración de la versión de idioma de Visual Basic](../../../language-reference/configure-language-version.md).

En algunos casos, el compilador de Visual Basic no puede inferir el nombre del elemento de tupla desde el nombre del candidato y el campo de tupla solo se puede hacer referencia mediante su nombre predeterminado, como `Item1`, `Item2`, etcetera. Se incluyen los siguientes:

- El nombre del candidato es el mismo que el nombre de un miembro de la tupla, como `Item3`, `Rest`, o `ToString`.

- El nombre del candidato está duplicado en la tupla.
 
Cuando se produce un error en la inferencia de nombre de campo, Visual Basic no genera un error del compilador, ni es una excepción en tiempo de ejecución. En su lugar, los campos de tupla deben hacer referencia a sus nombres predefinidos, como `Item1` y `Item2`. 
  
## <a name="tuples-versus-structures"></a>Tuplas frente a estructuras

Una tupla de Visual Basic es un tipo de valor que es una instancia de uno de los un **System.ValueTuple** tipos genéricos. Por ejemplo, el `holiday` tupla definida en el ejemplo anterior es una instancia de la <xref:System.ValueTuple%603> estructura. Está diseñado para ser un contenedor ligero para datos. Dado que el objetivo es la tupla para facilitar la creación de un objeto con varios elementos de datos, carece de algunas de las características que podría tener una estructura personalizada. Se incluyen los siguientes:

- Miembros personalizados. No se puede definir sus propias propiedades, métodos o eventos de una tupla.

- Validación. No se puede validar los datos asignados a campos.

- Inmutabilidad. Las tuplas de Visual Basic son mutables. En cambio, una estructura personalizada le permite controlar si una instancia es mutable o no.

Si la inmutabilidad y validación de campos, propiedades o miembros personalizados es importante, debe usar Visual Basic [estructura](../../../language-reference/statements/structure-statement.md) instrucción para definir un tipo de valor personalizado.

Una tupla de Visual Basic heredan los miembros de su **ValueTuple** tipo. Además de sus campos, estos incluyen los siguientes métodos:

| Miembro | Descripción |
| ---|---|
| CompareTo | Compara la tupla actual a otra tupla con el mismo número de elementos. |
| Es igual a | Determina si la tupla actual es igual que otro objeto o tupla. |
| GetHashCode | Calcula el código hash para la instancia actual. |
| ToString | Devuelve la representación de cadena de esta tupla, que tiene la forma `(Item1, Item2...)`, donde `Item1` y `Item2` representan los valores de campos de la tupla. |

Además, el **ValueTuple** tipos implementan <xref:System.Collections.IStructuralComparable> y <xref:System.Collections.IStructuralEquatable> interfaces, que le permiten definir comparadores de cliente.

## <a name="assignment-and-tuples"></a>Asignación y tuplas

Visual Basic admite la asignación entre tipos de tupla que tienen el mismo número de campos. Los tipos de campo se pueden convertir si se cumple una de las siguientes acciones:

- El campo de origen y destino son del mismo tipo.

- Se define una conversión de ampliación (o implícita) del tipo de origen al tipo de destino. 

- `Option Strict` es `On`, y se define una conversión de restricción (o explícita) del tipo de origen al tipo de destino. Esta conversión puede producir una excepción si el valor de origen está fuera del intervalo del tipo de destino.

Otras conversiones no se tienen en cuenta para las asignaciones. Echemos un vistazo a los tipos de asignaciones que se permiten entre los tipos de tupla.

Tenga en cuenta estas variables que se usan en los ejemplos siguientes:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

Las dos primeras variables, `unnamed` y `anonymous`, no tienen nombres semánticos proporcionados para los campos. Sus nombres de campo son los predeterminados `Item1` y `Item2`. Las dos últimas variables, `named` y `differentName` tienen nombres de campo semántico. Tenga en cuenta que estas dos tuplas tienen nombres diferentes para los campos.

Todas estas cuatro tuplas tienen el mismo número de campos (denominados "aridad") y los tipos de esos campos son idénticos. Por consiguiente, todas estas asignaciones funcionan:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

Observe que los nombres de las tuplas no se asignan. Los valores de los campos se asignan según el orden de los campos de la tupla.

Por último, tenga en cuenta que podemos asignar el `named` tupla para el `conversion` tupla, incluso aunque el primer campo de `named` es un `Integer`y el primer campo de `conversion` es un `Long`. Esta asignación se realiza correctamente porque la conversión de un `Integer` a un `Long` es una conversión de ampliación.

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#3)]

Las tuplas con distintos números de campos no son asignables:

```vb
' Does not compile.
' VB30311: Value of type '(Integer, Integer, Integer)' cannot be converted
'          to '(Answer As Integer, Message As String)'
var differentShape = (1, 2, 3)
named = differentShape
```

## <a name="tuples-as-method-return-values"></a>Tuplas como valores devueltos del método

Un método puede devolver un solo valor. Con frecuencia, sin embargo, desea que una llamada al método para devolver varios valores. Hay varias maneras de solucionar esta limitación:

- Puede crear una clase personalizada o una estructura cuyas propiedades o campos representan los valores devueltos por el método. Por lo tanto, es una solución pesada; requiere que se defina un tipo personalizado cuyo único propósito es recuperar los valores de una llamada al método.

- Puede devolver un único valor desde el método y devolver los valores restantes pasando por referencia al método. Esto implica la sobrecarga de crear instancias de una variable y los riesgos que se sobrescriba accidentalmente el valor de la variable que se pasa por referencia.

- Puede utilizar una tupla, que proporciona una solución ligera para recuperar varios valores devueltos.

Por ejemplo, el **TryParse** los métodos de devolución de .NET un `Boolean` valor que indica si la operación de análisis se realizó correctamente. Se devuelve el resultado de la operación de análisis en una variable pasada por referencia al método. Normalmente, una llamada a la un método de análisis como <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> el siguiente aspecto:

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#1)]

Podemos devolvemos una tupla de la operación de análisis si se incluyen la llamada a la <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> método en nuestro propio método. En el ejemplo siguiente, `NumericLibrary.ParseInteger` llamadas la <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> método y devuelve una tupla con nombre con dos elementos. 

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

A continuación, puede llamar al método con código similar al siguiente:

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

## <a name="visual-basic-tuples-and-tuples-in-the-net-framework"></a>Tuplas de Visual Basic y las tuplas en .NET Framework

Una tupla de Visual Basic es una instancia de uno de los **System.ValueTuple** tipos genéricos, que se introdujeron en .NET Framework 4.7. .NET Framework también incluye un conjunto de genérico **System.Tuple** clases. Estas clases, pero difieren de las tuplas de Visual Basic y **System.ValueTuple** tipos genéricos en varios aspectos:

- Los elementos de la **tupla** clases son propiedades denominadas `Item1`, `Item2`, y así sucesivamente. En Visual Basic tuplas y **ValueTuple** tipos, elementos de tupla son campos.

- No se puede asignar nombres descriptivos a los elementos de un **tupla** instancia o de un **ValueTuple** instancia. Visual Basic permite asignar nombres a los que se comunican el significado de los campos.

- Las propiedades de un **tupla** instancia son de solo lectura; las tuplas son inmutables. En Visual Basic tuplas y **ValueTuple** tipos, campos de tupla son de lectura y escritura; las tuplas son mutables.

- La interfaz genérica **tupla** tipos son tipos de referencia. Uso de estos **tupla** implica la asignación de objetos de tipos. En rutas de acceso activas, esto puede suponer un importante impacto en el rendimiento de la aplicación. Las tuplas de Visual Basic y **ValueTuple** tipos son tipos de valor.

Métodos de extensión en el <xref:System.TupleExtensions> clase facilitan la conversión entre las tuplas de Visual Basic y .NET **tupla** objetos. El **ToTuple** método convierte una tupla de Visual Basic en .NET **tupla** objeto y el **ToValueTuple** método convierte .NET **tupla** objeto en una tupla de Visual Basic.

En el ejemplo siguiente se crea una tupla, lo convierte en un .NET **tupla** objeto y se convierte de nuevo a una tupla de Visual Basic. El ejemplo, a continuación, comparan esta tupla con el original para asegurarse de que son iguales.

[!code-vb[Convert](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple2.vb#1)]

## <a name="see-also"></a>Vea también

[Referencia del lenguaje Visual Basic](index.md)  

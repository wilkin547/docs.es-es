---
description: 'Más información sobre: tuplas (Visual Basic)'
title: Tuplas
ms.date: 04/23/2017
helpviewer_keywords:
- tuples [Visual Basic]
ms.assetid: 3e66cd1b-3432-4e1d-8c37-5ebacae8f53f
ms.openlocfilehash: f598facb446b7d50864c0cf9151195cfcde158bb
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100454461"
---
# <a name="tuples-visual-basic"></a>Tuplas (Visual Basic)

A partir de Visual Basic 2017, el lenguaje de Visual Basic ofrece compatibilidad integrada para tuplas que facilitan la creación de tuplas y el acceso a los elementos de las tuplas. Una tupla es una estructura de datos ligera que tiene un número específico y una secuencia de valores. Al crear una instancia de la tupla, se define el número y el tipo de datos de cada valor (o elemento). Por ejemplo, una tupla de 2 (o par) tiene dos elementos. El primero puede ser un `Boolean` valor, mientras que el segundo es `String` . Dado que las tuplas facilitan el almacenamiento de varios valores en un único objeto, a menudo se usan como una manera ligera de devolver varios valores de un método.

> [!IMPORTANT]
> La compatibilidad de tupla requiere el <xref:System.ValueTuple> tipo. Si el .NET Framework 4,7 no está instalado, debe agregar el paquete NuGet `System.ValueTuple` , que está disponible en la galería de Nuget. Sin este paquete, puede obtener un error de compilación similar al siguiente: "el tipo predefinido ' ValueTuple (de,,,) ' no está definido ni importado".

## <a name="instantiating-and-using-a-tuple"></a>Crear instancias y usar una tupla

Cree una instancia de una tupla incluyendo los valores delimitados por comas entre paréntesis. Cada uno de esos valores se convierte en un campo de la tupla. Por ejemplo, el código siguiente define un triple (o 3-tupla) con `Date` como su primer valor, un `String` como segundo y `Boolean` como el tercero.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#1)]

De forma predeterminada, el nombre de cada campo de una tupla se compone de la cadena `Item` junto con la posición basada en uno de los campos de la tupla. En esta tupla de 3, el `Date` campo es `Item1` , el `String` campo es `Item2` y el `Boolean` campo es `Item3` . En el ejemplo siguiente se muestran los valores de los campos de la tupla de la que se ha creado una instancia en la línea de código anterior.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#2)]

Los campos de una tupla Visual Basic son de lectura y escritura; después de haber creado una instancia de una tupla, puede modificar sus valores. En el ejemplo siguiente se modifican dos de los tres campos de la tupla creada en el ejemplo anterior y se muestra el resultado.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#3)]

## <a name="instantiating-and-using-a-named-tuple"></a>Crear instancias y usar una tupla con nombre

En lugar de usar nombres predeterminados para los campos de una tupla, puede crear instancias de una *tupla con nombre* asignando sus propios nombres a los elementos de la tupla. A continuación, se puede tener acceso a los campos de la tupla por sus nombres asignados *o* por sus nombres predeterminados. En el ejemplo siguiente se crea una instancia de la misma tupla de 3 que anteriormente, salvo que asigna explícitamente un nombre al primer campo `EventDate` , el segundo `Name` y el tercero `IsHoliday` . A continuación, se muestran los valores de campo, se modifican y se muestran los valores de campo de nuevo.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#4)]

## <a name="inferred-tuple-element-names"></a>Nombres de elementos de tupla inferidos

A partir de Visual Basic 15,3, Visual Basic puede deducir los nombres de los elementos de tupla; no es necesario asignarlos explícitamente. Los nombres de tupla deducidos son útiles cuando se inicializa una tupla a partir de un conjunto de variables y se desea que el nombre del elemento de tupla sea el mismo que el nombre de la variable.

En el ejemplo siguiente se crea una `stateInfo` tupla que contiene tres elementos con el nombre explícito,, `state` `stateName` y `capital` . Tenga en cuenta que, al asignar nombres a los elementos, la instrucción de inicialización de tupla simplemente asigna los elementos con nombre a los valores de las variables con el mismo nombre.

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#1)]

Dado que los elementos y las variables tienen el mismo nombre, el compilador Visual Basic puede deducir los nombres de los campos, como se muestra en el ejemplo siguiente.

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#2)]

Para habilitar los nombres de elementos de tupla inferidos, debe definir la versión del compilador Visual Basic que se va a usar en el archivo de proyecto Visual Basic ( \* . vbproj):

```xml
<PropertyGroup>
  <LangVersion>15.3</LangVersion>
</PropertyGroup>
```

El número de versión puede ser cualquier versión del compilador Visual Basic a partir de 15,3. En lugar de codificar de forma rígida una versión específica del compilador, también puede especificar "latest" como valor de `LangVersion` para compilar con la versión más reciente del compilador Visual Basic instalada en el sistema.

Para obtener más información, vea [establecer la versión de lenguaje Visual Basic](../../../language-reference/configure-language-version.md).

En algunos casos, el compilador de Visual Basic no puede inferir el nombre del elemento de tupla a partir del nombre del candidato y solo se puede hacer referencia al campo de tupla usando su nombre predeterminado, como `Item1` , `Item2` , etc. Entre ellas se incluyen:

- El nombre del candidato es el mismo que el nombre de un miembro de la tupla, como `Item3` , `Rest` o `ToString` .

- El nombre del candidato está duplicado en la tupla.

Cuando se produce un error en la inferencia de nombre de campo, Visual Basic no genera un error del compilador ni se produce una excepción en tiempo de ejecución. En su lugar, se debe hacer referencia a los campos de tupla mediante sus nombres predefinidos, como `Item1` y `Item2` .

## <a name="tuples-versus-structures"></a>Tuplas frente a estructuras

Una tupla Visual Basic es un tipo de valor que es una instancia de uno de los tipos genéricos **System. ValueTuple** . Por ejemplo, la `holiday` tupla definida en el ejemplo anterior es una instancia de la <xref:System.ValueTuple%603> estructura. Está diseñado para ser un contenedor ligero para los datos. Dado que la tupla pretende facilitar la creación de un objeto con varios elementos de datos, carece de algunas de las características que puede tener una estructura personalizada. Se incluyen los siguientes:

- Miembros personalizados. No puede definir sus propias propiedades, métodos o eventos para una tupla.

- Valida. No se pueden validar los datos asignados a los campos.

- Inmutabilidad. Visual Basic tuplas son mutables. En cambio, una estructura personalizada le permite controlar si una instancia es modificable o inmutable.

Si los miembros personalizados, la validación de propiedades y campos o la inmutabilidad son importantes, debe utilizar la instrucción Visual Basic [Structure](../../../language-reference/statements/structure-statement.md) para definir un tipo de valor personalizado.

Una tupla Visual Basic hereda los miembros de su tipo **ValueTuple** . Además de sus campos, se incluyen los siguientes métodos:

| Método | Descripción |
| ---|---|
| CompareTo | Compara la tupla actual con otra tupla con el mismo número de elementos. |
| es igual a | Determina si la tupla actual es igual a otra tupla u objeto. |
| GetHashCode | Calcula el código hash de la instancia actual. |
| ToString | Devuelve la representación de cadena de esta tupla, que tiene la forma `(Item1, Item2...)` , donde `Item1` y `Item2` representan los valores de los campos de la tupla. |

Además, los tipos de **ValueTuple** implementan <xref:System.Collections.IStructuralComparable> <xref:System.Collections.IStructuralEquatable> interfaces e, que permiten definir comparadores personalizados.

## <a name="assignment-and-tuples"></a>Asignación y tuplas

Visual Basic admite la asignación entre tipos de tupla que tienen el mismo número de campos. Los tipos de campo se pueden convertir si se cumple una de las siguientes condiciones:

- El campo de origen y de destino son del mismo tipo.

- Se define una conversión de ampliación (o implícita) del tipo de origen al tipo de destino.

- `Option Strict` es `On` , y se define una conversión de restricción (o explícita) del tipo de origen al tipo de destino. Esta conversión puede producir una excepción si el valor de origen está fuera del intervalo del tipo de destino.

Otras conversiones no se tienen en cuenta para las asignaciones. Echemos un vistazo a los tipos de asignaciones que se permiten entre los tipos de tupla.

Tenga en cuenta estas variables que se usan en los ejemplos siguientes:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

Las dos primeras variables, `unnamed` y `anonymous` , no tienen nombres semánticos proporcionados para los campos. Los nombres de campo son los valores predeterminados `Item1` y `Item2` . Las dos últimas variables `named` y `differentName` tienen nombres de campo semánticos. Tenga en cuenta que estas dos tuplas tienen nombres diferentes para los campos.

Las cuatro de estas tuplas tienen el mismo número de campos (denominado "aridad") y los tipos de esos campos son idénticos. Por consiguiente, todas estas asignaciones funcionan:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

Observe que los nombres de las tuplas no se asignan. Los valores de los campos se asignan según el orden de los campos de la tupla.

Por último, observe que podemos asignar la `named` tupla a la `conversion` tupla, aunque el primer campo de `named` sea `Integer` , y el primer campo de `conversion` sea un `Long` . Esta asignación se realiza correctamente porque la conversión `Integer` de a `Long` es una conversión de ampliación.

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

Un método solo puede devolver un valor. Sin embargo, a menudo le gustaría que una llamada al método devuelva varios valores. Hay varias maneras de solucionar esta limitación:

- Puede crear una clase o estructura personalizada cuyas propiedades o campos representen los valores devueltos por el método. Por lo tanto, es una solución pesada; requiere que se defina un tipo personalizado cuyo único propósito sea recuperar valores de una llamada al método.

- Puede devolver un valor único desde el método y devolver los valores restantes pasándolos por referencia al método. Esto implica la sobrecarga de crear instancias de una variable y los riesgos que sobrescriben involuntariamente el valor de la variable que se pasa por referencia.

- Puede usar una tupla, que proporciona una solución ligera para recuperar varios valores devueltos.

Por ejemplo, los métodos **TryParse** en .net devuelven un `Boolean` valor que indica si la operación de análisis se realizó correctamente. El resultado de la operación de análisis se devuelve en una variable que se pasa por referencia al método. Normalmente, una llamada a un método de análisis como se <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> parece a lo siguiente:

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#1)]

Podemos devolver una tupla a partir de la operación de análisis si encapsulamos la llamada al <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> método en nuestro propio método. En el ejemplo siguiente, `NumericLibrary.ParseInteger` llama al <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> método y devuelve una tupla con nombre con dos elementos.

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

Después, puede llamar al método con código como el siguiente:

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

## <a name="visual-basic-tuples-and-tuples-in-the-net-framework"></a>Visual Basic tuplas y tuplas en el .NET Framework

Una tupla Visual Basic es una instancia de uno de los tipos genéricos **System. ValueTuple** , que se introdujeron en el .NET Framework 4,7. El .NET Framework también incluye un conjunto de clases genéricas **System. Tuple** . Sin embargo, estas clases difieren de las tuplas Visual Basic y los tipos genéricos **System. ValueTuple** de varias maneras:

- Los elementos de las clases de **tupla** son propiedades denominadas `Item1` , `Item2` , etc. En Visual Basic tuplas y los tipos **ValueTuple** , los elementos de tupla son campos.

- No se pueden asignar nombres descriptivos a los elementos de una instancia de **tupla** o de una instancia de **ValueTuple** . Visual Basic permite asignar nombres que comunican el significado de los campos.

- Las propiedades de una instancia de **tupla** son de solo lectura; las tuplas son inmutables. En Visual Basic tuplas y los tipos **ValueTuple** , los campos de tupla son de lectura y escritura. las tuplas son mutables.

- Los tipos de **tupla** genéricos son tipos de referencia. El uso de estos tipos de **tupla** implica la asignación de objetos. En rutas de acceso activas, esto puede suponer un importante impacto en el rendimiento de la aplicación. Visual Basic tuplas y los tipos **ValueTuple** son tipos de valor.

Los métodos de extensión de la clase facilitan la <xref:System.TupleExtensions> conversión entre Visual Basic tuplas y objetos de **tupla** de .net. El método **ToTuple** convierte una tupla Visual Basic en un objeto de **tupla** de .net y el método **ToValueTuple** convierte un objeto de **tupla** de .net en una tupla Visual Basic.

En el ejemplo siguiente se crea una tupla, se convierte en un objeto de **tupla** de .net y se vuelve a convertir en una tupla Visual Basic. A continuación, en el ejemplo se compara esta tupla con la original para asegurarse de que son iguales.

[!code-vb[Convert](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple2.vb#1)]

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje Visual Basic](index.md)

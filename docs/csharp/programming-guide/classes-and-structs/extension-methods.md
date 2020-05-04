---
title: 'Métodos de extensión: Guía de programación de C#'
ms.date: 03/19/2020
helpviewer_keywords:
- methods [C#], adding to existing types
- extension methods [C#]
- methods [C#], extension
ms.assetid: 175ce3ff-9bbf-4e64-8421-faeb81a0bb51
ms.openlocfilehash: fc816123134995b753beda0a6f281133d6ddd691
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "82506823"
---
# <a name="extension-methods-c-programming-guide"></a>Métodos de extensión (Guía de programación de C#)

Los métodos de extensión permiten "agregar" métodos a los tipos existentes sin crear un nuevo tipo derivado, recompilar o modificar de otra manera el tipo original. Los métodos de extensión son métodos estáticos, pero se les llama como si fueran métodos de instancia en el tipo extendido. En el caso del código de cliente escrito en C#, F# y Visual Basic, no existe ninguna diferencia aparente entre llamar a un método de extensión y llamar a los métodos definidos en un tipo.

Los métodos de extensión más comunes son los operadores de consulta LINQ estándar, que agregan funciones de consulta a los tipos <xref:System.Collections.IEnumerable?displayProperty=nameWithType> y <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> existentes. Para usar los operadores de consulta estándar, inclúyalos primero en el ámbito con una directiva `using System.Linq`. A partir de ese momento, cualquier tipo que implemente <xref:System.Collections.Generic.IEnumerable%601> parecerá tener métodos de instancia como <xref:System.Linq.Enumerable.GroupBy%2A>, <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Average%2A>, etc. Puede ver estos métodos adicionales en la finalización de instrucciones de IntelliSense al escribir "punto" después de una instancia de un tipo <xref:System.Collections.Generic.IEnumerable%601>, como <xref:System.Collections.Generic.List%601> o <xref:System.Array>.

### <a name="orderby-example"></a>Ejemplo de OrderBy

En el ejemplo siguiente se muestra cómo llamar al método `OrderBy` de operador de consulta estándar en una matriz de enteros. La expresión entre paréntesis es una expresión lambda. Muchos operadores de consulta estándar toman expresiones lambda como parámetros, pero no es un requisito para los métodos de extensión. Para obtener más información, vea [Expresiones lambda](../statements-expressions-operators/lambda-expressions.md).

[!code-csharp[csProgGuideExtensionMethods#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#3)]

Los métodos de extensión se definen como métodos estáticos, pero se les llama usando la sintaxis de método de instancia. Su primer parámetro especifica en qué tipo funciona el método. El parámetro va precedido del modificador [this](../../language-reference/keywords/this.md). Los métodos de extensión únicamente se encuentran dentro del ámbito cuando el espacio de nombres se importa explícitamente en el código fuente con una directiva `using`.

En el ejemplo siguiente se muestra un método de extensión definido para la clase <xref:System.String?displayProperty=nameWithType>. Se define dentro de una clase estática no anidada y no genérica:

[!code-csharp[csProgGuideExtensionMethods#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#4)]

El método de extensión `WordCount` se puede incluir en el ámbito con esta directiva `using`:

```csharp
using ExtensionMethods;
```

También se le puede llamar desde una aplicación con esta sintaxis:

```csharp
string s = "Hello Extension Methods";
int i = s.WordCount();
```

El método de extensión se invoca en el código con la sintaxis de método de instancia. El lenguaje intermedio (IL) generado por el compilador convierte el código en una llamada en el método estático. El principio de encapsulación no se infringe realmente. Los métodos de extensión no pueden tener acceso a las variables privadas en el tipo que extienden.

Para obtener más información, vea [Procedimiento para implementar e invocar un método de extensión personalizado](./how-to-implement-and-call-a-custom-extension-method.md).

En general, probablemente se llamará a métodos de extensión con mucha más frecuencia de la que se implementarán métodos propios. Dado que los métodos de extensión se llaman con la sintaxis de método de instancia, no se requieren conocimientos especiales para usarlos desde el código de cliente. Para habilitar los métodos de extensión para un tipo determinado, basta con agregar una directiva `using` para el espacio de nombres en el que se definen los métodos. Por ejemplo, para usar los operadores de consulta estándar, agregue esta directiva `using` al código:

```csharp
using System.Linq;
```

(Puede que haya que agregar también una referencia a System.Core.dll). Observará que los operadores de consulta estándar aparecen ahora en IntelliSense como métodos adicionales disponibles para la mayoría de los tipos <xref:System.Collections.Generic.IEnumerable%601>.

## <a name="binding-extension-methods-at-compile-time"></a>Enlazar métodos de extensión en tiempo de compilación

Se pueden usar métodos de extensión para ampliar una clase o interfaz, pero no para invalidarlas. Nunca se llamará a un método de extensión con el mismo nombre y signatura que un método de interfaz o clase. En tiempo de compilación, los métodos de extensión siempre tienen menos prioridad que los métodos de instancia definidos en el propio tipo. En otras palabras, si un tipo tiene un método denominado `Process(int i)` y hay un método de extensión con la misma signatura, el compilador siempre se enlazará al método de instancia. Cuando el compilador encuentra una invocación de método, primero busca una coincidencia en los métodos de instancia del tipo. Si no la hay, buscará cualquier método de extensión definido para el tipo y se enlazará al primer método de extensión que encuentre. En el ejemplo siguiente se muestra cómo determina el compilador a qué método de extensión o de instancia enlazarse.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestran las reglas que el compilador de C# sigue para determinar si se va a enlazar una llamada a método a un método de instancia del tipo o a un método de extensión. La clase estática `Extensions` contiene métodos de extensión definidos para cualquier tipo que implemente `IMyInterface`. Las clases `A`, `B` y `C` implementan la interfaz.

Nunca se llama al método de extensión `MethodB`, porque su nombre y signatura coinciden exactamente con los métodos ya implementados por las clases.

Si el compilador no encuentra un método de instancia con una signatura coincidente, se enlazará a un método de extensión coincidente, si existe.

[!code-csharp[csProgGuideExtensionMethods#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#5)]

## <a name="common-usage-patterns"></a>Patrones de uso común

### <a name="collection-functionality"></a>Funcionalidad de colección

En el pasado, era habitual crear "Clases de colección" que implementaban la interfaz <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> para un tipo especificado e incluían una funcionalidad que actuaba en colecciones de ese tipo. Aunque no hay ningún problema con la creación de este tipo de objeto de colección, se puede lograr la misma funcionalidad mediante una extensión en <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>. Las extensiones tienen la ventaja de permitir que se llame a la funcionalidad desde cualquier colección como <xref:System.Array?displayProperty=nameWithType> o <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> que implementa <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> en ese tipo. Encontrará un ejemplo de esto mediante una matriz de Int32 [anteriormente en este artículo](#orderby-example).

### <a name="layer-specific-functionality"></a>Funcionalidad específica de la capa

Al usar Onion Architecture (Arquitectura cebolla) u otro diseño de la aplicación por niveles, es habitual tener un conjunto de entidades de dominio u objetos de transferencia de datos que se pueden usar para la comunicación entre los límites de la aplicación. Por regla general, estos objetos no contienen ninguna funcionalidad o contienen únicamente una funcionalidad mínima que se aplica a todas las capas de la aplicación. Los métodos de extensión se pueden usar para agregar una funcionalidad específica de cada capa de la aplicación sin cargar el objeto con métodos no necesarios o deseados en otras capas.

```aspx-csharp
public class DomainEntity
{
    public int Id { get; set; }
    public string FirstName { get; set; }
    public string LastName { get; set; }
}

static class DomainEntityExtensions
{
    static string FullName(this DomainEntity value)
        => $"{value.FirstName} {value.LastName}";
}
```

### <a name="extending-predefined-types"></a>Ampliación de tipos predefinidos

En lugar de crear nuevos objetos cuando es necesario crear una funcionalidad reutilizable, a menudo podemos ampliar un tipo existente como un tipo CLR o de .NET Framework. Como ejemplo, si no usamos métodos de extensión, podemos crear una clase `Engine` o `Query` para ejecutar una consulta en un servidor SQL Server al que se puede llamar desde varias ubicaciones en nuestro código. Sin embargo, en su lugar, podemos ampliar la clase <xref:System.Data.SqlClient.SqlConnection?displayProperty=nameWithType> mediante métodos de extensión para realizar esa consulta desde cualquier lugar en el que tengamos una conexión a un servidor SQL Server. Otros ejemplos podrían ser la adición de una funcionalidad común a la clase <xref:System.String?displayProperty=nameWithType>, la ampliación de las funcionalidades de procesamiento de datos de los objetos <xref:System.IO.File?displayProperty=nameWithType> y <xref:System.IO.Stream?displayProperty=nameWithType>, y los objetos <xref:System.Exception?displayProperty=nameWithType> para una funcionalidad de control de errores específica. Solo su imaginación y sentido común limitan estos tipos de casos de uso.

La ampliación de tipos predefinidos puede ser difícil con los tipos `struct`, ya que se pasan en función del valor a los métodos. Eso significa que los cambios en la estructura se realizan en una copia de la misma. Esos cambios dejarán de verse una vez que se salga del método de extensión. A partir de C# 7.2, puede agregar el modificador `ref` al primer argumento de un método de extensión. La adición del modificador `ref` significa que el primer argumento se pasa por referencia. Esto le permite escribir métodos de extensión que cambian el estado de la estructura que se amplía.

## <a name="general-guidelines"></a>Instrucciones generales

Aunque sigue considerándose preferible agregar la funcionalidad modificando un código del objeto o derivando un nuevo tipo siempre que sea razonable y posible hacerlo, los métodos de extensión se han convertido en una opción fundamental para crear una funcionalidad reutilizable en todo el ecosistema .NET. Para esas ocasiones en las que no cuente con el control del origen original, si un objeto derivado es inadecuado o imposible, o la funcionalidad no se debe exponer más allá de su ámbito aplicable, los métodos de extensión son una opción excelente.

Para obtener más información sobre los tipos derivados, consulte [Herencia](./inheritance.md).

Al usar un método de extensión para ampliar un tipo cuyo código fuente no está bajo su control, se corre el riesgo de que un cambio en la implementación del tipo interrumpa el método de extensión.

Si se implementan métodos de extensión para un tipo determinado, recuerde los puntos siguientes:

- Nunca se llamará a un método de extensión si tiene la misma signatura que un método definido en el tipo.
- Los métodos de extensión se incluyen en el ámbito en el nivel de espacio de nombres. Por ejemplo, si se tienen varias clases estáticas que contienen métodos de extensión en un único espacio de nombres denominado `Extensions`, la directiva `using Extensions;` los incluirá a todos en el ámbito.

Para una biblioteca de clases ya implementada, no deben usarse métodos de extensión para evitar incrementar el número de versión de un ensamblado. Si desea agregar una funcionalidad significativa a una biblioteca de la que es propietario del código fuente, deben seguirse las instrucciones de .NET Framework estándar para el control de versiones de ensamblado. Para obtener más información, vea [Versiones de los ensamblados](../../../standard/assembly/versioning.md).

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Ejemplos de programación en paralelo (incluyen numerosos métodos de extensión de ejemplo)](/samples/browse/?products=dotnet-core%2Cdotnet-standard&term=parallel)
- [Expresiones lambda](../statements-expressions-operators/lambda-expressions.md)
- [Información general sobre operadores de consulta estándar](../concepts/linq/standard-query-operators-overview.md)
- [Conversion rules for Instance parameters and their impact](https://docs.microsoft.com/archive/blogs/sreekarc/conversion-rules-for-instance-parameters-and-their-impact) (Reglas de conversión para los parámetros de instancia y su impacto)
- [Extension methods Interoperability between languages](https://docs.microsoft.com/archive/blogs/sreekarc/extension-methods-interoperability-between-languages) (Interoperabilidad de los métodos de extensión entre lenguajes)
- [Extension methods and Curried Delegates](https://docs.microsoft.com/archive/blogs/sreekarc/extension-methods-and-curried-delegates) (Métodos de extensión y delegados currificados)
- [Extension method Binding and Error reporting](https://docs.microsoft.com/archive/blogs/sreekarc/extension-method-binding-and-error-reporting) (Enlazar métodos de extensión y notificación de errores)

---
title: 'Constructores de instancias: Guía de programación de C#'
description: Los constructores de instancias de C# crean e inicializan variables miembro de instancia cuando se usa la expresión nueva para crear un objeto de una clase.
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], instance constructors
- instance constructors [C#]
ms.assetid: 24663779-c1e5-4af4-a942-ca554e4c542d
ms.openlocfilehash: 0f9372c744a7bdfab44c8cd020a4378cff729c57
ms.sourcegitcommit: 8299abfbd5c49b596d61f1e4d09bc6b8ba055b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "98899040"
---
# <a name="instance-constructors-c-programming-guide"></a>Constructores de instancias (Guía de programación de C#)

Los constructores de instancias se usan para crear e inicializar las variables miembro de instancia cuando se usa la expresión [new](../../language-reference/operators/new-operator.md) para crear un objeto de una [clase](../../language-reference/keywords/class.md). Para inicializar una clase [estática](../../language-reference/keywords/static.md), o variables estáticas en una clase no estática, se define un constructor estático. Para obtener más información, vea [Constructores estáticos (Guía de programación de C#)](./static-constructors.md).  
  
 En el siguiente ejemplo se muestra un constructor de instancias:  
  
 [!code-csharp[CoordsWithParameterlessConstructorOnly#1](snippets/instance-constructors/coords/Program.cs#1)]
  
> [!NOTE]
> Para mayor claridad, esta clase contiene campos públicos. El uso de campos públicos no es una práctica de programación recomendada porque permite que cualquier método de cualquier parte de un programa obtenga acceso sin restricciones ni comprobaciones a los mecanismos internos de un objeto. Los miembros de datos generalmente deberían ser privados y solo se debería tener acceso a ellos a través de las propiedades y métodos de la clase.  
  
 Se llama a este constructor de instancias cada vez que se crea un objeto basado en la clase `Coords`. Un constructor como este, que no toma ningún argumento, se denomina *constructor sin parámetros*. Pero a menudo resulta útil proporcionar constructores adicionales. Por ejemplo, se puede agregar un constructor a la clase `Coords` que permita especificar los valores iniciales de los miembros de datos:  
  
 [!code-csharp[TwoArgumentConstructor#2](snippets/instance-constructors/coords/Program.cs#2)]
  
 Esto permite crear objetos `Coords` con valores iniciales predeterminados o específicos, como este:  
  
 [!code-csharp[InstantiatingCoords#3](snippets/instance-constructors/coords/Program.cs#3)]
  
 Si una clase no tiene un constructor, se genera automáticamente un constructor sin parámetros y los valores predeterminados se usan para inicializar los campos del objeto. Por ejemplo, un [int](../../language-reference/builtin-types/integral-numeric-types.md) se inicializa en 0. Para obtener información sobre los valores predeterminados de los tipos, vea [Valores predeterminados de los tipos de C#](../../language-reference/builtin-types/default-values.md). Por tanto, dado que el constructor sin parámetros de la clase `Coords` inicializa todos los miembros de datos en cero, se puede quitar por completo sin cambiar el funcionamiento de la clase. Más adelante en este tema se proporciona un ejemplo completo del uso de varios constructores en el Ejemplo 1 y en el Ejemplo 2 se proporciona un ejemplo de un constructor generado automáticamente.  
  
 Los constructores de instancias también se pueden usar para llamar a los constructores de instancias de las clases base. El constructor de clase puede invocar el constructor de la clase base a través del inicializador, como sigue:  
  
```csharp
class Circle : Shape
{
    public Circle(double radius)
        : base(radius, 0)
    {
    }
}
```
  
 En este ejemplo, la clase `Circle` pasa valores que representan el radio y el alto al constructor proporcionado por `Shape` desde el que se deriva `Circle`. Un ejemplo completo del uso de `Shape` y `Circle` aparece en este tema en el Ejemplo 3.  
  
## <a name="example-1"></a>Ejemplo 1  

 En el ejemplo siguiente se muestra una clase con dos constructores de clase, uno sin argumentos y uno con dos argumentos.  
  
 [!code-csharp[CoordsFullExample#4](snippets/instance-constructors/coords/Program.cs#4)]
  
## <a name="example-2"></a>Ejemplo 2  

 En este ejemplo, la clase `Person` no tiene ningún constructor, en cuyo caso, se proporciona automáticamente un constructor sin parámetros y los campos se inicializan en sus valores predeterminados.  
  
 [!code-csharp[Person](snippets/instance-constructors/person/Program.cs)]
  
 Observe que el valor predeterminado de `age` es `0` y el valor predeterminado de `name` es `null`.
  
## <a name="example-3"></a>Ejemplo 3  

 En el ejemplo siguiente se muestra cómo usar el inicializador de la clase base. La clase `Circle` se deriva de la clase general `Shape` y la clase `Cylinder` se deriva de la clase `Circle`. En cada clase derivada, el constructor usa su inicializador de clase base.  
  
 [!code-csharp[ShapesExample](snippets/instance-constructors/shapes/Program.cs)]
  
 Para obtener más ejemplos sobre cómo invocar los constructores de clase base, vea [virtual](../../language-reference/keywords/virtual.md), [override](../../language-reference/keywords/override.md) y [base](../../language-reference/keywords/base.md).  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Clases y structs](./index.md)
- [Constructores](./constructors.md)
- [Finalizadores](./destructors.md)
- [static](../../language-reference/keywords/static.md)

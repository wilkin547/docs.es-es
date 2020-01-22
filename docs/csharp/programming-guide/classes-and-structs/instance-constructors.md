---
title: 'Constructores de instancias: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], instance constructors
- instance constructors [C#]
ms.assetid: 24663779-c1e5-4af4-a942-ca554e4c542d
ms.openlocfilehash: 621b8ca7510b0b9916c9c46f201ff77402c3c655
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964730"
---
# <a name="instance-constructors-c-programming-guide"></a>Constructores de instancias (Guía de programación de C#)

Los constructores de instancias se usan para crear e inicializar las variables miembro de instancia cuando se usa la expresión [new](../../language-reference/operators/new-operator.md) para crear un objeto de una [clase](../../language-reference/keywords/class.md). Para inicializar una clase [estática](../../language-reference/keywords/static.md), o variables estáticas en una clase no estática, se define un constructor estático. Para obtener más información, vea [Constructores estáticos (Guía de programación de C#)](./static-constructors.md).  
  
 En el siguiente ejemplo se muestra un constructor de instancias:  
  
 [!code-csharp[csProgGuideObjects#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#5)]  
  
> [!NOTE]
> Para mayor claridad, esta clase contiene campos públicos. El uso de campos públicos no es una práctica de programación recomendada porque permite que cualquier método de cualquier parte de un programa obtenga acceso sin restricciones ni comprobaciones a los mecanismos internos de un objeto. Los miembros de datos generalmente deberían ser privados y solo se debería tener acceso a ellos a través de las propiedades y métodos de la clase.  
  
 Se llama a este constructor de instancias cada vez que se crea un objeto basado en la clase `Coords`. Un constructor como este, que no toma ningún argumento, se denomina *constructor sin parámetros*. Pero a menudo resulta útil proporcionar constructores adicionales. Por ejemplo, se puede agregar un constructor a la clase `Coords` que permita especificar los valores iniciales de los miembros de datos:  
  
 [!code-csharp[csProgGuideObjects#76](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#76)]  
  
 Esto permite crear objetos `Coords` con valores iniciales predeterminados o específicos, como este:  
  
 [!code-csharp[csProgGuideObjects#77](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#77)]  
  
 Si una clase no tiene un constructor, se genera automáticamente un constructor sin parámetros y los valores predeterminados se usan para inicializar los campos del objeto. Por ejemplo, un [int](../../language-reference/builtin-types/integral-numeric-types.md) se inicializa en 0. Para obtener información sobre los valores predeterminados de los tipos, vea [Valores predeterminados de los tipos de C#](../../language-reference/builtin-types/default-values.md). Por tanto, dado que el constructor sin parámetros de la clase `Coords` inicializa todos los miembros de datos en cero, se puede quitar por completo sin cambiar el funcionamiento de la clase. Más adelante en este tema se proporciona un ejemplo completo del uso de varios constructores en el Ejemplo 1 y en el Ejemplo 2 se proporciona un ejemplo de un constructor generado automáticamente.  
  
 Los constructores de instancias también se pueden usar para llamar a los constructores de instancias de las clases base. El constructor de clase puede invocar el constructor de la clase base a través del inicializador, como sigue:  
  
 [!code-csharp[csProgGuideObjects#78](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#78)]  
  
 En este ejemplo, la clase `Circle` pasa valores que representan el radio y el alto al constructor proporcionado por `Shape` desde el que se deriva `Circle`. Un ejemplo completo del uso de `Shape` y `Circle` aparece en este tema en el Ejemplo 3.  
  
## <a name="example-1"></a>Ejemplo 1  
 En el ejemplo siguiente se muestra una clase con dos constructores de clase, uno sin argumentos y uno con dos argumentos.  
  
 [!code-csharp[csProgGuideObjects#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#4)]  
  
## <a name="example-2"></a>Ejemplo 2  
 En este ejemplo, la clase `Person` no tiene ningún constructor, en cuyo caso, se proporciona automáticamente un constructor sin parámetros y los campos se inicializan en sus valores predeterminados.  
  
 [!code-csharp[csProgGuideObjects#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#8)]  
  
 Observe que el valor predeterminado de `age` es `0` y el valor predeterminado de `name` es `null`.
  
## <a name="example-3"></a>Ejemplo 3  
 En el ejemplo siguiente se muestra cómo usar el inicializador de la clase base. La clase `Circle` se deriva de la clase general `Shape` y la clase `Cylinder` se deriva de la clase `Circle`. En cada clase derivada, el constructor usa su inicializador de clase base.  
  
 [!code-csharp[csProgGuideObjects#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#9)]  
  
 Para obtener más ejemplos sobre cómo invocar los constructores de clase base, vea [virtual](../../language-reference/keywords/virtual.md), [override](../../language-reference/keywords/override.md) y [base](../../language-reference/keywords/base.md).  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Clases y structs](./index.md)
- [Constructores](./constructors.md)
- [Finalizadores](./destructors.md)
- [static](../../language-reference/keywords/static.md)

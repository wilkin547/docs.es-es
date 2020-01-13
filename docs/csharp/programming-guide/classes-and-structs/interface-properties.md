---
title: 'Propiedades de interfaces: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: ff892a35f4be6600c00bc0c72c2f789ef6eb4408
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705540"
---
# <a name="interface-properties-c-programming-guide"></a>Propiedades de interfaces (Guía de programación de C#)

Las propiedades se pueden declarar en una [interfaz](../../language-reference/keywords/interface.md). A continuación se muestra un ejemplo de un descriptor de acceso de propiedad de interfaz:

[!code-csharp[csProgGuideProperties#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#14)]

El descriptor de acceso de una propiedad de interfaz no tiene un cuerpo. Por tanto, el propósito de los descriptores de acceso es indicar si la propiedad es de lectura y escritura, de solo lectura o de solo escritura.

## <a name="example"></a>Ejemplo

En este ejemplo, la interfaz `IEmployee` tiene una propiedad de lectura y escritura, `Name`, y una propiedad de solo lectura, `Counter`. La clase `Employee` implementa la interfaz `IEmployee` y usa estas dos propiedades. El programa lee el nombre de un nuevo empleado y el número actual de empleados y muestra el nombre del empleado y el número de empleados calculado.

Puede usar el nombre completo de la propiedad, que hace referencia a la interfaz en la que se declara el miembro. Por ejemplo:

[!code-csharp[csProgGuideProperties#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#16)]

Se denomina [implementación de interfaz explícita](../interfaces/explicit-interface-implementation.md). Por ejemplo, si la clase `Employee` implementa dos interfaces `ICitizen` y `IEmployee`, y ambas interfaces tienen la propiedad `Name`, la implementación del miembro de interfaz explícita será necesaria. Es decir, la siguiente declaración de propiedad:

[!code-csharp[csProgGuideProperties#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#16)]

implementa la propiedad `Name` en la interfaz `IEmployee`, mientras que la siguiente declaración:

[!code-csharp[csProgGuideProperties#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#17)]

implementa la propiedad `Name` en la interfaz `ICitizen`.

[!code-csharp[csProgGuideProperties#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#15)]

**`210 Hazem Abolrous`**

## <a name="sample-output"></a>Resultados de ejemplo

```console
Enter number of employees: 210
Enter the name of the new employee: Hazem Abolrous
The employee information:
Employee number: 211
Employee name: Hazem Abolrous
```

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Propiedades](./properties.md)
- [Utilizar propiedades](./using-properties.md)
- [Comparación entre propiedades e indizadores](../indexers/comparison-between-properties-and-indexers.md)
- [Indizadores](../indexers/index.md)
- [Interfaces](../interfaces/index.md)

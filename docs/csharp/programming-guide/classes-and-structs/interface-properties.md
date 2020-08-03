---
title: 'Propiedades de interfaces: Guía de programación de C#'
description: Las propiedades se pueden declarar en una interfaz de C#. En este ejemplo se declara un descriptor de acceso de propiedad de interfaz.
ms.date: 01/31/2020
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: 920381ae804a6a968bfd667171269377f3d7e448
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864974"
---
# <a name="interface-properties-c-programming-guide"></a>Propiedades de interfaces (Guía de programación de C#)

Las propiedades se pueden declarar en una [interfaz](../../language-reference/keywords/interface.md). En el ejemplo siguiente se declara un descriptor de acceso de propiedad de interfaz:

[!code-csharp[DeclareProperties](~/samples/snippets/csharp/interfaces/properties.cs#DeclareInterfaceProperties)]

Normalmente, las propiedades de interfaz no tienen un cuerpo. Los descriptores de acceso indican si la propiedad es de lectura y escritura, de solo lectura o de solo escritura. A diferencia de las clases y las estructuras, la declaración de los descriptores de acceso sin cuerpo no declara una [propiedad implementada automáticamente](auto-implemented-properties.md). A partir de C# 8.0, una interfaz puede definir una implementación predeterminada para los miembros, incluidas las propiedades. La definición de una implementación predeterminada para una propiedad en una interfaz es poco frecuente, ya que las interfaces no pueden definir campos de datos de instancia.

## <a name="example"></a>Ejemplo

En este ejemplo, la interfaz `IEmployee` tiene una propiedad de lectura y escritura, `Name`, y una propiedad de solo lectura, `Counter`. La clase `Employee` implementa la interfaz `IEmployee` y usa estas dos propiedades. El programa lee el nombre de un nuevo empleado y el número actual de empleados y muestra el nombre del empleado y el número de empleados calculado.

Puede usar el nombre completo de la propiedad, que hace referencia a la interfaz en la que se declara el miembro. Por ejemplo:

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

En el ejemplo anterior se muestra la [implementación de interfaz explícita](../interfaces/explicit-interface-implementation.md). Por ejemplo, si la clase `Employee` implementa dos interfaces `ICitizen` y `IEmployee`, y ambas interfaces tienen la propiedad `Name`, la implementación del miembro de interfaz explícita será necesaria. Es decir, la siguiente declaración de propiedad:

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

implementa la propiedad `Name` en la interfaz `IEmployee`, mientras que la siguiente declaración:

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#CitizenImplementation)]

implementa la propiedad `Name` en la interfaz `ICitizen`.

[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#PropertyExample)]
[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#UseProperty)]

**`210 Hazem Abolrous`**

## <a name="sample-output"></a>Salida de ejemplo

```console
Enter number of employees: 210
Enter the name of the new employee: Hazem Abolrous
The employee information:
Employee number: 211
Employee name: Hazem Abolrous
```

## <a name="see-also"></a>Consulte también

- [Guía de programación de C#](../index.md)
- [Propiedades](./properties.md)
- [Utilizar propiedades](./using-properties.md)
- [Comparación entre propiedades e indizadores](../indexers/comparison-between-properties-and-indexers.md)
- [Indizadores](../indexers/index.md)
- [Interfaces](../interfaces/index.md)

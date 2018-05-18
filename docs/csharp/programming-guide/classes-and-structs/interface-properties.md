---
title: Propiedades de interfaces (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: bfa03c7ebe82f3f6a03666d908a5fa9d4e386172
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="interface-properties-c-programming-guide"></a>Propiedades de interfaces (Guía de programación de C#)
Las propiedades se pueden declarar en una [interfaz](../../../csharp/language-reference/keywords/interface.md). A continuación tiene un ejemplo de un descriptor de acceso de indexador de interfaz:  
  
 [!code-csharp[csProgGuideProperties#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_1.cs)]  
  
 El descriptor de acceso de una propiedad de interfaz no tiene un cuerpo. Por tanto, el propósito de los descriptores de acceso es indicar si la propiedad es de lectura y escritura, de solo lectura o de solo escritura.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, la interfaz `IEmployee` tiene una propiedad de lectura y escritura, `Name`, y una propiedad de solo lectura, `Counter`. La clase `Employee` implementa la interfaz `IEmployee` y usa estas dos propiedades. El programa lee el nombre de un nuevo empleado y el número actual de empleados y muestra el nombre del empleado y el número de empleados calculado.  
  
 Puede usar el nombre completo de la propiedad, que hace referencia a la interfaz en la que se declara el miembro. Por ejemplo:  
  
 [!code-csharp[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]  
  
 Se denomina [implementación de interfaz explícita](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md). Por ejemplo, si la clase `Employee` implementa dos interfaces `ICitizen` y `IEmployee`, y ambas interfaces tienen la propiedad `Name`, la implementación del miembro de interfaz explícita será necesaria. Es decir, la siguiente declaración de propiedad:  
  
 [!code-csharp[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]  
  
 implementa la propiedad `Name` en la interfaz `IEmployee`, mientras que la siguiente declaración:  
  
 [!code-csharp[csProgGuideProperties#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_3.cs)]  
  
 implementa la propiedad `Name` en la interfaz `ICitizen`.  
  
 [!code-csharp[csProgGuideProperties#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_4.cs)]  
  
  **`210 Hazem Abolrous`**    
## <a name="sample-output"></a>Resultados del ejemplo  
 `Enter number of employees: 210`  
  
 `Enter the name of the new employee: Hazem Abolrous`  
  
 `The employee information:`  
  
 `Employee number: 211`  
  
 `Employee name: Hazem Abolrous`  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md)  
 [Utilizar propiedades](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
 [Comparación entre propiedades e indizadores](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
 [Indizadores](../../../csharp/programming-guide/indexers/index.md)  
 [Interfaces](../../../csharp/programming-guide/interfaces/index.md)

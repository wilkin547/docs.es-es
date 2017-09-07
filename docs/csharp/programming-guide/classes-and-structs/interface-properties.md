---
title: "Propiedades de interfaces (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2b76cdc4e8419b08dcd95c3711eaead5513ae1d9
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="interface-properties-c-programming-guide"></a>Propiedades de interfaces (Guía de programación de C#)
Las propiedades se pueden declarar en una [interfaz](../../../csharp/language-reference/keywords/interface.md). A continuación tiene un ejemplo de un descriptor de acceso de indexador de interfaz:  
  
 [!code-cs[csProgGuideProperties#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_1.cs)]  
  
 El descriptor de acceso de una propiedad de interfaz no tiene un cuerpo. Por tanto, el propósito de los descriptores de acceso es indicar si la propiedad es de lectura y escritura, de solo lectura o de solo escritura.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, la interfaz `IEmployee` tiene una propiedad de lectura y escritura, `Name`, y una propiedad de solo lectura, `Counter`. La clase `Employee` implementa la interfaz `IEmployee` y usa estas dos propiedades. El programa lee el nombre de un nuevo empleado y el número actual de empleados y muestra el nombre del empleado y el número de empleados calculado.  
  
 Puede usar el nombre completo de la propiedad, que hace referencia a la interfaz en la que se declara el miembro. Por ejemplo:  
  
 [!code-cs[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]  
  
 Se denomina [implementación de interfaz explícita](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md). Por ejemplo, si la clase `Employee` implementa dos interfaces `ICitizen` y `IEmployee`, y ambas interfaces tienen la propiedad `Name`, la implementación del miembro de interfaz explícita será necesaria. Es decir, la siguiente declaración de propiedad:  
  
 [!code-cs[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]  
  
 implementa la propiedad `Name` en la interfaz `IEmployee`, mientras que la siguiente declaración:  
  
 [!code-cs[csProgGuideProperties#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_3.cs)]  
  
 implementa la propiedad `Name` en la interfaz `ICitizen`.  
  
 [!code-cs[csProgGuideProperties#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_4.cs)]  
  
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
 [Indexers](../../../csharp/programming-guide/indexers/index.md)  (Indexadores)  
 [Interfaces](../../../csharp/programming-guide/interfaces/index.md)


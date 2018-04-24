---
title: Indizadores en interfaces (Guía de programación de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- indexers [C#], in interfaces
- accessors [C#], indexers
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 478920b5c1dea489db48caa48c045c4bd3da66ec
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="indexers-in-interfaces-c-programming-guide"></a>Indizadores en interfaces (Guía de programación de C#)
Los indexadores se pueden declarar en una [interfaz](../../../csharp/language-reference/keywords/interface.md). Los descriptores de acceso de los indexadores de interfaz se diferencian de los descriptores de acceso de los indexadores de [clase](../../../csharp/language-reference/keywords/class.md) de las maneras siguientes:  
  
-   Los descriptores de acceso de interfaz no usan modificadores.  
  
-   Un descriptor de acceso de interfaz no tiene un cuerpo.  
  
 Por tanto, el propósito del descriptor de acceso es indicar si el indexador es de lectura y escritura, de solo lectura o de solo escritura.  
  
 A continuación tiene un ejemplo de un descriptor de acceso de indexador de interfaz:  
  
 [!code-csharp[csProgGuideIndexers#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_1.cs)]  
  
 La firma de un indexador debe ser diferente de las firmas de los demás indexadores declarados en la misma interfaz.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo, se muestra cómo implementar indexadores de interfaz.  
  
 [!code-csharp[csProgGuideIndexers#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_2.cs)]  
  
 En el ejemplo anterior, podría usar la implementación del miembro de interfaz explícita al usar el nombre completo del miembro de interfaz. Por ejemplo:  
  
```  
public string ISomeInterface.this[int index]   
{   
}   
```  
  
 En cambio, el nombre completo solo es necesario para evitar la ambigüedad cuando la clase implementa más de una interfaz con la misma firma de indexador. Por ejemplo, si una clase `Employee` implementa dos interfaces `ICitizen` y `IEmployee` y ambas interfaces tienen la misma firma de indexador, la implementación del miembro de interfaz explícita es necesaria. Es decir, la siguiente declaración de indexador:  
  
```  
public string IEmployee.this[int index]   
{   
}   
```  
  
 implementa el indexador en la interfaz `IEmployee`, mientras que la siguiente declaración:  
  
```  
public string ICitizen.this[int index]
{   
}   
```  
  
 implementa el indexador en la interfaz `ICitizen`.  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Indizadores](../../../csharp/programming-guide/indexers/index.md)  
 [Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md)  
 [Interfaces](../../../csharp/programming-guide/interfaces/index.md)

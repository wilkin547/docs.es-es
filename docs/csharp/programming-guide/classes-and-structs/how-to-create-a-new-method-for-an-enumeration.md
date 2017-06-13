---
title: "Crear un método para una enumeración (Guía de programación de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- enumerations [C#]
- extension methods [C#], for enums
- enum extensibility [C#]
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
caps.latest.revision: 7
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: f015ec08818de7f99c5f16d237114c489edae1b6
ms.contentlocale: es-es
ms.lasthandoff: 06/12/2017

---
# <a name="how-to-create-a-new-method-for-an-enumeration-c-programming-guide"></a>Cómo: Crear un método nuevo para una enumeración (Guía de programación de C#)
Puede usar métodos de extensión para agregar funcionalidad a un tipo de enumeración concreto.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, la enumeración `Grades` representa las posibles calificaciones con letras que un alumno puede recibir en una clase. Un método de extensión denominado `Passing` se agrega al tipo `Grades` para que cada instancia de ese tipo "sepa" ahora si representa una calificación de aprobado o no.  
  
 [!code-cs[csProgGuideExtensionMethods#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-create-a-new-method-for-an-enumeration_1.cs)]  
  
 Tenga en cuenta que la clase `Extensions` también contiene una variable estática que se actualiza dinámicamente y que el valor devuelto del método de extensión refleja el valor actual de esa variable. Esto demuestra que, en segundo plano, los métodos de extensión se invocan directamente en la clase estática en donde se definen.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para ejecutar este código, cópielo y péguelo en un proyecto de aplicación de la consola de Visual C# creado en [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)]. De forma predeterminada, este proyecto tiene como destino la versión 3.5 de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] y tiene una referencia a System.Core.dll y una directiva `using` para System.Linq. Si faltan uno o varios de estos requisitos del proyecto, se pueden agregar manualmente.   
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Métodos de extensión](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)

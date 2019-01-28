---
title: 'Procedimiento Crear un método nuevo para una enumeración: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [C#]
- extension methods [C#], for enums
- enum extensibility [C#]
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
ms.openlocfilehash: 411606b6d86f8781be0cb2db19474d563c09a610
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54725134"
---
# <a name="how-to-create-a-new-method-for-an-enumeration-c-programming-guide"></a>Procedimiento Crear un método nuevo para una enumeración (Guía de programación de C#)
Puede usar métodos de extensión para agregar funcionalidad a un tipo de enumeración concreto.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, la enumeración `Grades` representa las posibles calificaciones con letras que un alumno puede recibir en una clase. Un método de extensión denominado `Passing` se agrega al tipo `Grades` para que cada instancia de ese tipo "sepa" ahora si representa una calificación de aprobado o no.  
  
 [!code-csharp[csProgGuideExtensionMethods#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-create-a-new-method-for-an-enumeration_1.cs)]  
  
 Tenga en cuenta que la clase `Extensions` también contiene una variable estática que se actualiza dinámicamente y que el valor devuelto del método de extensión refleja el valor actual de esa variable. Esto demuestra que, en segundo plano, los métodos de extensión se invocan directamente en la clase estática en donde se definen.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para ejecutar este código, cópielo y péguelo en un proyecto de aplicación de consola de Visual C# creado en Visual Studio. De forma predeterminada, este proyecto tiene como destino la versión 3.5 de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] y tiene una referencia a System.Core.dll y una directiva `using` para System.Linq. Si faltan alguno de estos requisitos del proyecto, se puede agregar manualmente.  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Métodos de extensión](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)

---
title: "Cómo: Inicializar un diccionario con un inicializador de colección (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- collection initializers [C#], with Dictionary
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8b8de5fb85a839d52ad00ad552ef823d9817e9b7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-initialize-a-dictionary-with-a-collection-initializer-c-programming-guide"></a>Cómo: Inicializar un diccionario con un inicializador de colección (Guía de programación de C#)
Un método <xref:System.Collections.Generic.Dictionary`2> contains a collection of key/value pairs. Its <xref:System.Collections.Generic.Dictionary`2.Add*> acepta dos parámetros, uno para la clave y otro para el valor. Para inicializar un método <xref:System.Collections.Generic.Dictionary`2>, or any collection whose `Add` que acepte varios parámetros, encierre entre llaves cada uno de los conjuntos de parámetros, como se muestra en el ejemplo siguiente.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente, <xref:System.Collections.Generic.Dictionary`2> is initialized with instances of type `StudentName`.  
  
 [!code-csharp[csProgGuideLINQ#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-a-dictionary-with-a-collection-initializer_1.cs)]  
  
 Observe los dos pares de llaves en cada elemento de la colección. Las llaves internas contienen el inicializador de objeto para `StudentName` y las llaves externas contienen el inicializador para el par clave-valor que se agregará a `students`<xref:System.Collections.Generic.Dictionary`2>. Por último, el inicializador completo de la colección para el diccionario se encierra entre llaves.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para ejecutar este código, copie y pegue la clase en un proyecto de aplicación de consola de Visual C# creado en [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)]. De manera predeterminada, el proyecto tiene como destino la versión 3.5 de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] y contiene una referencia a System.Core.dll y una directiva using para System.Linq. Si faltan uno o varios de estos requisitos del proyecto, puede agregarlos manualmente.  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Inicializadores de objeto y colección](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)

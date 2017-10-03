---
title: "Cómo: Inicializar un diccionario con un inicializador de colección (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- collection initializers [C#], with Dictionary
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
caps.latest.revision: 10
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 41d6a9934daaa1274901e20de58cfd480c904bfa
ms.contentlocale: es-es
ms.lasthandoff: 09/25/2017

---
# <a name="how-to-initialize-a-dictionary-with-a-collection-initializer-c-programming-guide"></a>Cómo: Inicializar un diccionario con un inicializador de colección (Guía de programación de C#)
Un método <xref:System.Collections.Generic.Dictionary`2> contains a collection of key/value pairs. Its <xref:System.Collections.Generic.Dictionary`2.Add*> acepta dos parámetros, uno para la clave y otro para el valor. Para inicializar un método <xref:System.Collections.Generic.Dictionary`2>, or any collection whose `Add` que acepte varios parámetros, encierre entre llaves cada uno de los conjuntos de parámetros, como se muestra en el ejemplo siguiente.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente, <xref:System.Collections.Generic.Dictionary`2> is initialized with instances of type `StudentName`.  
  
 [!code-cs[csProgGuideLINQ#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-a-dictionary-with-a-collection-initializer_1.cs)]  
  
 Observe los dos pares de llaves en cada elemento de la colección. Las llaves internas contienen el inicializador de objeto para `StudentName` y las llaves externas contienen el inicializador para el par clave-valor que se agregará a `students`<xref:System.Collections.Generic.Dictionary`2>. Por último, el inicializador completo de la colección para el diccionario se encierra entre llaves.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para ejecutar este código, copie y pegue la clase en un proyecto de aplicación de consola de Visual C# creado en [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)]. De manera predeterminada, el proyecto tiene como destino la versión 3.5 de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] y contiene una referencia a System.Core.dll y una directiva using para System.Linq. Si faltan uno o varios de estos requisitos del proyecto, puede agregarlos manualmente.   
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Inicializadores de objeto y colección](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)


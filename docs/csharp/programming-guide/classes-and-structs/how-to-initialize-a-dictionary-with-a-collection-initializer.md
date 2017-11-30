---
title: "Cómo: Inicializar un diccionario con un inicializador de colección (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: collection initializers [C#], with Dictionary
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
caps.latest.revision: "10"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8b8de5fb85a839d52ad00ad552ef823d9817e9b7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-initialize-a-dictionary-with-a-collection-initializer-c-programming-guide"></a><span data-ttu-id="f0859-102">Cómo: Inicializar un diccionario con un inicializador de colección (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="f0859-102">How to: Initialize a Dictionary with a Collection Initializer (C# Programming Guide)</span></span>
<span data-ttu-id="f0859-103">Un método <xref:System.Collections.Generic.Dictionary`2> contains a collection of key/value pairs. Its <xref:System.Collections.Generic.Dictionary`2.Add*> acepta dos parámetros, uno para la clave y otro para el valor.</span><span class="sxs-lookup"><span data-stu-id="f0859-103">A <xref:System.Collections.Generic.Dictionary`2> contains a collection of key/value pairs. Its <xref:System.Collections.Generic.Dictionary`2.Add*> method takes two parameters, one for the key and one for the value.</span></span> <span data-ttu-id="f0859-104">Para inicializar un método <xref:System.Collections.Generic.Dictionary`2>, or any collection whose `Add\` que acepte varios parámetros, encierre entre llaves cada uno de los conjuntos de parámetros, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f0859-104">To initialize a <xref:System.Collections.Generic.Dictionary`2>, or any collection whose `Add\` method takes multiple parameters, enclose each set of parameters in braces as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0859-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f0859-105">Example</span></span>  
 <span data-ttu-id="f0859-106">En el ejemplo de código siguiente, <xref:System.Collections.Generic.Dictionary`2> is initialized with instances of type `StudentName\`.</span><span class="sxs-lookup"><span data-stu-id="f0859-106">In the following code example, a <xref:System.Collections.Generic.Dictionary`2> is initialized with instances of type `StudentName\`.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-a-dictionary-with-a-collection-initializer_1.cs)]  
  
 <span data-ttu-id="f0859-107">Observe los dos pares de llaves en cada elemento de la colección.</span><span class="sxs-lookup"><span data-stu-id="f0859-107">Note the two pairs of braces in each element of the collection.</span></span> <span data-ttu-id="f0859-108">Las llaves internas contienen el inicializador de objeto para `StudentName` y las llaves externas contienen el inicializador para el par clave-valor que se agregará a `students`<xref:System.Collections.Generic.Dictionary\`2>.</span><span class="sxs-lookup"><span data-stu-id="f0859-108">The innermost braces enclose the object initializer for the `StudentName`, and the outermost braces enclose the initializer for the key/value pair that will be added to the `students`<xref:System.Collections.Generic.Dictionary\`2>.</span></span> <span data-ttu-id="f0859-109">Por último, el inicializador completo de la colección para el diccionario se encierra entre llaves.</span><span class="sxs-lookup"><span data-stu-id="f0859-109">Finally, the whole collection initializer for the dictionary is enclosed in braces.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f0859-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="f0859-110">Compiling the Code</span></span>  
 <span data-ttu-id="f0859-111">Para ejecutar este código, copie y pegue la clase en un proyecto de aplicación de consola de Visual C# creado en [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0859-111">To run this code, copy and paste the class into a Visual C# console application project that has been created in [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)].</span></span> <span data-ttu-id="f0859-112">De manera predeterminada, el proyecto tiene como destino la versión 3.5 de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] y contiene una referencia a System.Core.dll y una directiva using para System.Linq.</span><span class="sxs-lookup"><span data-stu-id="f0859-112">By default, this project targets version 3.5 of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], and it has a reference to System.Core.dll and a using directive for System.Linq.</span></span> <span data-ttu-id="f0859-113">Si faltan uno o varios de estos requisitos del proyecto, puede agregarlos manualmente.</span><span class="sxs-lookup"><span data-stu-id="f0859-113">If one or more of these requirements are missing from the project, you can add them manually.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0859-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0859-114">See Also</span></span>  
 [<span data-ttu-id="f0859-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f0859-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f0859-116">Inicializadores de objeto y colección</span><span class="sxs-lookup"><span data-stu-id="f0859-116">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)

---
title: 'Cómo: Inicializar un diccionario con un inicializador de colección (Guía de programación de C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- collection initializers [C#], with Dictionary
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
caps.latest.revision: 10
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9f014e92167d92f7daebcfb4c2e1d54f69ee2575
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-initialize-a-dictionary-with-a-collection-initializer-c-programming-guide"></a><span data-ttu-id="82cc9-102">Cómo: Inicializar un diccionario con un inicializador de colección (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="82cc9-102">How to: Initialize a Dictionary with a Collection Initializer (C# Programming Guide)</span></span>
<span data-ttu-id="82cc9-103"><xref:System.Collections.Generic.Dictionary`2> contiene una colección de pares clave-valor.</span><span class="sxs-lookup"><span data-stu-id="82cc9-103">A <xref:System.Collections.Generic.Dictionary`2> contains a collection of key/value pairs.</span></span> <span data-ttu-id="82cc9-104">Su método <xref:System.Collections.Generic.Dictionary`2.Add*> toma dos parámetros: uno para la clave y otro para el valor.</span><span class="sxs-lookup"><span data-stu-id="82cc9-104">Its <xref:System.Collections.Generic.Dictionary`2.Add*> method takes two parameters, one for the key and one for the value.</span></span> <span data-ttu-id="82cc9-105">Para inicializar <xref:System.Collections.Generic.Dictionary`2>, o cualquier otra colección cuyo método `Add` tome varios parámetros, encierre entre llaves cada uno de los conjuntos de parámetros, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="82cc9-105">To initialize a <xref:System.Collections.Generic.Dictionary`2>, or any collection whose `Add` method takes multiple parameters, enclose each set of parameters in braces as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82cc9-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="82cc9-106">Example</span></span>  
 <span data-ttu-id="82cc9-107">En el ejemplo de código siguiente, <xref:System.Collections.Generic.Dictionary`2> se inicializa con instancias del tipo `StudentName`.</span><span class="sxs-lookup"><span data-stu-id="82cc9-107">In the following code example, a <xref:System.Collections.Generic.Dictionary`2> is initialized with instances of type `StudentName`.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-a-dictionary-with-a-collection-initializer_1.cs)]  
  
 <span data-ttu-id="82cc9-108">Observe los dos pares de llaves en cada elemento de la colección.</span><span class="sxs-lookup"><span data-stu-id="82cc9-108">Note the two pairs of braces in each element of the collection.</span></span> <span data-ttu-id="82cc9-109">Las llaves internas contienen el inicializador de objeto para `StudentName` y las llaves externas contienen el inicializador para el par clave-valor que se agregará a `students`<xref:System.Collections.Generic.Dictionary`2>.</span><span class="sxs-lookup"><span data-stu-id="82cc9-109">The innermost braces enclose the object initializer for the `StudentName`, and the outermost braces enclose the initializer for the key/value pair that will be added to the `students`<xref:System.Collections.Generic.Dictionary`2>.</span></span> <span data-ttu-id="82cc9-110">Por último, el inicializador completo de la colección para el diccionario se encierra entre llaves.</span><span class="sxs-lookup"><span data-stu-id="82cc9-110">Finally, the whole collection initializer for the dictionary is enclosed in braces.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="82cc9-111">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="82cc9-111">Compiling the Code</span></span>  
 <span data-ttu-id="82cc9-112">Para ejecutar este código, copie y pegue la clase en un proyecto de aplicación de consola de Visual C# creado en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="82cc9-112">To run this code, copy and paste the class into a Visual C# console application project that has been created in Visual Studio.</span></span> <span data-ttu-id="82cc9-113">De manera predeterminada, el proyecto tiene como destino la versión 3.5 de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] y contiene una referencia a System.Core.dll y una directiva using para System.Linq.</span><span class="sxs-lookup"><span data-stu-id="82cc9-113">By default, this project targets version 3.5 of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], and it has a reference to System.Core.dll and a using directive for System.Linq.</span></span> <span data-ttu-id="82cc9-114">Si faltan uno o varios de estos requisitos del proyecto, puede agregarlos manualmente.</span><span class="sxs-lookup"><span data-stu-id="82cc9-114">If one or more of these requirements are missing from the project, you can add them manually.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82cc9-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="82cc9-115">See Also</span></span>  
 [<span data-ttu-id="82cc9-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="82cc9-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="82cc9-117">Inicializadores de objeto y colección</span><span class="sxs-lookup"><span data-stu-id="82cc9-117">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)

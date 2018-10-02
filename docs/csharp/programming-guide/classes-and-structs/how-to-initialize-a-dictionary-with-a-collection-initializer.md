---
title: 'Cómo: Inicializar un diccionario con un inicializador de colección (Guía de programación de C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [C#], with Dictionary
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
ms.openlocfilehash: ca2f508e5500cc135b2712362bcfb71778a664c1
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2018
ms.locfileid: "44227342"
---
# <a name="how-to-initialize-a-dictionary-with-a-collection-initializer-c-programming-guide"></a><span data-ttu-id="44a89-102">Cómo: Inicializar un diccionario con un inicializador de colección (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="44a89-102">How to initialize a dictionary with a collection initializer (C# Programming Guide)</span></span>

<span data-ttu-id="44a89-103"><xref:System.Collections.Generic.Dictionary%602> contiene una colección de pares clave-valor.</span><span class="sxs-lookup"><span data-stu-id="44a89-103">A <xref:System.Collections.Generic.Dictionary%602> contains a collection of key/value pairs.</span></span> <span data-ttu-id="44a89-104">Su método <xref:System.Collections.Generic.Dictionary%602.Add*> toma dos parámetros: uno para la clave y otro para el valor.</span><span class="sxs-lookup"><span data-stu-id="44a89-104">Its <xref:System.Collections.Generic.Dictionary%602.Add*> method takes two parameters, one for the key and one for the value.</span></span> <span data-ttu-id="44a89-105">Para inicializar <xref:System.Collections.Generic.Dictionary%602>, o cualquier otra colección cuyo método `Add` tome varios parámetros, encierre entre llaves cada uno de los conjuntos de parámetros, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="44a89-105">To initialize a <xref:System.Collections.Generic.Dictionary%602>, or any collection whose `Add` method takes multiple parameters, enclose each set of parameters in braces as shown in the following example.</span></span>

## <a name="example"></a><span data-ttu-id="44a89-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="44a89-106">Example</span></span>

<span data-ttu-id="44a89-107">En el ejemplo de código siguiente, <xref:System.Collections.Generic.Dictionary%602> se inicializa con instancias del tipo `StudentName`.</span><span class="sxs-lookup"><span data-stu-id="44a89-107">In the following code example, a <xref:System.Collections.Generic.Dictionary%602> is initialized with instances of type `StudentName`.</span></span>  
  
[!code-csharp[csProgGuideLINQ#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-a-dictionary-with-a-collection-initializer_1.cs)]

<span data-ttu-id="44a89-108">Observe los dos pares de llaves en cada elemento de la colección.</span><span class="sxs-lookup"><span data-stu-id="44a89-108">Note the two pairs of braces in each element of the collection.</span></span> <span data-ttu-id="44a89-109">Las llaves internas contienen el inicializador de objeto para `StudentName`, mientras que las externas contienen el inicializador para el par clave-valor que se va a agregar al <xref:System.Collections.Generic.Dictionary%602> `students`.</span><span class="sxs-lookup"><span data-stu-id="44a89-109">The innermost braces enclose the object initializer for the `StudentName`, and the outermost braces enclose the initializer for the key/value pair that will be added to the `students` <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="44a89-110">Por último, el inicializador completo de la colección para el diccionario se encierra entre llaves.</span><span class="sxs-lookup"><span data-stu-id="44a89-110">Finally, the whole collection initializer for the dictionary is enclosed in braces.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="44a89-111">Compilación del código</span><span class="sxs-lookup"><span data-stu-id="44a89-111">Compiling the code</span></span>

<span data-ttu-id="44a89-112">Para ejecutar este código, copie y pegue la clase en un proyecto de aplicación de consola de Visual C# creado en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="44a89-112">To run this code, copy and paste the class into a Visual C# console application project that has been created in Visual Studio.</span></span> <span data-ttu-id="44a89-113">De manera predeterminada, el proyecto tiene como destino la versión 3.5 de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] y contiene una referencia a System.Core.dll y una directiva using para System.Linq.</span><span class="sxs-lookup"><span data-stu-id="44a89-113">By default, this project targets version 3.5 of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], and it has a reference to System.Core.dll and a using directive for System.Linq.</span></span> <span data-ttu-id="44a89-114">Si faltan uno o varios de estos requisitos del proyecto, se pueden agregar manualmente.</span><span class="sxs-lookup"><span data-stu-id="44a89-114">If one or more of these requirements are missing from the project, you can add them manually.</span></span>

## <a name="see-also"></a><span data-ttu-id="44a89-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="44a89-115">See also</span></span>

- [<span data-ttu-id="44a89-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="44a89-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="44a89-117">Inicializadores de objeto y colección</span><span class="sxs-lookup"><span data-stu-id="44a89-117">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)

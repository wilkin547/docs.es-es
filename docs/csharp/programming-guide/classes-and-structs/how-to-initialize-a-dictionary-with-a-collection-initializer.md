---
title: 'Inicialización de un diccionario con un inicializador de colección: Guía de programación de C#'
description: Obtenga información sobre cómo inicializar un diccionario en C#, mediante el método Add o un inicializador de índice. En este ejemplo se muestran las dos opciones.
ms.date: 12/20/2018
helpviewer_keywords:
- collection initializers [C#], with Dictionary
ms.topic: how-to
ms.custom: contperfq2
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
ms.openlocfilehash: 667b39076f01ab59eb64cf31d7c1dbb921500135
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099352"
---
# <a name="how-to-initialize-a-dictionary-with-a-collection-initializer-c-programming-guide"></a><span data-ttu-id="74552-104">Procedimientos: inicialización de un diccionario con un inicializador de colección (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="74552-104">How to initialize a dictionary with a collection initializer (C# Programming Guide)</span></span>

<span data-ttu-id="74552-105">Una clase <xref:System.Collections.Generic.Dictionary%602> contiene una colección de pares clave-valor.</span><span class="sxs-lookup"><span data-stu-id="74552-105">A <xref:System.Collections.Generic.Dictionary%602> contains a collection of key/value pairs.</span></span> <span data-ttu-id="74552-106">Su método <xref:System.Collections.Generic.Dictionary%602.Add%2A> toma dos parámetros: uno para la clave y otro para el valor.</span><span class="sxs-lookup"><span data-stu-id="74552-106">Its <xref:System.Collections.Generic.Dictionary%602.Add%2A> method takes two parameters, one for the key and one for the value.</span></span> <span data-ttu-id="74552-107">Una manera de inicializar <xref:System.Collections.Generic.Dictionary%602>, o cualquier colección cuyo método `Add` tome varios parámetros, es incluir entre llaves cada conjunto de parámetros, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="74552-107">One way to initialize a <xref:System.Collections.Generic.Dictionary%602>, or any collection whose `Add` method takes multiple parameters, is to enclose each set of parameters in braces as shown in the following example.</span></span> <span data-ttu-id="74552-108">Otra opción es usar un inicializador de índice, lo que también se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="74552-108">Another option is to use an index initializer, also shown in the following example.</span></span>

## <a name="example"></a><span data-ttu-id="74552-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="74552-109">Example</span></span>

<span data-ttu-id="74552-110">En el ejemplo de código siguiente, <xref:System.Collections.Generic.Dictionary%602> se inicializa con instancias de tipo `StudentName`.</span><span class="sxs-lookup"><span data-stu-id="74552-110">In the following code example, a <xref:System.Collections.Generic.Dictionary%602> is initialized with instances of type `StudentName`.</span></span>  <span data-ttu-id="74552-111">La primera inicialización usa el método `Add` con dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="74552-111">The first initialization uses the `Add` method with two arguments.</span></span> <span data-ttu-id="74552-112">El compilador genera una llamada a `Add` por cada uno de los pares de claves `int` y valores `StudentName`.</span><span class="sxs-lookup"><span data-stu-id="74552-112">The compiler generates a call to `Add` for each of the pairs of `int` keys and `StudentName` values.</span></span> <span data-ttu-id="74552-113">La segunda usa un método de indizador de lectura y escritura público de la clase `Dictionary`:</span><span class="sxs-lookup"><span data-stu-id="74552-113">The second uses a public read / write indexer method of the `Dictionary` class:</span></span>

[!code-csharp[InitializerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToDictionaryInitializer.cs#HowToDictionaryInitializer)]  

<span data-ttu-id="74552-114">Observe los dos pares de llaves de cada elemento de la colección en la primera declaración.</span><span class="sxs-lookup"><span data-stu-id="74552-114">Note the two pairs of braces in each element of the collection in the first declaration.</span></span> <span data-ttu-id="74552-115">Las llaves internas contienen el inicializador de objeto para `StudentName`, mientras que las externas contienen el inicializador para el par clave-valor que se va a agregar a la clase <xref:System.Collections.Generic.Dictionary%602> `students`.</span><span class="sxs-lookup"><span data-stu-id="74552-115">The innermost braces enclose the object initializer for the `StudentName`, and the outermost braces enclose the initializer for the key/value pair that will be added to the `students` <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="74552-116">Por último, el inicializador completo de la colección para el diccionario se encierra entre llaves.</span><span class="sxs-lookup"><span data-stu-id="74552-116">Finally, the whole collection initializer for the dictionary is enclosed in braces.</span></span> <span data-ttu-id="74552-117">En la segunda inicialización, el lado izquierdo de la asignación es la clave y el lado derecho es el valor, con un inicializador de objeto para `StudentName`.</span><span class="sxs-lookup"><span data-stu-id="74552-117">In the second initialization, the left side of the assignment is the key and the right side is the value, using an object initializer for `StudentName`.</span></span>

## <a name="see-also"></a><span data-ttu-id="74552-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="74552-118">See also</span></span>

- [<span data-ttu-id="74552-119">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="74552-119">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="74552-120">Inicializadores de objeto y colección</span><span class="sxs-lookup"><span data-stu-id="74552-120">Object and Collection Initializers</span></span>](./object-and-collection-initializers.md)

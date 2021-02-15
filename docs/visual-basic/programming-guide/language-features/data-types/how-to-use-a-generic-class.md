---
description: 'Más información sobre: Cómo: usar una clase genérica (Visual Basic)'
title: Procedimiento Uso de clases genéricas
ms.date: 07/20/2015
helpviewer_keywords:
- type parameters [Visual Basic], defining
- data type arguments [Visual Basic], defining
- arguments [Visual Basic], data types
- Of keyword [Visual Basic], using
- generic parameters
- data type parameters
- generics [Visual Basic], about generics
- data types [Visual Basic], as parameters
- data types [Visual Basic], as arguments
- parameters [Visual Basic], type
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], creating generic types
- data type arguments
- parameters [Visual Basic], data type
- data type parameters [Visual Basic], defining
- type arguments [Visual Basic], defining
- arguments [Visual Basic], type
ms.assetid: 242dd2a6-86c4-4ce7-83f2-f2661803f752
ms.openlocfilehash: b21f29223c6a7f611fd4064a0df28ed72f599361
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100483968"
---
# <a name="how-to-use-a-generic-class-visual-basic"></a><span data-ttu-id="eac78-103">Cómo: Usar clases genéricas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eac78-103">How to: Use a Generic Class (Visual Basic)</span></span>

<span data-ttu-id="eac78-104">Las clases que toman *parámetros de tipo* se denominan *clases genéricas*.</span><span class="sxs-lookup"><span data-stu-id="eac78-104">A class that takes *type parameters* is called a *generic class*.</span></span> <span data-ttu-id="eac78-105">Si usa una clase genérica, puede generar una *clase construida* a partir de ella proporcionando un *argumento de tipo* para cada uno de estos parámetros.</span><span class="sxs-lookup"><span data-stu-id="eac78-105">If you are using a generic class, you can generate a *constructed class* from it by supplying a *type argument* for each of these parameters.</span></span> <span data-ttu-id="eac78-106">Después, puede declarar una variable del tipo de clase construida, crear una instancia de la clase construida y asignarla a esa variable.</span><span class="sxs-lookup"><span data-stu-id="eac78-106">You can then declare a variable of the constructed class type, and you can create an instance of the constructed class and assign it to that variable.</span></span>  
  
 <span data-ttu-id="eac78-107">Además de clases, también puede definir y usar estructuras genéricas, interfaces, procedimientos y delegados.</span><span class="sxs-lookup"><span data-stu-id="eac78-107">In addition to classes, you can also define and use generic structures, interfaces, procedures, and delegates.</span></span>  
  
 <span data-ttu-id="eac78-108">En el procedimiento siguiente se toma una clase genérica definida en el .NET Framework y se crea una instancia a partir de ella.</span><span class="sxs-lookup"><span data-stu-id="eac78-108">The following procedure takes a generic class defined in the .NET Framework and creates an instance from it.</span></span>  
  
### <a name="to-use-a-class-that-takes-a-type-parameter"></a><span data-ttu-id="eac78-109">Para usar una clase que toma un parámetro de tipo</span><span class="sxs-lookup"><span data-stu-id="eac78-109">To use a class that takes a type parameter</span></span>  
  
1. <span data-ttu-id="eac78-110">Al principio del archivo de código fuente, incluya una [instrucción Imports (espacio de nombres de .net y tipo)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md) para importar el <xref:System.Collections.Generic?displayProperty=nameWithType> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="eac78-110">At the beginning of your source file, include an [Imports Statement (.NET Namespace and Type)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md) to import the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="eac78-111">Esto le permite hacer referencia a la clase <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> sin tener que usar su nombre completo para diferenciarla de otras clases queue, como <xref:System.Collections.Queue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="eac78-111">This allows you to refer to the <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> class without having to fully qualify it to differentiate it from other queue classes such as <xref:System.Collections.Queue?displayProperty=nameWithType>.</span></span>  
  
2. <span data-ttu-id="eac78-112">Cree el objeto de la manera normal, pero agregue `(Of type)` inmediatamente después del nombre de clase.</span><span class="sxs-lookup"><span data-stu-id="eac78-112">Create the object in the normal way, but add `(Of type)` immediately after the class name.</span></span>  
  
     <span data-ttu-id="eac78-113">En el ejemplo siguiente se usa la misma clase (<xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>) para crear dos objetos queue que contienen elementos de distintos tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="eac78-113">The following example uses the same class (<xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>) to create two queue objects that hold items of different data types.</span></span> <span data-ttu-id="eac78-114">Agrega elementos al final de cada cola y, después, quita y muestra los elementos de la parte delantera de cada cola.</span><span class="sxs-lookup"><span data-stu-id="eac78-114">It adds items to the end of each queue and then removes and displays items from the front of each queue.</span></span>  
  
     [!code-vb[VbVbalrDataTypes#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="eac78-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eac78-115">See also</span></span>

- [<span data-ttu-id="eac78-116">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="eac78-116">Data Types</span></span>](index.md)
- [<span data-ttu-id="eac78-117">Tipos genéricos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="eac78-117">Generic Types in Visual Basic</span></span>](generic-types.md)
- [<span data-ttu-id="eac78-118">Independencia del lenguaje y componentes independientes del lenguaje</span><span class="sxs-lookup"><span data-stu-id="eac78-118">Language Independence and Language-Independent Components</span></span>](../../../../standard/language-independence-and-language-independent-components.md)
- [<span data-ttu-id="eac78-119">De</span><span class="sxs-lookup"><span data-stu-id="eac78-119">Of</span></span>](../../../language-reference/statements/of-clause.md)
- [<span data-ttu-id="eac78-120">Instrucción Imports (Tipo y espacio de nombres de .NET)</span><span class="sxs-lookup"><span data-stu-id="eac78-120">Imports Statement (.NET Namespace and Type)</span></span>](../../../language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="eac78-121">Procedimiento Definición de clases capaces de proporcionar la misma funcionalidad en tipos de datos diferentes</span><span class="sxs-lookup"><span data-stu-id="eac78-121">How to: Define a Class That Can Provide Identical Functionality on Different Data Types</span></span>](how-to-define-a-class-that-can-provide-identical-functionality.md)
- [<span data-ttu-id="eac78-122">Iteradores</span><span class="sxs-lookup"><span data-stu-id="eac78-122">Iterators</span></span>](../../concepts/iterators.md)

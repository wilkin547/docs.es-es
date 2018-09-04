---
title: 'Cómo: Usar clases genéricas (Visual Basic)'
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
ms.openlocfilehash: 3bcf7b0556ef2c5d9b8f82442815672b2b3cde86
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43520662"
---
# <a name="how-to-use-a-generic-class-visual-basic"></a><span data-ttu-id="e5733-102">Cómo: Usar clases genéricas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e5733-102">How to: Use a Generic Class (Visual Basic)</span></span>
<span data-ttu-id="e5733-103">Las clases que toman *parámetros de tipo* se denominan *clases genéricas*.</span><span class="sxs-lookup"><span data-stu-id="e5733-103">A class that takes *type parameters* is called a *generic class*.</span></span> <span data-ttu-id="e5733-104">Si usa una clase genérica, puede generar una *clase construida* a partir de ella proporcionando un *argumento de tipo* para cada uno de estos parámetros.</span><span class="sxs-lookup"><span data-stu-id="e5733-104">If you are using a generic class, you can generate a *constructed class* from it by supplying a *type argument* for each of these parameters.</span></span> <span data-ttu-id="e5733-105">Después, puede declarar una variable del tipo de clase construida, crear una instancia de la clase construida y asignarla a esa variable.</span><span class="sxs-lookup"><span data-stu-id="e5733-105">You can then declare a variable of the constructed class type, and you can create an instance of the constructed class and assign it to that variable.</span></span>  
  
 <span data-ttu-id="e5733-106">Además de clases, también puede definir y usar estructuras genéricas, interfaces, procedimientos y delegados.</span><span class="sxs-lookup"><span data-stu-id="e5733-106">In addition to classes, you can also define and use generic structures, interfaces, procedures, and delegates.</span></span>  
  
 <span data-ttu-id="e5733-107">En el procedimiento siguiente se toma una clase genérica definida en [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] y se crea una instancia a partir de ella.</span><span class="sxs-lookup"><span data-stu-id="e5733-107">The following procedure takes a generic class defined in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] and creates an instance from it.</span></span>  
  
### <a name="to-use-a-class-that-takes-a-type-parameter"></a><span data-ttu-id="e5733-108">Para usar una clase que toma un parámetro de tipo</span><span class="sxs-lookup"><span data-stu-id="e5733-108">To use a class that takes a type parameter</span></span>  
  
1.  <span data-ttu-id="e5733-109">Al principio del archivo de origen, incluya una [instrucción Imports (tipo y Namespace. NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) para importar el <xref:System.Collections.Generic?displayProperty=nameWithType> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e5733-109">At the beginning of your source file, include an [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to import the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="e5733-110">Esto le permite hacer referencia a la clase <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> sin tener que usar su nombre completo para diferenciarla de otras clases queue, como <xref:System.Collections.Queue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e5733-110">This allows you to refer to the <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> class without having to fully qualify it to differentiate it from other queue classes such as <xref:System.Collections.Queue?displayProperty=nameWithType>.</span></span>  
  
2.  <span data-ttu-id="e5733-111">Cree el objeto de la manera normal, pero agregue `(Of` `type``)` inmediatamente después del nombre de clase.</span><span class="sxs-lookup"><span data-stu-id="e5733-111">Create the object in the normal way, but add `(Of` `type``)` immediately after the class name.</span></span>  
  
     <span data-ttu-id="e5733-112">En el ejemplo siguiente se usa la misma clase (<xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>) para crear dos objetos queue que contienen elementos de distintos tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="e5733-112">The following example uses the same class (<xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>) to create two queue objects that hold items of different data types.</span></span> <span data-ttu-id="e5733-113">Agrega elementos al final de cada cola y, después, quita y muestra los elementos de la parte delantera de cada cola.</span><span class="sxs-lookup"><span data-stu-id="e5733-113">It adds items to the end of each queue and then removes and displays items from the front of each queue.</span></span>  
  
     [!code-vb[VbVbalrDataTypes#9](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/how-to-use-a-generic-class_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e5733-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5733-114">See Also</span></span>  
 [<span data-ttu-id="e5733-115">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="e5733-115">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="e5733-116">Tipos genéricos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e5733-116">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="e5733-117">Independencia del lenguaje y componentes independientes del lenguaje</span><span class="sxs-lookup"><span data-stu-id="e5733-117">Language Independence and Language-Independent Components</span></span>](../../../../standard/language-independence-and-language-independent-components.md)  
 [<span data-ttu-id="e5733-118">Of</span><span class="sxs-lookup"><span data-stu-id="e5733-118">Of</span></span>](../../../../visual-basic/language-reference/statements/of-clause.md)  
 [<span data-ttu-id="e5733-119">Imports (instrucción), espacio de nombres y tipo .NET</span><span class="sxs-lookup"><span data-stu-id="e5733-119">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="e5733-120">Definir una clase que pueda proporcionar la misma funcionalidad en tipos de datos diferentes</span><span class="sxs-lookup"><span data-stu-id="e5733-120">How to: Define a Class That Can Provide Identical Functionality on Different Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)  
 [<span data-ttu-id="e5733-121">Iteradores</span><span class="sxs-lookup"><span data-stu-id="e5733-121">Iterators</span></span>](https://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)

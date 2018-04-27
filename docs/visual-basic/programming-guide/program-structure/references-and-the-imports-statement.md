---
title: Referencias y la instrucción Imports (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references [Visual Basic], assembly
- namespaces [Visual Basic], assemblies
- referencing assemblies
- Imports statement [Visual Basic], referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 051351c2fa0648de54bbfd36b1630ec1cd49d6f0
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="references-and-the-imports-statement-visual-basic"></a><span data-ttu-id="31e25-102">Referencias y la instrucción Imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31e25-102">References and the Imports Statement (Visual Basic)</span></span>
<span data-ttu-id="31e25-103">Se pueden disponer de objetos externos a su proyecto eligiendo la **Agregar referencia** comando el **proyecto** menú.</span><span class="sxs-lookup"><span data-stu-id="31e25-103">You can make external objects available to your project by choosing the **Add Reference** command on the **Project** menu.</span></span> <span data-ttu-id="31e25-104">Las referencias en Visual Basic pueden apuntar a ensamblados, que son similares a las bibliotecas de tipos, pero contienen más información.</span><span class="sxs-lookup"><span data-stu-id="31e25-104">References in Visual Basic can point to assemblies, which are like type libraries but contain more information.</span></span>  
  
## <a name="the-imports-statement"></a><span data-ttu-id="31e25-105">La instrucción Imports</span><span class="sxs-lookup"><span data-stu-id="31e25-105">The Imports Statement</span></span>  
 <span data-ttu-id="31e25-106">Los ensamblados incluyen uno o varios espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="31e25-106">Assemblies include one or more namespaces.</span></span> <span data-ttu-id="31e25-107">Cuando se agrega una referencia a un ensamblado, también puede agregar un `Imports` instrucción a un módulo que controla la visibilidad de los espacios de nombres del ensamblado dentro del módulo.</span><span class="sxs-lookup"><span data-stu-id="31e25-107">When you add a reference to an assembly, you can also add an `Imports` statement to a module that controls the visibility of that assembly's namespaces within the module.</span></span> <span data-ttu-id="31e25-108">El `Imports` instrucción proporciona un contexto de ámbito que permite utilizar solamente la parte del espacio de nombres necesaria para suministrar una referencia única.</span><span class="sxs-lookup"><span data-stu-id="31e25-108">The `Imports` statement provides a scoping context that lets you use only the portion of the namespace necessary to supply a unique reference.</span></span>  
  
 <span data-ttu-id="31e25-109">El `Imports` instrucción tiene la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="31e25-109">The `Imports` statement has the following syntax:</span></span>  
  
 <span data-ttu-id="31e25-110">`Imports` [`|``Aliasname` =] `Namespace`</span><span class="sxs-lookup"><span data-stu-id="31e25-110">`Imports` [`|``Aliasname` =] `Namespace`</span></span>  
  
 <span data-ttu-id="31e25-111">`Aliasname` hace referencia a un nombre corto que se puede utilizar dentro de código para hacer referencia a un espacio de nombres importado.</span><span class="sxs-lookup"><span data-stu-id="31e25-111">`Aliasname` refers to a short name you can use within code to refer to an imported namespace.</span></span> <span data-ttu-id="31e25-112">`Namespace` es un espacio de nombres disponible a través de una referencia de proyecto, una definición dentro del proyecto, o a través de un anterior `Imports` instrucción.</span><span class="sxs-lookup"><span data-stu-id="31e25-112">`Namespace` is a namespace available through either a project reference, through a definition within the project, or through a previous `Imports` statement.</span></span>  
  
 <span data-ttu-id="31e25-113">Un módulo puede contener cualquier número de `Imports` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="31e25-113">A module may contain any number of `Imports` statements.</span></span> <span data-ttu-id="31e25-114">Deben aparecer después de cualquier `Option` instrucciones, si está presente, pero antes que cualquier otro código.</span><span class="sxs-lookup"><span data-stu-id="31e25-114">They must appear after any `Option` statements, if present, but before any other code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31e25-115">No confunda las referencias de proyecto con el `Imports` instrucción o `Declare` instrucción.</span><span class="sxs-lookup"><span data-stu-id="31e25-115">Do not confuse project references with the `Imports` statement or the `Declare` statement.</span></span> <span data-ttu-id="31e25-116">Referencias del proyecto disponer objetos externos, como los objetos de ensamblados, proyectos de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="31e25-116">Project references make external objects, such as objects in assemblies, available to Visual Basic projects.</span></span> <span data-ttu-id="31e25-117">El `Imports` instrucción se utiliza para simplificar el acceso a las referencias del proyecto, pero no proporciona acceso a estos objetos.</span><span class="sxs-lookup"><span data-stu-id="31e25-117">The `Imports` statement is used to simplify access to project references, but does not provide access to these objects.</span></span> <span data-ttu-id="31e25-118">El `Declare` instrucción se utiliza para declarar una referencia a un procedimiento externo en una biblioteca de vínculos dinámicos (DLL).</span><span class="sxs-lookup"><span data-stu-id="31e25-118">The `Declare` statement is used to declare a reference to an external procedure in a dynamic-link library (DLL).</span></span>  
  
## <a name="using-aliases-with-the-imports-statement"></a><span data-ttu-id="31e25-119">Uso de alias con la instrucción Imports</span><span class="sxs-lookup"><span data-stu-id="31e25-119">Using Aliases with the Imports Statement</span></span>  
 <span data-ttu-id="31e25-120">El `Imports` instrucción resulta más fácil acceso a los métodos de clases por lo que elimina la necesidad de escribir explícitamente los nombres completos de referencias.</span><span class="sxs-lookup"><span data-stu-id="31e25-120">The `Imports` statement makes it easier to access methods of classes by eliminating the need to explicitly type the fully qualified names of references.</span></span> <span data-ttu-id="31e25-121">Los alias permiten asignar un nombre más descriptivo para solamente una parte de un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="31e25-121">Aliases let you assign a friendlier name to just one part of a namespace.</span></span> <span data-ttu-id="31e25-122">Por ejemplo, el retorno de carro/avance secuencia que produce un único fragmento de texto para mostrarse en varias líneas de línea es parte de la <xref:Microsoft.VisualBasic.ControlChars> módulo en el <xref:Microsoft.VisualBasic?displayProperty=nameWithType> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="31e25-122">For example, the carriage return/line feed sequence that causes a single piece of text to be displayed on multiple lines is part of the <xref:Microsoft.VisualBasic.ControlChars> module in the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="31e25-123">Para utilizar esta constante en un programa sin alias, se tendría que escribir el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="31e25-123">To use this constant in a program without an alias, you would need to type the following code:</span></span>  
  
 [!code-vb[VbVbalrApplication#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_1.vb)]  
  
 <span data-ttu-id="31e25-124">`Imports` instrucciones siempre deben ser las primeras líneas inmediatamente después de cualquier `Option` instrucciones de un módulo.</span><span class="sxs-lookup"><span data-stu-id="31e25-124">`Imports` statements must always be the first lines immediately following any `Option` statements in a module.</span></span> <span data-ttu-id="31e25-125">El siguiente fragmento de código muestra cómo importar y asignar un alias a la <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> módulo:</span><span class="sxs-lookup"><span data-stu-id="31e25-125">The following code fragment shows how to import and assign an alias to the <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> module:</span></span>  
  
 [!code-vb[VbVbalrApplication#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_2.vb)]  
  
 <span data-ttu-id="31e25-126">Las futuras referencias a este espacio de nombres pueden ser mucho más breves:</span><span class="sxs-lookup"><span data-stu-id="31e25-126">Future references to this namespace can be considerably shorter:</span></span>  
  
 [!code-vb[VbVbalrApplication#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_3.vb)]  
  
 <span data-ttu-id="31e25-127">Si un `Imports` instrucción no incluye un nombre de alias, los elementos definidos en el espacio de nombres importado pueden utilizarse en el módulo sin calificación.</span><span class="sxs-lookup"><span data-stu-id="31e25-127">If an `Imports` statement does not include an alias name, elements defined within the imported namespace can be used in the module without qualification.</span></span> <span data-ttu-id="31e25-128">Si se especifica el nombre de alias, debe usarse como un calificador de nombres dentro de ese espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="31e25-128">If the alias name is specified, it must be used as a qualifier for names contained within that namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31e25-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="31e25-129">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ControlChars>  
 <xref:Microsoft.VisualBasic>  
   
 [<span data-ttu-id="31e25-130">Espacios de nombres en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="31e25-130">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="31e25-131">Ensamblados y Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="31e25-131">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="31e25-132">Crear y utilizar ensamblados mediante la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="31e25-132">How to: Create and Use Assemblies Using the Command Line</span></span>](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4)  
 [<span data-ttu-id="31e25-133">Imports (instrucción), espacio de nombres y tipo .NET</span><span class="sxs-lookup"><span data-stu-id="31e25-133">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)

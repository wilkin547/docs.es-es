---
title: Referencias y la instrucción Imports (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references [Visual Basic], assembly
- namespaces [Visual Basic], assemblies
- referencing assemblies
- Imports statement [Visual Basic], referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
ms.openlocfilehash: c50a25dc0802f275e5cd4e0068e1a68bf559abc1
ms.sourcegitcommit: d9a0071d0fd490ae006c816f78a563b9946e269a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2019
ms.locfileid: "55066043"
---
# <a name="references-and-the-imports-statement-visual-basic"></a><span data-ttu-id="ca202-102">Referencias y la instrucción Imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca202-102">References and the Imports Statement (Visual Basic)</span></span>
<span data-ttu-id="ca202-103">Se pueden objetos externos a disposición del proyecto eligiendo la **Agregar referencia** comando el **proyecto** menú.</span><span class="sxs-lookup"><span data-stu-id="ca202-103">You can make external objects available to your project by choosing the **Add Reference** command on the **Project** menu.</span></span> <span data-ttu-id="ca202-104">Las referencias en Visual Basic pueden apuntar a ensamblados, que son similares a las bibliotecas de tipos, pero contienen más información.</span><span class="sxs-lookup"><span data-stu-id="ca202-104">References in Visual Basic can point to assemblies, which are like type libraries but contain more information.</span></span>  
  
## <a name="the-imports-statement"></a><span data-ttu-id="ca202-105">La instrucción Imports</span><span class="sxs-lookup"><span data-stu-id="ca202-105">The Imports Statement</span></span>  
 <span data-ttu-id="ca202-106">Los ensamblados incluyen uno o varios espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="ca202-106">Assemblies include one or more namespaces.</span></span> <span data-ttu-id="ca202-107">Cuando se agrega una referencia a un ensamblado, también puede agregar un `Imports` instrucción a un módulo que controla la visibilidad de espacios de nombres del ensamblado dentro del módulo.</span><span class="sxs-lookup"><span data-stu-id="ca202-107">When you add a reference to an assembly, you can also add an `Imports` statement to a module that controls the visibility of that assembly's namespaces within the module.</span></span> <span data-ttu-id="ca202-108">El `Imports` instrucción proporciona un ámbito de contexto que le permite usar sólo la parte del espacio de nombres necesarios para proporcionar una referencia única.</span><span class="sxs-lookup"><span data-stu-id="ca202-108">The `Imports` statement provides a scoping context that lets you use only the portion of the namespace necessary to supply a unique reference.</span></span>  
  
 <span data-ttu-id="ca202-109">El `Imports` instrucción tiene la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="ca202-109">The `Imports` statement has the following syntax:</span></span>  
  
 `Imports [Aliasname =] Namespace`  
  
 <span data-ttu-id="ca202-110">`Aliasname` hace referencia a un nombre corto que se puede usar dentro de código para hacer referencia a un espacio de nombres importado.</span><span class="sxs-lookup"><span data-stu-id="ca202-110">`Aliasname` refers to a short name you can use within code to refer to an imported namespace.</span></span> <span data-ttu-id="ca202-111">`Namespace` es un espacio de nombres disponible a través de una referencia de proyecto, mediante una definición dentro del proyecto o una anterior `Imports` instrucción.</span><span class="sxs-lookup"><span data-stu-id="ca202-111">`Namespace` is a namespace available through either a project reference, through a definition within the project, or through a previous `Imports` statement.</span></span>  
  
 <span data-ttu-id="ca202-112">Un módulo puede contener cualquier número de `Imports` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="ca202-112">A module may contain any number of `Imports` statements.</span></span> <span data-ttu-id="ca202-113">Deben aparecer después de cualquier `Option` instrucciones, si está presente, pero antes de cualquier otro código.</span><span class="sxs-lookup"><span data-stu-id="ca202-113">They must appear after any `Option` statements, if present, but before any other code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca202-114">No confunda las referencias de proyecto con el `Imports` instrucción o el `Declare` instrucción.</span><span class="sxs-lookup"><span data-stu-id="ca202-114">Do not confuse project references with the `Imports` statement or the `Declare` statement.</span></span> <span data-ttu-id="ca202-115">Las referencias de proyecto disposición objetos externos, como los objetos de ensamblados, proyectos de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ca202-115">Project references make external objects, such as objects in assemblies, available to Visual Basic projects.</span></span> <span data-ttu-id="ca202-116">El `Imports` instrucción se usa para simplificar el acceso a las referencias de proyecto, pero no proporciona acceso a estos objetos.</span><span class="sxs-lookup"><span data-stu-id="ca202-116">The `Imports` statement is used to simplify access to project references, but does not provide access to these objects.</span></span> <span data-ttu-id="ca202-117">El `Declare` instrucción se utiliza para declarar una referencia a un procedimiento externo en una biblioteca de vínculos dinámicos (DLL).</span><span class="sxs-lookup"><span data-stu-id="ca202-117">The `Declare` statement is used to declare a reference to an external procedure in a dynamic-link library (DLL).</span></span>  
  
## <a name="using-aliases-with-the-imports-statement"></a><span data-ttu-id="ca202-118">Uso de alias con la instrucción Imports</span><span class="sxs-lookup"><span data-stu-id="ca202-118">Using Aliases with the Imports Statement</span></span>  
 <span data-ttu-id="ca202-119">El `Imports` instrucción facilita acceso a los métodos de clases por lo que elimina la necesidad de escribir explícitamente los nombres completos de referencias.</span><span class="sxs-lookup"><span data-stu-id="ca202-119">The `Imports` statement makes it easier to access methods of classes by eliminating the need to explicitly type the fully qualified names of references.</span></span> <span data-ttu-id="ca202-120">Los alias permiten asignar un nombre más descriptivo a sólo una parte de un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="ca202-120">Aliases let you assign a friendlier name to just one part of a namespace.</span></span> <span data-ttu-id="ca202-121">Por ejemplo, el retorno de carro/avance la secuencia que produce un único fragmento de texto que se mostrará en varias líneas de línea es parte de la <xref:Microsoft.VisualBasic.ControlChars> módulo en el <xref:Microsoft.VisualBasic?displayProperty=nameWithType> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="ca202-121">For example, the carriage return/line feed sequence that causes a single piece of text to be displayed on multiple lines is part of the <xref:Microsoft.VisualBasic.ControlChars> module in the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="ca202-122">Para usar esta constante en un programa sin un alias, se tendría que escribir el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="ca202-122">To use this constant in a program without an alias, you would need to type the following code:</span></span>  
  
 [!code-vb[VbVbalrApplication#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_1.vb)]  
  
 <span data-ttu-id="ca202-123">`Imports` instrucciones siempre deben ser las primeras líneas inmediatamente después de cualquier `Option` las instrucciones de un módulo.</span><span class="sxs-lookup"><span data-stu-id="ca202-123">`Imports` statements must always be the first lines immediately following any `Option` statements in a module.</span></span> <span data-ttu-id="ca202-124">El fragmento de código siguiente muestra cómo importar y asignar un alias para el <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> módulo:</span><span class="sxs-lookup"><span data-stu-id="ca202-124">The following code fragment shows how to import and assign an alias to the <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> module:</span></span>  
  
 [!code-vb[VbVbalrApplication#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_2.vb)]  
  
 <span data-ttu-id="ca202-125">Referencia futura a este espacio de nombres puede ser mucho más breves:</span><span class="sxs-lookup"><span data-stu-id="ca202-125">Future references to this namespace can be considerably shorter:</span></span>  
  
 [!code-vb[VbVbalrApplication#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_3.vb)]  
  
 <span data-ttu-id="ca202-126">Si un `Imports` instrucción no incluye un nombre de alias, se pueden usar elementos definidos en el espacio de nombres importado en el módulo sin calificación.</span><span class="sxs-lookup"><span data-stu-id="ca202-126">If an `Imports` statement does not include an alias name, elements defined within the imported namespace can be used in the module without qualification.</span></span> <span data-ttu-id="ca202-127">Si se especifica el nombre de alias, debe usarse como calificador para los nombres dentro de ese espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="ca202-127">If the alias name is specified, it must be used as a qualifier for names contained within that namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca202-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca202-128">See also</span></span>

- <xref:Microsoft.VisualBasic.ControlChars>
- <xref:Microsoft.VisualBasic>
- [<span data-ttu-id="ca202-129">Espacios de nombres en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ca202-129">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="ca202-130">Ensamblados y Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="ca202-130">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)
- <span data-ttu-id="ca202-131">[Cómo: Crear y utilizar ensamblados mediante la línea de comandos](../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="ca202-131">[How to: Create and Use Assemblies Using the Command Line](../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md)</span></span>
- [<span data-ttu-id="ca202-132">Imports (instrucción), espacio de nombres y tipo .NET</span><span class="sxs-lookup"><span data-stu-id="ca202-132">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)

---
title: Referencias y la instrucción Imports
ms.date: 07/20/2015
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references [Visual Basic], assembly
- namespaces [Visual Basic], assemblies
- referencing assemblies
- Imports statement [Visual Basic], referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
ms.openlocfilehash: 31b4fe001f2b8a62ac30488053c57cd186020421
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347272"
---
# <a name="references-and-the-imports-statement-visual-basic"></a><span data-ttu-id="d0790-102">Referencias y la instrucción Imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d0790-102">References and the Imports Statement (Visual Basic)</span></span>
<span data-ttu-id="d0790-103">Puede hacer que los objetos externos estén disponibles para el proyecto eligiendo el comando **Agregar referencia** en el menú **proyecto** .</span><span class="sxs-lookup"><span data-stu-id="d0790-103">You can make external objects available to your project by choosing the **Add Reference** command on the **Project** menu.</span></span> <span data-ttu-id="d0790-104">Las referencias en Visual Basic pueden apuntar a ensamblados, que son similares a las bibliotecas de tipos, pero contienen más información.</span><span class="sxs-lookup"><span data-stu-id="d0790-104">References in Visual Basic can point to assemblies, which are like type libraries but contain more information.</span></span>  
  
## <a name="the-imports-statement"></a><span data-ttu-id="d0790-105">La instrucción Imports</span><span class="sxs-lookup"><span data-stu-id="d0790-105">The Imports Statement</span></span>  
 <span data-ttu-id="d0790-106">Los ensamblados incluyen uno o varios espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="d0790-106">Assemblies include one or more namespaces.</span></span> <span data-ttu-id="d0790-107">Al agregar una referencia a un ensamblado, también puede Agregar una instrucción `Imports` a un módulo que controla la visibilidad de los espacios de nombres de ese ensamblado en el módulo.</span><span class="sxs-lookup"><span data-stu-id="d0790-107">When you add a reference to an assembly, you can also add an `Imports` statement to a module that controls the visibility of that assembly's namespaces within the module.</span></span> <span data-ttu-id="d0790-108">La instrucción `Imports` proporciona un contexto de ámbito que le permite usar solo la parte del espacio de nombres necesaria para proporcionar una referencia única.</span><span class="sxs-lookup"><span data-stu-id="d0790-108">The `Imports` statement provides a scoping context that lets you use only the portion of the namespace necessary to supply a unique reference.</span></span>  
  
 <span data-ttu-id="d0790-109">La instrucción `Imports` tiene la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="d0790-109">The `Imports` statement has the following syntax:</span></span>  
  
 `Imports [Aliasname =] Namespace`  
  
 <span data-ttu-id="d0790-110">`Aliasname` hace referencia a un nombre corto que puede usar en el código para hacer referencia a un espacio de nombres importado.</span><span class="sxs-lookup"><span data-stu-id="d0790-110">`Aliasname` refers to a short name you can use within code to refer to an imported namespace.</span></span> <span data-ttu-id="d0790-111">`Namespace` es un espacio de nombres disponible a través de una referencia de proyecto, a través de una definición dentro del proyecto o a través de una instrucción de `Imports` anterior.</span><span class="sxs-lookup"><span data-stu-id="d0790-111">`Namespace` is a namespace available through either a project reference, through a definition within the project, or through a previous `Imports` statement.</span></span>  
  
 <span data-ttu-id="d0790-112">Un módulo puede contener cualquier número de instrucciones `Imports`.</span><span class="sxs-lookup"><span data-stu-id="d0790-112">A module may contain any number of `Imports` statements.</span></span> <span data-ttu-id="d0790-113">Deben aparecer después de cualquier instrucción `Option`, si está presente, pero antes de cualquier otro código.</span><span class="sxs-lookup"><span data-stu-id="d0790-113">They must appear after any `Option` statements, if present, but before any other code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d0790-114">No confunda las referencias de proyecto con la instrucción `Imports` o la instrucción `Declare`.</span><span class="sxs-lookup"><span data-stu-id="d0790-114">Do not confuse project references with the `Imports` statement or the `Declare` statement.</span></span> <span data-ttu-id="d0790-115">Las referencias de proyecto hacen que los objetos externos, como los objetos de los ensamblados, estén disponibles para proyectos de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d0790-115">Project references make external objects, such as objects in assemblies, available to Visual Basic projects.</span></span> <span data-ttu-id="d0790-116">La instrucción `Imports` se usa para simplificar el acceso a las referencias del proyecto, pero no proporciona acceso a estos objetos.</span><span class="sxs-lookup"><span data-stu-id="d0790-116">The `Imports` statement is used to simplify access to project references, but does not provide access to these objects.</span></span> <span data-ttu-id="d0790-117">La instrucción `Declare` se utiliza para declarar una referencia a un procedimiento externo en una biblioteca de vínculos dinámicos (DLL).</span><span class="sxs-lookup"><span data-stu-id="d0790-117">The `Declare` statement is used to declare a reference to an external procedure in a dynamic-link library (DLL).</span></span>  
  
## <a name="using-aliases-with-the-imports-statement"></a><span data-ttu-id="d0790-118">Usar alias con la instrucción Imports</span><span class="sxs-lookup"><span data-stu-id="d0790-118">Using Aliases with the Imports Statement</span></span>  
 <span data-ttu-id="d0790-119">La instrucción `Imports` facilita el acceso a los métodos de las clases, ya que elimina la necesidad de escribir explícitamente los nombres completos de las referencias.</span><span class="sxs-lookup"><span data-stu-id="d0790-119">The `Imports` statement makes it easier to access methods of classes by eliminating the need to explicitly type the fully qualified names of references.</span></span> <span data-ttu-id="d0790-120">Los alias permiten asignar un nombre más descriptivo a solo una parte de un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="d0790-120">Aliases let you assign a friendlier name to just one part of a namespace.</span></span> <span data-ttu-id="d0790-121">Por ejemplo, la secuencia de retorno de carro/avance de línea que hace que se muestre un único fragmento de texto en varias líneas forma parte del módulo de <xref:Microsoft.VisualBasic.ControlChars> en el espacio de nombres <xref:Microsoft.VisualBasic?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d0790-121">For example, the carriage return/line feed sequence that causes a single piece of text to be displayed on multiple lines is part of the <xref:Microsoft.VisualBasic.ControlChars> module in the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="d0790-122">Para usar esta constante en un programa sin un alias, debe escribir el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="d0790-122">To use this constant in a program without an alias, you would need to type the following code:</span></span>  
  
 [!code-vb[VbVbalrApplication#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#3)]  
  
 <span data-ttu-id="d0790-123">`Imports` instrucciones siempre deben ser las primeras líneas inmediatamente después de cualquier instrucción `Option` de un módulo.</span><span class="sxs-lookup"><span data-stu-id="d0790-123">`Imports` statements must always be the first lines immediately following any `Option` statements in a module.</span></span> <span data-ttu-id="d0790-124">En el siguiente fragmento de código se muestra cómo importar y asignar un alias al módulo <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="d0790-124">The following code fragment shows how to import and assign an alias to the <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> module:</span></span>  
  
 [!code-vb[VbVbalrApplication#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#4)]  
  
 <span data-ttu-id="d0790-125">Las referencias futuras a este espacio de nombres pueden ser mucho más cortas:</span><span class="sxs-lookup"><span data-stu-id="d0790-125">Future references to this namespace can be considerably shorter:</span></span>  
  
 [!code-vb[VbVbalrApplication#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#5)]  
  
 <span data-ttu-id="d0790-126">Si una instrucción `Imports` no incluye un nombre de alias, los elementos definidos en el espacio de nombres importado se pueden usar en el módulo sin calificación.</span><span class="sxs-lookup"><span data-stu-id="d0790-126">If an `Imports` statement does not include an alias name, elements defined within the imported namespace can be used in the module without qualification.</span></span> <span data-ttu-id="d0790-127">Si se especifica el nombre de alias, se debe usar como calificador para los nombres contenidos dentro de ese espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="d0790-127">If the alias name is specified, it must be used as a qualifier for names contained within that namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0790-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0790-128">See also</span></span>

- <xref:Microsoft.VisualBasic.ControlChars>
- <xref:Microsoft.VisualBasic>
- [<span data-ttu-id="d0790-129">Espacios de nombres en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d0790-129">Namespaces in Visual Basic</span></span>](namespaces.md)
- [<span data-ttu-id="d0790-130">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="d0790-130">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="d0790-131">Imports (instrucción), espacio de nombres y tipo .NET</span><span class="sxs-lookup"><span data-stu-id="d0790-131">Imports Statement (.NET Namespace and Type)</span></span>](../../language-reference/statements/imports-statement-net-namespace-and-type.md)

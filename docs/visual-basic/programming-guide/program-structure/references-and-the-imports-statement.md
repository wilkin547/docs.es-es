---
title: Instrucción Imports y referencias
ms.date: 07/20/2015
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references [Visual Basic], assembly
- namespaces [Visual Basic], assemblies
- referencing assemblies
- Imports statement [Visual Basic], referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
ms.openlocfilehash: 13f250e1b015e5a821da83e557033bc878a8a3b8
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097909"
---
# <a name="references-and-the-imports-statement-visual-basic"></a><span data-ttu-id="631f6-102">Referencias y la instrucción Imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="631f6-102">References and the Imports Statement (Visual Basic)</span></span>

<span data-ttu-id="631f6-103">Puede hacer que los objetos externos estén disponibles para el proyecto eligiendo el comando **Agregar referencia** en el menú **proyecto** .</span><span class="sxs-lookup"><span data-stu-id="631f6-103">You can make external objects available to your project by choosing the **Add Reference** command on the **Project** menu.</span></span> <span data-ttu-id="631f6-104">Las referencias en Visual Basic pueden apuntar a ensamblados, que son similares a las bibliotecas de tipos, pero contienen más información.</span><span class="sxs-lookup"><span data-stu-id="631f6-104">References in Visual Basic can point to assemblies, which are like type libraries but contain more information.</span></span>  
  
## <a name="the-imports-statement"></a><span data-ttu-id="631f6-105">La instrucción Imports</span><span class="sxs-lookup"><span data-stu-id="631f6-105">The Imports Statement</span></span>  

 <span data-ttu-id="631f6-106">Los ensamblados incluyen uno o varios espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="631f6-106">Assemblies include one or more namespaces.</span></span> <span data-ttu-id="631f6-107">Al agregar una referencia a un ensamblado, también puede Agregar una `Imports` instrucción a un módulo que controla la visibilidad de los espacios de nombres de ese ensamblado en el módulo.</span><span class="sxs-lookup"><span data-stu-id="631f6-107">When you add a reference to an assembly, you can also add an `Imports` statement to a module that controls the visibility of that assembly's namespaces within the module.</span></span> <span data-ttu-id="631f6-108">La `Imports` instrucción proporciona un contexto de ámbito que le permite usar solo la parte del espacio de nombres necesaria para proporcionar una referencia única.</span><span class="sxs-lookup"><span data-stu-id="631f6-108">The `Imports` statement provides a scoping context that lets you use only the portion of the namespace necessary to supply a unique reference.</span></span>  
  
 <span data-ttu-id="631f6-109">La `Imports` instrucción tiene la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="631f6-109">The `Imports` statement has the following syntax:</span></span>  
  
 `Imports [Aliasname =] Namespace`  
  
 <span data-ttu-id="631f6-110">`Aliasname` hace referencia a un nombre corto que puede usar en el código para hacer referencia a un espacio de nombres importado.</span><span class="sxs-lookup"><span data-stu-id="631f6-110">`Aliasname` refers to a short name you can use within code to refer to an imported namespace.</span></span> <span data-ttu-id="631f6-111">`Namespace` es un espacio de nombres disponible a través de una referencia de proyecto, a través de una definición dentro del proyecto o a través de una `Imports` instrucción anterior.</span><span class="sxs-lookup"><span data-stu-id="631f6-111">`Namespace` is a namespace available through either a project reference, through a definition within the project, or through a previous `Imports` statement.</span></span>  
  
 <span data-ttu-id="631f6-112">Un módulo puede contener cualquier número de `Imports` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="631f6-112">A module may contain any number of `Imports` statements.</span></span> <span data-ttu-id="631f6-113">Deben aparecer después de cualquier `Option` instrucción, si está presente, pero antes de cualquier otro código.</span><span class="sxs-lookup"><span data-stu-id="631f6-113">They must appear after any `Option` statements, if present, but before any other code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="631f6-114">No confunda las referencias de proyecto con la `Imports` instrucción o la `Declare` instrucción.</span><span class="sxs-lookup"><span data-stu-id="631f6-114">Do not confuse project references with the `Imports` statement or the `Declare` statement.</span></span> <span data-ttu-id="631f6-115">Las referencias de proyecto hacen que los objetos externos, como los objetos de los ensamblados, estén disponibles para proyectos de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="631f6-115">Project references make external objects, such as objects in assemblies, available to Visual Basic projects.</span></span> <span data-ttu-id="631f6-116">La `Imports` instrucción se usa para simplificar el acceso a las referencias del proyecto, pero no proporciona acceso a estos objetos.</span><span class="sxs-lookup"><span data-stu-id="631f6-116">The `Imports` statement is used to simplify access to project references, but does not provide access to these objects.</span></span> <span data-ttu-id="631f6-117">La `Declare` instrucción se utiliza para declarar una referencia a un procedimiento externo en una biblioteca de vínculos dinámicos (dll).</span><span class="sxs-lookup"><span data-stu-id="631f6-117">The `Declare` statement is used to declare a reference to an external procedure in a dynamic-link library (DLL).</span></span>  
  
## <a name="using-aliases-with-the-imports-statement"></a><span data-ttu-id="631f6-118">Usar alias con la instrucción Imports</span><span class="sxs-lookup"><span data-stu-id="631f6-118">Using Aliases with the Imports Statement</span></span>  

 <span data-ttu-id="631f6-119">La `Imports` instrucción facilita el acceso a los métodos de las clases, ya que elimina la necesidad de escribir explícitamente los nombres completos de las referencias.</span><span class="sxs-lookup"><span data-stu-id="631f6-119">The `Imports` statement makes it easier to access methods of classes by eliminating the need to explicitly type the fully qualified names of references.</span></span> <span data-ttu-id="631f6-120">Los alias permiten asignar un nombre más descriptivo a solo una parte de un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="631f6-120">Aliases let you assign a friendlier name to just one part of a namespace.</span></span> <span data-ttu-id="631f6-121">Por ejemplo, la secuencia de retorno de carro/avance de línea que hace que se muestre un único fragmento de texto en varias líneas es parte del <xref:Microsoft.VisualBasic.ControlChars> módulo en el <xref:Microsoft.VisualBasic?displayProperty=nameWithType> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="631f6-121">For example, the carriage return/line feed sequence that causes a single piece of text to be displayed on multiple lines is part of the <xref:Microsoft.VisualBasic.ControlChars> module in the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="631f6-122">Para usar esta constante en un programa sin un alias, debe escribir el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="631f6-122">To use this constant in a program without an alias, you would need to type the following code:</span></span>  
  
 [!code-vb[VbVbalrApplication#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#3)]  
  
 <span data-ttu-id="631f6-123">`Imports` las instrucciones siempre deben ser las primeras líneas inmediatamente después `Option` de cualquier instrucción de un módulo.</span><span class="sxs-lookup"><span data-stu-id="631f6-123">`Imports` statements must always be the first lines immediately following any `Option` statements in a module.</span></span> <span data-ttu-id="631f6-124">En el siguiente fragmento de código se muestra cómo importar y asignar un alias al <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> módulo:</span><span class="sxs-lookup"><span data-stu-id="631f6-124">The following code fragment shows how to import and assign an alias to the <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> module:</span></span>  
  
 [!code-vb[VbVbalrApplication#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#4)]  
  
 <span data-ttu-id="631f6-125">Las referencias futuras a este espacio de nombres pueden ser mucho más cortas:</span><span class="sxs-lookup"><span data-stu-id="631f6-125">Future references to this namespace can be considerably shorter:</span></span>  
  
 [!code-vb[VbVbalrApplication#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#5)]  
  
 <span data-ttu-id="631f6-126">Si una `Imports` instrucción no incluye un nombre de alias, los elementos definidos en el espacio de nombres importado se pueden usar en el módulo sin calificación.</span><span class="sxs-lookup"><span data-stu-id="631f6-126">If an `Imports` statement does not include an alias name, elements defined within the imported namespace can be used in the module without qualification.</span></span> <span data-ttu-id="631f6-127">Si se especifica el nombre de alias, se debe usar como calificador para los nombres contenidos dentro de ese espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="631f6-127">If the alias name is specified, it must be used as a qualifier for names contained within that namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="631f6-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="631f6-128">See also</span></span>

- <xref:Microsoft.VisualBasic.ControlChars>
- <xref:Microsoft.VisualBasic>
- [<span data-ttu-id="631f6-129">Espacios de nombres en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="631f6-129">Namespaces in Visual Basic</span></span>](namespaces.md)
- [<span data-ttu-id="631f6-130">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="631f6-130">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="631f6-131">Instrucción Imports (Tipo y espacio de nombres de .NET)</span><span class="sxs-lookup"><span data-stu-id="631f6-131">Imports Statement (.NET Namespace and Type)</span></span>](../../language-reference/statements/imports-statement-net-namespace-and-type.md)

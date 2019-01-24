---
title: Convenciones de nomenclatura de Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- names [Visual Basic], Visual Basic rules
- naming conventions
- naming conventions [Visual Basic], Visual Basic
- Visual Basic code, naming conventions
- conventions [Visual Basic], Visual Basic coding
- names [Visual Basic], naming conventions
- naming conventions [Visual Basic], classes
ms.assetid: 164949a4-2a7c-4736-9d82-9c3078e2e56c
ms.openlocfilehash: ebb9d21e32993f2eb035993d32dc3de7d97b49f6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672141"
---
# <a name="visual-basic-naming-conventions"></a><span data-ttu-id="d35da-102">Convenciones de nomenclatura de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d35da-102">Visual Basic Naming Conventions</span></span>
<span data-ttu-id="d35da-103">Al dar nombre a un elemento en la aplicación de Visual Basic, el primer carácter del nombre debe ser un carácter alfabético o un carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="d35da-103">When you name an element in your Visual Basic application, the first character of that name must be an alphabetic character or an underscore.</span></span> <span data-ttu-id="d35da-104">Sin embargo, tenga en cuenta que los nombres que empiezan por un carácter de subrayado no son compatibles con el [independencia del lenguaje y componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span><span class="sxs-lookup"><span data-stu-id="d35da-104">Note, however, that names beginning with an underscore are not compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span>  
  
 <span data-ttu-id="d35da-105">Las sugerencias siguientes se aplican a la nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="d35da-105">The following suggestions apply to naming.</span></span>  
  
-   <span data-ttu-id="d35da-106">Empiece cada palabra independiente de un nombre con una letra mayúscula, como en `FindLastRecord` y `RedrawMyForm`.</span><span class="sxs-lookup"><span data-stu-id="d35da-106">Begin each separate word in a name with a capital letter, as in `FindLastRecord` and `RedrawMyForm`.</span></span>  
  
-   <span data-ttu-id="d35da-107">Empiece los nombres de función y método con un verbo, como en `InitNameArray` o `CloseDialog`.</span><span class="sxs-lookup"><span data-stu-id="d35da-107">Begin function and method names with a verb, as in `InitNameArray` or `CloseDialog`.</span></span>  
  
-   <span data-ttu-id="d35da-108">Empezar a la clase, estructura, módulo y los nombres de propiedad y un sustantivo, como en `EmployeeName` o `CarAccessory`.</span><span class="sxs-lookup"><span data-stu-id="d35da-108">Begin class, structure, module, and property names with a noun, as in `EmployeeName` or `CarAccessory`.</span></span>  
  
-   <span data-ttu-id="d35da-109">Empiece los nombres de interfaz con el prefijo "I", seguido por un nombre o una frase del sistema, como `IComponent`, o con un adjetivo que describe el comportamiento de la interfaz, como `IPersistable`.</span><span class="sxs-lookup"><span data-stu-id="d35da-109">Begin interface names with the prefix "I", followed by a noun or a noun phrase, like `IComponent`, or with an adjective describing the interface's behavior, like `IPersistable`.</span></span> <span data-ttu-id="d35da-110">No utilice el carácter de subrayado y utilizar las abreviaturas con moderación, ya que pueden causar confusión.</span><span class="sxs-lookup"><span data-stu-id="d35da-110">Do not use the underscore, and use abbreviations sparingly, because abbreviations can cause confusion.</span></span>  
  
-   <span data-ttu-id="d35da-111">Empiece los nombres de controlador de eventos y un sustantivo que describe el tipo de evento seguido por el "`EventHandler`"sufijo, como en"`MouseEventHandler`".</span><span class="sxs-lookup"><span data-stu-id="d35da-111">Begin event handler names with a noun describing the type of event followed by the "`EventHandler`" suffix, as in "`MouseEventHandler`".</span></span>  
  
-   <span data-ttu-id="d35da-112">En los nombres de las clases de argumento de evento, incluya el "`EventArgs`" sufijo.</span><span class="sxs-lookup"><span data-stu-id="d35da-112">In names of event argument classes, include the "`EventArgs`" suffix.</span></span>  
  
-   <span data-ttu-id="d35da-113">Si un evento tiene un concepto de "before" o "after", utilice un sufijo en tiempo presente o pasado, como en "`ControlAdd`"o"`ControlAdded`".</span><span class="sxs-lookup"><span data-stu-id="d35da-113">If an event has a concept of "before" or "after," use a suffix in present or past tense, as in "`ControlAdd`" or "`ControlAdded`".</span></span>  
  
-   <span data-ttu-id="d35da-114">Para términos largos o utilizados con frecuencia, utilice abreviaturas para mantener las longitudes de nombre razonable, por ejemplo, "HTML", en lugar de "Lenguaje de marcado de hipertexto".</span><span class="sxs-lookup"><span data-stu-id="d35da-114">For long or frequently used terms, use abbreviations to keep name lengths reasonable, for example, "HTML", instead of "Hypertext Markup Language".</span></span> <span data-ttu-id="d35da-115">En general, los nombres de variable mayores que 32 caracteres son difíciles de leer en un monitor configurado con una resolución baja.</span><span class="sxs-lookup"><span data-stu-id="d35da-115">In general, variable names greater than 32 characters are difficult to read on a monitor set to a low resolution.</span></span> <span data-ttu-id="d35da-116">Además, asegúrese de que sus abreviaturas son coherentes en toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d35da-116">Also, make sure your abbreviations are consistent throughout the entire application.</span></span> <span data-ttu-id="d35da-117">Cambio de forma aleatoria en un proyecto entre "HTML" y "Lenguaje de marcado de hipertexto" puede crearle confusión.</span><span class="sxs-lookup"><span data-stu-id="d35da-117">Randomly switching in a project between "HTML" and "Hypertext Markup Language" can lead to confusion.</span></span>  
  
-   <span data-ttu-id="d35da-118">Evite el uso de nombres en un ámbito interno que son los mismos que los nombres en un ámbito externo.</span><span class="sxs-lookup"><span data-stu-id="d35da-118">Avoid using names in an inner scope that are the same as names in an outer scope.</span></span> <span data-ttu-id="d35da-119">Puede producir un error si se tiene acceso a la variable equivocada.</span><span class="sxs-lookup"><span data-stu-id="d35da-119">Errors can result if the wrong variable is accessed.</span></span> <span data-ttu-id="d35da-120">Si se produce un conflicto entre una variable y la palabra clave del mismo nombre, debe identificar la palabra clave anteponiendo la biblioteca de tipos adecuado.</span><span class="sxs-lookup"><span data-stu-id="d35da-120">If a conflict occurs between a variable and the keyword of the same name, you must identify the keyword by preceding it with the appropriate type library.</span></span> <span data-ttu-id="d35da-121">Por ejemplo, si tiene una variable denominada `Date`, puede usar la función intrínseca `Date` función solo mediante una llamada a <xref:System.DateTime.Date%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d35da-121">For example, if you have a variable called `Date`, you can use the intrinsic `Date` function only by calling <xref:System.DateTime.Date%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d35da-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="d35da-122">See also</span></span>
- [<span data-ttu-id="d35da-123">Palabras clave como nombres de elementos en código</span><span class="sxs-lookup"><span data-stu-id="d35da-123">Keywords as Element Names in Code</span></span>](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)
- [<span data-ttu-id="d35da-124">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="d35da-124">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="d35da-125">Nombres de elementos declarados</span><span class="sxs-lookup"><span data-stu-id="d35da-125">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="d35da-126">Convenciones de código y estructura de programas</span><span class="sxs-lookup"><span data-stu-id="d35da-126">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="d35da-127">Referencia del lenguaje Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d35da-127">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)

---
title: Convenciones de nomenclatura
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
ms.openlocfilehash: 98fdda2934c9df1b33f41b6e0442a39246efe168
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347317"
---
# <a name="visual-basic-naming-conventions"></a><span data-ttu-id="50797-102">Convenciones de nomenclatura de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="50797-102">Visual Basic Naming Conventions</span></span>
<span data-ttu-id="50797-103">Al asignar un nombre a un elemento en la aplicación Visual Basic, el primer carácter de ese nombre debe ser un carácter alfabético o un carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="50797-103">When you name an element in your Visual Basic application, the first character of that name must be an alphabetic character or an underscore.</span></span> <span data-ttu-id="50797-104">Sin embargo, tenga en cuenta que los nombres que empiezan por un carácter de subrayado no son compatibles con la [independencia del lenguaje y los componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span><span class="sxs-lookup"><span data-stu-id="50797-104">Note, however, that names beginning with an underscore are not compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span>  
  
 <span data-ttu-id="50797-105">Las sugerencias siguientes se aplican a la asignación de nombres.</span><span class="sxs-lookup"><span data-stu-id="50797-105">The following suggestions apply to naming.</span></span>  
  
- <span data-ttu-id="50797-106">Comience cada palabra independiente en un nombre con una letra mayúscula, como en `FindLastRecord` y `RedrawMyForm`.</span><span class="sxs-lookup"><span data-stu-id="50797-106">Begin each separate word in a name with a capital letter, as in `FindLastRecord` and `RedrawMyForm`.</span></span>  
  
- <span data-ttu-id="50797-107">Los nombres de función y método de inicio con un verbo, como en `InitNameArray` o `CloseDialog`.</span><span class="sxs-lookup"><span data-stu-id="50797-107">Begin function and method names with a verb, as in `InitNameArray` or `CloseDialog`.</span></span>  
  
- <span data-ttu-id="50797-108">Empiece la clase, la estructura, el módulo y los nombres de propiedad con un nombre, como en `EmployeeName` o `CarAccessory`.</span><span class="sxs-lookup"><span data-stu-id="50797-108">Begin class, structure, module, and property names with a noun, as in `EmployeeName` or `CarAccessory`.</span></span>  
  
- <span data-ttu-id="50797-109">Comience los nombres de interfaz con el prefijo "I", seguido de un sustantivo o un sustantivo, como `IComponent`, o con un adjetivo que describa el comportamiento de la interfaz, como `IPersistable`.</span><span class="sxs-lookup"><span data-stu-id="50797-109">Begin interface names with the prefix "I", followed by a noun or a noun phrase, like `IComponent`, or with an adjective describing the interface's behavior, like `IPersistable`.</span></span> <span data-ttu-id="50797-110">No use el carácter de subrayado y use las abreviaturas con moderación, ya que las abreviaturas pueden causar confusión.</span><span class="sxs-lookup"><span data-stu-id="50797-110">Do not use the underscore, and use abbreviations sparingly, because abbreviations can cause confusion.</span></span>  
  
- <span data-ttu-id="50797-111">Comience los nombres de los controladores de eventos con un nombre que describa el tipo de evento seguido del sufijo "`EventHandler`", como en "`MouseEventHandler`".</span><span class="sxs-lookup"><span data-stu-id="50797-111">Begin event handler names with a noun describing the type of event followed by the "`EventHandler`" suffix, as in "`MouseEventHandler`".</span></span>  
  
- <span data-ttu-id="50797-112">En los nombres de las clases de argumento de evento, incluya el sufijo "`EventArgs`".</span><span class="sxs-lookup"><span data-stu-id="50797-112">In names of event argument classes, include the "`EventArgs`" suffix.</span></span>  
  
- <span data-ttu-id="50797-113">Si un evento tiene un concepto de "Before" o "after", use un sufijo en el pasado o en el pasado, como en "`ControlAdd`" o "`ControlAdded`".</span><span class="sxs-lookup"><span data-stu-id="50797-113">If an event has a concept of "before" or "after," use a suffix in present or past tense, as in "`ControlAdd`" or "`ControlAdded`".</span></span>  
  
- <span data-ttu-id="50797-114">Para términos largos o usados con frecuencia, use abreviaturas para mantener las longitudes de nombre razonables, por ejemplo, "HTML", en lugar de "Lenguaje de marcado de hipertexto".</span><span class="sxs-lookup"><span data-stu-id="50797-114">For long or frequently used terms, use abbreviations to keep name lengths reasonable, for example, "HTML", instead of "Hypertext Markup Language".</span></span> <span data-ttu-id="50797-115">En general, los nombres de variable de más de 32 caracteres son difíciles de leer en un monitor establecido en una resolución baja.</span><span class="sxs-lookup"><span data-stu-id="50797-115">In general, variable names greater than 32 characters are difficult to read on a monitor set to a low resolution.</span></span> <span data-ttu-id="50797-116">Además, asegúrese de que las abreviaturas son coherentes en toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="50797-116">Also, make sure your abbreviations are consistent throughout the entire application.</span></span> <span data-ttu-id="50797-117">El cambio aleatorio de un proyecto entre "HTML" y "Lenguaje de marcado de hipertexto" puede producir confusión.</span><span class="sxs-lookup"><span data-stu-id="50797-117">Randomly switching in a project between "HTML" and "Hypertext Markup Language" can lead to confusion.</span></span>  
  
- <span data-ttu-id="50797-118">Evite usar nombres en un ámbito interno que coincidan con los nombres de un ámbito externo.</span><span class="sxs-lookup"><span data-stu-id="50797-118">Avoid using names in an inner scope that are the same as names in an outer scope.</span></span> <span data-ttu-id="50797-119">Se pueden producir errores si se tiene acceso a la variable equivocada.</span><span class="sxs-lookup"><span data-stu-id="50797-119">Errors can result if the wrong variable is accessed.</span></span> <span data-ttu-id="50797-120">Si se produce un conflicto entre una variable y la palabra clave con el mismo nombre, debe identificar la palabra clave anteponiendo la biblioteca de tipos adecuada.</span><span class="sxs-lookup"><span data-stu-id="50797-120">If a conflict occurs between a variable and the keyword of the same name, you must identify the keyword by preceding it with the appropriate type library.</span></span> <span data-ttu-id="50797-121">Por ejemplo, si tiene una variable denominada `Date`, puede usar la función de `Date` intrínseca solo mediante una llamada a <xref:System.DateTime.Date%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="50797-121">For example, if you have a variable called `Date`, you can use the intrinsic `Date` function only by calling <xref:System.DateTime.Date%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50797-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="50797-122">See also</span></span>

- [<span data-ttu-id="50797-123">Palabras clave como nombres de elementos en código</span><span class="sxs-lookup"><span data-stu-id="50797-123">Keywords as Element Names in Code</span></span>](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)
- [<span data-ttu-id="50797-124">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="50797-124">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="50797-125">Nombres de elementos declarados</span><span class="sxs-lookup"><span data-stu-id="50797-125">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="50797-126">Convenciones de código y estructura de programas</span><span class="sxs-lookup"><span data-stu-id="50797-126">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="50797-127">Referencia del lenguaje Visual Basic</span><span class="sxs-lookup"><span data-stu-id="50797-127">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)

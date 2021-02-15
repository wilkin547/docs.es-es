---
description: 'Más información acerca de: Visual Basic convenciones de nomenclatura'
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
ms.openlocfilehash: 058d3b06ca1da71c4d8993c6bd451531ec758dbd
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100461013"
---
# <a name="visual-basic-naming-conventions"></a><span data-ttu-id="63964-103">Convenciones de nomenclatura de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="63964-103">Visual Basic Naming Conventions</span></span>

<span data-ttu-id="63964-104">Al asignar un nombre a un elemento en la aplicación Visual Basic, el primer carácter de ese nombre debe ser un carácter alfabético o un carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="63964-104">When you name an element in your Visual Basic application, the first character of that name must be an alphabetic character or an underscore.</span></span> <span data-ttu-id="63964-105">Sin embargo, tenga en cuenta que los nombres que empiezan por un carácter de subrayado no son compatibles con la [independencia del lenguaje y los componentes de Language-Independent](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span><span class="sxs-lookup"><span data-stu-id="63964-105">Note, however, that names beginning with an underscore are not compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span>  
  
 <span data-ttu-id="63964-106">Las sugerencias siguientes se aplican a la asignación de nombres.</span><span class="sxs-lookup"><span data-stu-id="63964-106">The following suggestions apply to naming.</span></span>  
  
- <span data-ttu-id="63964-107">Empiece cada palabra independiente en un nombre con una letra mayúscula, como en `FindLastRecord` y `RedrawMyForm` .</span><span class="sxs-lookup"><span data-stu-id="63964-107">Begin each separate word in a name with a capital letter, as in `FindLastRecord` and `RedrawMyForm`.</span></span>  
  
- <span data-ttu-id="63964-108">Comience los nombres de función y método con un verbo, como en `InitNameArray` o `CloseDialog` .</span><span class="sxs-lookup"><span data-stu-id="63964-108">Begin function and method names with a verb, as in `InitNameArray` or `CloseDialog`.</span></span>  
  
- <span data-ttu-id="63964-109">Empiece la clase, la estructura, el módulo y los nombres de propiedad con un nombre, como en `EmployeeName` o `CarAccessory` .</span><span class="sxs-lookup"><span data-stu-id="63964-109">Begin class, structure, module, and property names with a noun, as in `EmployeeName` or `CarAccessory`.</span></span>  
  
- <span data-ttu-id="63964-110">Comience los nombres de interfaz con el prefijo "I", seguido de un sustantivo o un sustantivo, como `IComponent` , o con un adjetivo que describa el comportamiento de la interfaz, como `IPersistable` .</span><span class="sxs-lookup"><span data-stu-id="63964-110">Begin interface names with the prefix "I", followed by a noun or a noun phrase, like `IComponent`, or with an adjective describing the interface's behavior, like `IPersistable`.</span></span> <span data-ttu-id="63964-111">No use el carácter de subrayado y use las abreviaturas con moderación, ya que las abreviaturas pueden causar confusión.</span><span class="sxs-lookup"><span data-stu-id="63964-111">Do not use the underscore, and use abbreviations sparingly, because abbreviations can cause confusion.</span></span>  
  
- <span data-ttu-id="63964-112">Comience los nombres de los controladores de eventos con un nombre que describa el tipo de evento seguido del `EventHandler` sufijo "", como en " `MouseEventHandler` ".</span><span class="sxs-lookup"><span data-stu-id="63964-112">Begin event handler names with a noun describing the type of event followed by the "`EventHandler`" suffix, as in "`MouseEventHandler`".</span></span>  
  
- <span data-ttu-id="63964-113">En los nombres de las clases de argumento de evento, incluya el `EventArgs` sufijo "".</span><span class="sxs-lookup"><span data-stu-id="63964-113">In names of event argument classes, include the "`EventArgs`" suffix.</span></span>  
  
- <span data-ttu-id="63964-114">Si un evento tiene un concepto de "Before" o "after", use un sufijo en el pasado o en el pasado, como en " `ControlAdd` " o " `ControlAdded` ".</span><span class="sxs-lookup"><span data-stu-id="63964-114">If an event has a concept of "before" or "after," use a suffix in present or past tense, as in "`ControlAdd`" or "`ControlAdded`".</span></span>  
  
- <span data-ttu-id="63964-115">Para términos largos o usados con frecuencia, use abreviaturas para mantener las longitudes de nombre razonables, por ejemplo, "HTML", en lugar de "Lenguaje de marcado de hipertexto".</span><span class="sxs-lookup"><span data-stu-id="63964-115">For long or frequently used terms, use abbreviations to keep name lengths reasonable, for example, "HTML", instead of "Hypertext Markup Language".</span></span> <span data-ttu-id="63964-116">En general, los nombres de variable de más de 32 caracteres son difíciles de leer en un monitor establecido en una resolución baja.</span><span class="sxs-lookup"><span data-stu-id="63964-116">In general, variable names greater than 32 characters are difficult to read on a monitor set to a low resolution.</span></span> <span data-ttu-id="63964-117">Además, asegúrese de que las abreviaturas son coherentes en toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="63964-117">Also, make sure your abbreviations are consistent throughout the entire application.</span></span> <span data-ttu-id="63964-118">El cambio aleatorio de un proyecto entre "HTML" y "Lenguaje de marcado de hipertexto" puede producir confusión.</span><span class="sxs-lookup"><span data-stu-id="63964-118">Randomly switching in a project between "HTML" and "Hypertext Markup Language" can lead to confusion.</span></span>  
  
- <span data-ttu-id="63964-119">Evite usar nombres en un ámbito interno que coincidan con los nombres de un ámbito externo.</span><span class="sxs-lookup"><span data-stu-id="63964-119">Avoid using names in an inner scope that are the same as names in an outer scope.</span></span> <span data-ttu-id="63964-120">Se pueden producir errores si se tiene acceso a la variable equivocada.</span><span class="sxs-lookup"><span data-stu-id="63964-120">Errors can result if the wrong variable is accessed.</span></span> <span data-ttu-id="63964-121">Si se produce un conflicto entre una variable y la palabra clave con el mismo nombre, debe identificar la palabra clave anteponiendo la biblioteca de tipos adecuada.</span><span class="sxs-lookup"><span data-stu-id="63964-121">If a conflict occurs between a variable and the keyword of the same name, you must identify the keyword by preceding it with the appropriate type library.</span></span> <span data-ttu-id="63964-122">Por ejemplo, si tiene una variable denominada `Date` , solo puede utilizar la función intrínseca `Date` llamando a <xref:System.DateTime.Date%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="63964-122">For example, if you have a variable called `Date`, you can use the intrinsic `Date` function only by calling <xref:System.DateTime.Date%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63964-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="63964-123">See also</span></span>

- [<span data-ttu-id="63964-124">Palabras clave como nombres de elementos en el código</span><span class="sxs-lookup"><span data-stu-id="63964-124">Keywords as Element Names in Code</span></span>](keywords-as-element-names-in-code.md)
- [<span data-ttu-id="63964-125">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="63964-125">Me, My, MyBase, and MyClass</span></span>](me-my-mybase-and-myclass.md)
- [<span data-ttu-id="63964-126">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="63964-126">Declared Element Names</span></span>](../language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="63964-127">Convenciones de código y estructura de programas</span><span class="sxs-lookup"><span data-stu-id="63964-127">Program Structure and Code Conventions</span></span>](program-structure-and-code-conventions.md)
- [<span data-ttu-id="63964-128">Referencia del lenguaje Visual Basic</span><span class="sxs-lookup"><span data-stu-id="63964-128">Visual Basic Language Reference</span></span>](../../language-reference/index.md)

---
title: Lista de atributos (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: adfb980380bb787280715ca0185950657e174eb1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="attribute-list-visual-basic"></a><span data-ttu-id="46dc8-102">Lista de atributos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46dc8-102">Attribute List (Visual Basic)</span></span>
<span data-ttu-id="46dc8-103">Especifica los atributos que se aplicará a un elemento de programación declarado.</span><span class="sxs-lookup"><span data-stu-id="46dc8-103">Specifies the attributes to be applied to a declared programming element.</span></span> <span data-ttu-id="46dc8-104">Los diversos atributos se separan con comas.</span><span class="sxs-lookup"><span data-stu-id="46dc8-104">Multiple attributes are separated by commas.</span></span> <span data-ttu-id="46dc8-105">A continuación se muestra la sintaxis para un atributo.</span><span class="sxs-lookup"><span data-stu-id="46dc8-105">Following is the syntax for one attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46dc8-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="46dc8-106">Syntax</span></span>  
  
```  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="46dc8-107">Elementos</span><span class="sxs-lookup"><span data-stu-id="46dc8-107">Parts</span></span>  
 `attributemodifier`  
 <span data-ttu-id="46dc8-108">Obligatorio para atributos aplicados al principio de un archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="46dc8-108">Required for attributes applied at the beginning of a source file.</span></span> <span data-ttu-id="46dc8-109">Puede ser [ensamblado](../../../visual-basic/language-reference/modifiers/assembly.md) o [módulo](../../../visual-basic/language-reference/modifiers/module-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="46dc8-109">Can be [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) or [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md).</span></span>  
  
 `attributename`  
 <span data-ttu-id="46dc8-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="46dc8-110">Required.</span></span> <span data-ttu-id="46dc8-111">Nombre del atributo.</span><span class="sxs-lookup"><span data-stu-id="46dc8-111">Name of the attribute.</span></span>  
  
 `attributearguments`  
 <span data-ttu-id="46dc8-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="46dc8-112">Optional.</span></span> <span data-ttu-id="46dc8-113">Lista de argumentos posicionales para este atributo.</span><span class="sxs-lookup"><span data-stu-id="46dc8-113">List of positional arguments for this attribute.</span></span> <span data-ttu-id="46dc8-114">Varios argumentos están separados por comas.</span><span class="sxs-lookup"><span data-stu-id="46dc8-114">Multiple arguments are separated by commas.</span></span>  
  
 `attributeinitializer`  
 <span data-ttu-id="46dc8-115">Opcional.</span><span class="sxs-lookup"><span data-stu-id="46dc8-115">Optional.</span></span> <span data-ttu-id="46dc8-116">Lista de inicializadores de variable o propiedad para este atributo.</span><span class="sxs-lookup"><span data-stu-id="46dc8-116">List of variable or property initializers for this attribute.</span></span> <span data-ttu-id="46dc8-117">Inicializadores múltiples se separan por comas.</span><span class="sxs-lookup"><span data-stu-id="46dc8-117">Multiple initializers are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46dc8-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="46dc8-118">Remarks</span></span>  
 <span data-ttu-id="46dc8-119">Puede aplicar uno o más atributos a casi cualquier elemento de programación (tipos, procedimientos, propiedades y así sucesivamente).</span><span class="sxs-lookup"><span data-stu-id="46dc8-119">You can apply one or more attributes to nearly any programming element (types, procedures, properties, and so forth).</span></span> <span data-ttu-id="46dc8-120">Los atributos aparecen en los metadatos del ensamblado, y pueden ayudarle a anotar el código o especificar cómo se utiliza un elemento de programación determinado.</span><span class="sxs-lookup"><span data-stu-id="46dc8-120">Attributes appear in your assembly's metadata, and they can help you annotate your code or specify how to use a particular programming element.</span></span> <span data-ttu-id="46dc8-121">Puede aplicar atributos definidos por Visual Basic y .NET Framework, y puede definir sus propios atributos.</span><span class="sxs-lookup"><span data-stu-id="46dc8-121">You can apply attributes defined by Visual Basic and the .NET Framework, and you can define your own attributes.</span></span>  

 <span data-ttu-id="46dc8-122">Para obtener más información sobre cuándo utilizar los atributos, vea [información general de atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="46dc8-122">For more information on when to use attributes, see [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md).</span></span> <span data-ttu-id="46dc8-123">Para obtener información sobre nombres de atributo, vea [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="46dc8-123">For information on attribute names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="46dc8-124">Reglas</span><span class="sxs-lookup"><span data-stu-id="46dc8-124">Rules</span></span>  
  
-   <span data-ttu-id="46dc8-125">**Selección de ubicación.**</span><span class="sxs-lookup"><span data-stu-id="46dc8-125">**Placement.**</span></span> <span data-ttu-id="46dc8-126">Puede aplicar atributos a elementos de programación más declarados.</span><span class="sxs-lookup"><span data-stu-id="46dc8-126">You can apply attributes to most declared programming elements.</span></span> <span data-ttu-id="46dc8-127">Para aplicar uno o más atributos, coloque un *bloque de atributos* al principio de la declaración del elemento.</span><span class="sxs-lookup"><span data-stu-id="46dc8-127">To apply one or more attributes, you place an *attribute block* at the beginning of the element declaration.</span></span> <span data-ttu-id="46dc8-128">Cada entrada de la lista de atributos especifica un atributo que se va a aplicar, y el modificador y argumentos que está utilizando para esta invocación del atributo.</span><span class="sxs-lookup"><span data-stu-id="46dc8-128">Each entry in the attribute list specifies an attribute you wish to apply, and the modifier and arguments you are using for this invocation of the attribute.</span></span>  
  
-   <span data-ttu-id="46dc8-129">**Corchetes angulares.**</span><span class="sxs-lookup"><span data-stu-id="46dc8-129">**Angle Brackets.**</span></span> <span data-ttu-id="46dc8-130">Si se proporciona una lista de atributos, debe encerrar entre corchetes angulares ("`<`"y"`>`").</span><span class="sxs-lookup"><span data-stu-id="46dc8-130">If you supply an attribute list, you must enclose it in angle brackets ("`<`" and "`>`").</span></span>  
  
-   <span data-ttu-id="46dc8-131">**Parte de la declaración.**</span><span class="sxs-lookup"><span data-stu-id="46dc8-131">**Part of the Declaration.**</span></span> <span data-ttu-id="46dc8-132">El atributo debe formar parte de la declaración del elemento, no una instrucción independiente.</span><span class="sxs-lookup"><span data-stu-id="46dc8-132">The attribute must be part of the element declaration, not a separate statement.</span></span> <span data-ttu-id="46dc8-133">Puede usar la secuencia de continuación de línea (" `_`") para ampliar la instrucción de declaración en varias líneas de código fuente.</span><span class="sxs-lookup"><span data-stu-id="46dc8-133">You can use the line-continuation sequence (" `_`") to extend the declaration statement onto multiple source-code lines.</span></span>  
  
-   <span data-ttu-id="46dc8-134">**Modificadores.**</span><span class="sxs-lookup"><span data-stu-id="46dc8-134">**Modifiers.**</span></span> <span data-ttu-id="46dc8-135">Un modificador de atributo (`Assembly` o `Module`) es necesario en cada atributo aplicado a un elemento de programación al principio de un archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="46dc8-135">An attribute modifier (`Assembly` or `Module`) is required on every attribute applied to a programming element at the beginning of a source file.</span></span> <span data-ttu-id="46dc8-136">No se permiten modificadores de atributo en atributos aplicados a los elementos que no están al principio de un archivo de origen.</span><span class="sxs-lookup"><span data-stu-id="46dc8-136">Attribute modifiers are not allowed on attributes applied to elements that are not at the beginning of a source file.</span></span>  
  
-   <span data-ttu-id="46dc8-137">**Argumentos.**</span><span class="sxs-lookup"><span data-stu-id="46dc8-137">**Arguments.**</span></span> <span data-ttu-id="46dc8-138">Todos los argumentos posicionales para un atributo deben preceder a cualquier inicializador de variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="46dc8-138">All positional arguments for an attribute must precede any variable or property initializers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46dc8-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="46dc8-139">Example</span></span>  
 <span data-ttu-id="46dc8-140">El ejemplo siguiente aplica el <xref:System.Runtime.InteropServices.DllImportAttribute> atributo a un esquema de definición de un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="46dc8-140">The following example applies the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute to a skeleton definition of a `Function` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/attribute-list_1.vb)]  
  
 <span data-ttu-id="46dc8-141"><xref:System.Runtime.InteropServices.DllImportAttribute>indica que el procedimiento con atributos representa un punto de entrada en una biblioteca de vínculos dinámicos (DLL) no administrada.</span><span class="sxs-lookup"><span data-stu-id="46dc8-141"><xref:System.Runtime.InteropServices.DllImportAttribute> indicates that the attributed procedure represents an entry point in an unmanaged dynamic-link library (DLL).</span></span> <span data-ttu-id="46dc8-142">El atributo proporciona el nombre de archivo DLL como un argumento de posición y el resto de información como inicializadores de variables.</span><span class="sxs-lookup"><span data-stu-id="46dc8-142">The attribute supplies the DLL name as a positional argument and the other information as variable initializers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46dc8-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="46dc8-143">See Also</span></span>  
 [<span data-ttu-id="46dc8-144">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="46dc8-144">Assembly</span></span>](../../../visual-basic/language-reference/modifiers/assembly.md)  
 [<span data-ttu-id="46dc8-145">Module \<keyword></span><span class="sxs-lookup"><span data-stu-id="46dc8-145">Module \<keyword></span></span>](../../../visual-basic/language-reference/modifiers/module-keyword.md)  
 [<span data-ttu-id="46dc8-146">Información general de atributos</span><span class="sxs-lookup"><span data-stu-id="46dc8-146">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="46dc8-147">Interrumpir y combinar instrucciones en código</span><span class="sxs-lookup"><span data-stu-id="46dc8-147">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)

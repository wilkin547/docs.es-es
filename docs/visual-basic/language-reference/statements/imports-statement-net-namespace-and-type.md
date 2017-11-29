---
title: "Instrucción Imports (Tipo y espacio de nombres de .NET)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Imports
- imports
helpviewer_keywords:
- declared element names [Visual Basic], qualification
- imports [Visual Basic]
- Imports statement [Visual Basic]
- aliases [Visual Basic], Imports statement
- container elements [Visual Basic]
- namespaces [Visual Basic], importing
- Imports statement [Visual Basic], syntax
- import aliases [Visual Basic]
- aliases [Visual Basic], import
- declared elements [Visual Basic], container elements
ms.assetid: 7062f8aa-d890-4232-9eed-92836e13fb6e
caps.latest.revision: "40"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 46cc78c2fd039fb56fd4d1b797f2d09cbe95d317
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imports-statement-net-namespace-and-type"></a><span data-ttu-id="ad727-102">Instrucción Imports (Tipo y espacio de nombres de .NET)</span><span class="sxs-lookup"><span data-stu-id="ad727-102">Imports Statement (.NET Namespace and Type)</span></span>
<span data-ttu-id="ad727-103">Permite nombres que hace referencia sin calificación de espacio de nombres de tipo.</span><span class="sxs-lookup"><span data-stu-id="ad727-103">Enables type names to be referenced without namespace qualification.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad727-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad727-104">Syntax</span></span>  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## <a name="parts"></a><span data-ttu-id="ad727-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="ad727-105">Parts</span></span>  
  
|<span data-ttu-id="ad727-106">Término</span><span class="sxs-lookup"><span data-stu-id="ad727-106">Term</span></span>|<span data-ttu-id="ad727-107">Definición</span><span class="sxs-lookup"><span data-stu-id="ad727-107">Definition</span></span>|  
|---|---|  
|`aliasname`|<span data-ttu-id="ad727-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="ad727-108">Optional.</span></span> <span data-ttu-id="ad727-109">Un *alias de importación* o el nombre por el que el código puede hacer referencia a `namespace` en lugar de la cadena de calificación completa.</span><span class="sxs-lookup"><span data-stu-id="ad727-109">An *import alias* or name by which code can refer to `namespace` instead of the full qualification string.</span></span> <span data-ttu-id="ad727-110">Vea [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="ad727-110">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`namespace`|<span data-ttu-id="ad727-111">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ad727-111">Required.</span></span> <span data-ttu-id="ad727-112">El nombre completo del espacio de nombres que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="ad727-112">The fully qualified name of the namespace being imported.</span></span> <span data-ttu-id="ad727-113">Puede ser una cadena de espacios de nombres anidada a cualquier nivel.</span><span class="sxs-lookup"><span data-stu-id="ad727-113">Can be a string of namespaces nested to any level.</span></span>|  
|`element`|<span data-ttu-id="ad727-114">Opcional.</span><span class="sxs-lookup"><span data-stu-id="ad727-114">Optional.</span></span> <span data-ttu-id="ad727-115">El nombre de un elemento de programación declarado en el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="ad727-115">The name of a programming element declared in the namespace.</span></span> <span data-ttu-id="ad727-116">Puede ser cualquier elemento contenedor.</span><span class="sxs-lookup"><span data-stu-id="ad727-116">Can be any container element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad727-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ad727-117">Remarks</span></span>  
 <span data-ttu-id="ad727-118">El `Imports` instrucción permite los tipos que se encuentran en un espacio de nombres que hace referencia directamente.</span><span class="sxs-lookup"><span data-stu-id="ad727-118">The `Imports`  statement enables types that are contained in a given namespace to be referenced directly.</span></span>  
  
 <span data-ttu-id="ad727-119">Puede proporcionar un nombre de espacio de nombres único o una cadena de espacios de nombres anidados.</span><span class="sxs-lookup"><span data-stu-id="ad727-119">You can supply a single namespace name or a string of nested namespaces.</span></span> <span data-ttu-id="ad727-120">Cada espacio de nombres anidado se separa del siguiente espacio de nombres de nivel superior con un punto (`.`), como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ad727-120">Each nested namespace is separated from the next higher level namespace by a period (`.`), as the following example illustrates.</span></span>  
  
 `Imports System.Collections.Generic`  
  
 <span data-ttu-id="ad727-121">Cada archivo de código fuente puede contener cualquier número de `Imports` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="ad727-121">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="ad727-122">Éstas deben seguir las declaraciones de opción existentes, como el `Option Strict` instrucción y se debe preceder a cualquier declaración de elemento de programación como `Module` o `Class` las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="ad727-122">These must follow any option declarations, such as the `Option Strict` statement, and they must precede any programming element declarations, such as `Module` or `Class` statements.</span></span>  
  
 <span data-ttu-id="ad727-123">Puede usar `Imports` sólo en el nivel de archivo.</span><span class="sxs-lookup"><span data-stu-id="ad727-123">You can use `Imports` only at file level.</span></span> <span data-ttu-id="ad727-124">Esto significa que el contexto de la declaración para la importación debe ser un archivo de origen y no puede ser un espacio de nombres, clase, estructura, módulo, interfaz, procedimiento o bloque.</span><span class="sxs-lookup"><span data-stu-id="ad727-124">This means the declaration context for importation must be a source file, and cannot be a namespace, class, structure, module, interface, procedure, or block.</span></span>  
  
 <span data-ttu-id="ad727-125">Tenga en cuenta que el `Imports` instrucción no hace que estén disponibles para el proyecto de elementos de otros proyectos y ensamblados.</span><span class="sxs-lookup"><span data-stu-id="ad727-125">Note that the `Imports` statement does not make elements from other projects and assemblies available to your project.</span></span> <span data-ttu-id="ad727-126">La importación no ocupar el lugar de establecer una referencia.</span><span class="sxs-lookup"><span data-stu-id="ad727-126">Importing does not take the place of setting a reference.</span></span> <span data-ttu-id="ad727-127">Sólo quita la necesidad de calificar nombres que ya están disponibles para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="ad727-127">It only removes the need to qualify names that are already available to your project.</span></span> <span data-ttu-id="ad727-128">Para obtener más información, vea "Importar elementos contenedores" en [referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="ad727-128">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad727-129">Puede definir implícita `Imports` instrucciones mediante el uso de la [página referencias, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="ad727-129">You can define implicit `Imports` statements by using the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span> <span data-ttu-id="ad727-130">Para obtener más información, consulte [Cómo: agregar o quitar espacios de nombres importados (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="ad727-130">For more information, see [How to: Add or Remove Imported Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span></span>  
  
## <a name="import-aliases"></a><span data-ttu-id="ad727-131">Alias de importación</span><span class="sxs-lookup"><span data-stu-id="ad727-131">Import Aliases</span></span>  
 <span data-ttu-id="ad727-132">Un *alias de importación* define el alias para un espacio de nombres o tipo.</span><span class="sxs-lookup"><span data-stu-id="ad727-132">An *import alias* defines the alias for a namespace or type.</span></span> <span data-ttu-id="ad727-133">Alias de importación son útiles cuando necesite utilizar los elementos con el mismo nombre que se declaran en uno o varios espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="ad727-133">Import aliases are useful when you need to use items with the same name that are declared in one or more namespaces.</span></span> <span data-ttu-id="ad727-134">Para obtener más información y un ejemplo, vea "Calificar un nombre de elemento" en [referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="ad727-134">For more information and an example, see "Qualifying an Element Name" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="ad727-135">No se deben declarar un miembro en el nivel de módulo con el mismo nombre que `aliasname`.</span><span class="sxs-lookup"><span data-stu-id="ad727-135">You should not declare a member at module level with the same name as `aliasname`.</span></span> <span data-ttu-id="ad727-136">Si lo hace, el compilador de Visual Basic utiliza `aliasname` solo para el miembro declarado y ya no se reconoce como un alias de importación.</span><span class="sxs-lookup"><span data-stu-id="ad727-136">If you do, the Visual Basic compiler uses `aliasname` only for the declared member and no longer recognizes it as an import alias.</span></span>  
  
 <span data-ttu-id="ad727-137">Aunque la sintaxis utilizada para declarar un alias de importación que se utiliza para importar un prefijo de espacio de nombres XML, los resultados son diferentes.</span><span class="sxs-lookup"><span data-stu-id="ad727-137">Although the syntax used for declaring an import alias is like that used for importing an XML namespace prefix, the results are different.</span></span> <span data-ttu-id="ad727-138">Un alias de importación se puede usar como una expresión en el código, mientras que un prefijo de espacio de nombres XML se puede utilizar únicamente en literales XML o propiedades de eje XML como el prefijo para un elemento completo o el nombre del atributo.</span><span class="sxs-lookup"><span data-stu-id="ad727-138">An import alias can be used as an expression in your code, whereas an XML namespace prefix can be used only in XML literals or XML axis properties as the prefix for a qualified element or attribute name.</span></span>  
  
### <a name="element-names"></a><span data-ttu-id="ad727-139">Nombres de elementos</span><span class="sxs-lookup"><span data-stu-id="ad727-139">Element Names</span></span>  
 <span data-ttu-id="ad727-140">Si proporciona `element`, debe representar un *elemento contenedor*, es decir, un elemento de programación que puede contener otros elementos.</span><span class="sxs-lookup"><span data-stu-id="ad727-140">If you supply `element`, it must represent a *container element*, that is, a programming element that can contain other elements.</span></span> <span data-ttu-id="ad727-141">Elementos contenedores incluyen clases, estructuras, módulos, interfaces y enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="ad727-141">Container elements include classes, structures, modules, interfaces, and enumerations.</span></span>  
  
 <span data-ttu-id="ad727-142">El ámbito de los elementos facilitados por un `Imports` instrucción depende de si se especifica `element`.</span><span class="sxs-lookup"><span data-stu-id="ad727-142">The scope of the elements made available by an `Imports` statement depends on whether you specify `element`.</span></span> <span data-ttu-id="ad727-143">Si solo especifica `namespace`, todo de forma exclusiva con el nombre de los miembros de ese espacio de nombres y los miembros de elementos contenedores dentro de ese espacio de nombres, están disponibles sin calificación.</span><span class="sxs-lookup"><span data-stu-id="ad727-143">If you specify only `namespace`, all uniquely named members of that namespace, and members of container elements within that namespace, are available without qualification.</span></span> <span data-ttu-id="ad727-144">Si se especifican ambas `namespace` y `element`, solo los miembros de ese elemento están disponibles sin calificación.</span><span class="sxs-lookup"><span data-stu-id="ad727-144">If you specify both `namespace` and `element`, only the members of that element are available without qualification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad727-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad727-145">Example</span></span>  
 <span data-ttu-id="ad727-146">El ejemplo siguiente devuelve todas las carpetas en el directorio C:\ utilizando la <xref:System.IO.DirectoryInfo> clase.</span><span class="sxs-lookup"><span data-stu-id="ad727-146">The following example returns all the folders in the C:\ directory by using the <xref:System.IO.DirectoryInfo> class.</span></span>  
  
 <span data-ttu-id="ad727-147">El código no tiene ningún `Imports` las instrucciones en la parte superior del archivo.</span><span class="sxs-lookup"><span data-stu-id="ad727-147">The code has no `Imports` statements at the top of the file.</span></span> <span data-ttu-id="ad727-148">Por lo tanto, la `DirectoryInfo`, <xref:System.Text.StringBuilder>, y <xref:Microsoft.VisualBasic.ControlChars.CrLf> referencias son todos los nombres completos con los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="ad727-148">Therefore, the `DirectoryInfo`, <xref:System.Text.StringBuilder>, and <xref:Microsoft.VisualBasic.ControlChars.CrLf> references are all fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#152](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="ad727-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad727-149">Example</span></span>  
 <span data-ttu-id="ad727-150">En el ejemplo siguiente se incluye `Imports` instrucciones para los espacios de nombres que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="ad727-150">The following example includes `Imports` statements for the referenced namespaces.</span></span> <span data-ttu-id="ad727-151">Por lo tanto, los tipos no tiene que ser un nombre completo con los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="ad727-151">Therefore, the types do not have to be fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#153](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_2.vb)]  
  
 [!code-vb[VbVbalrStatements#154](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="ad727-152">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad727-152">Example</span></span>  
 <span data-ttu-id="ad727-153">En el ejemplo siguiente se incluye `Imports` instrucciones que crean los alias para los espacios de nombres que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="ad727-153">The following example includes `Imports` statements that create aliases for the referenced namespaces.</span></span> <span data-ttu-id="ad727-154">Los tipos se califican con el alias.</span><span class="sxs-lookup"><span data-stu-id="ad727-154">The types are qualified with the aliases.</span></span>  
  
 [!code-vb[VbVbalrStatements#155](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_4.vb)]  
  
 [!code-vb[VbVbalrStatements#156](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_5.vb)]  
  
## <a name="example"></a><span data-ttu-id="ad727-155">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad727-155">Example</span></span>  
 <span data-ttu-id="ad727-156">En el ejemplo siguiente se incluye `Imports` instrucciones que crean los alias para los tipos que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="ad727-156">The following example includes `Imports` statements that create aliases for the referenced types.</span></span> <span data-ttu-id="ad727-157">Alias se usan para especificar los tipos.</span><span class="sxs-lookup"><span data-stu-id="ad727-157">Aliases are used to specify the types.</span></span>  
  
 [!code-vb[VbVbalrStatements#157](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_6.vb)]  
  
 [!code-vb[VbVbalrStatements#158](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_7.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ad727-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad727-158">See Also</span></span>  
 [<span data-ttu-id="ad727-159">Namespace (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ad727-159">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="ad727-160">Espacios de nombres en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ad727-160">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="ad727-161">Referencias y la instrucción Imports</span><span class="sxs-lookup"><span data-stu-id="ad727-161">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [<span data-ttu-id="ad727-162">Imports (instrucción), espacio de nombres XML</span><span class="sxs-lookup"><span data-stu-id="ad727-162">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)  
 [<span data-ttu-id="ad727-163">Referencias a elementos declarados</span><span class="sxs-lookup"><span data-stu-id="ad727-163">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)

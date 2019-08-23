---
title: 'Instrucción Imports: tipo y espacio de nombres .NET (Visual Basic)'
ms.date: 07/20/2015
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
ms.openlocfilehash: a0b7a6a5fd16dc0daa620e6b490ddfdeb0e7c80e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912386"
---
# <a name="imports-statement-net-namespace-and-type"></a><span data-ttu-id="d1933-102">Instrucción Imports (Tipo y espacio de nombres de .NET)</span><span class="sxs-lookup"><span data-stu-id="d1933-102">Imports Statement (.NET Namespace and Type)</span></span>
<span data-ttu-id="d1933-103">Permite hacer referencia a los nombres de tipo sin la calificación de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="d1933-103">Enables type names to be referenced without namespace qualification.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1933-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d1933-104">Syntax</span></span>  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## <a name="parts"></a><span data-ttu-id="d1933-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="d1933-105">Parts</span></span>  
  
|<span data-ttu-id="d1933-106">Término</span><span class="sxs-lookup"><span data-stu-id="d1933-106">Term</span></span>|<span data-ttu-id="d1933-107">Definición</span><span class="sxs-lookup"><span data-stu-id="d1933-107">Definition</span></span>|  
|---|---|  
|`aliasname`|<span data-ttu-id="d1933-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="d1933-108">Optional.</span></span> <span data-ttu-id="d1933-109">Un *alias de importación* o nombre con el que el código `namespace` puede hacer referencia en lugar de la cadena de calificación completa.</span><span class="sxs-lookup"><span data-stu-id="d1933-109">An *import alias* or name by which code can refer to `namespace` instead of the full qualification string.</span></span> <span data-ttu-id="d1933-110">Vea [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="d1933-110">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`namespace`|<span data-ttu-id="d1933-111">Necesario.</span><span class="sxs-lookup"><span data-stu-id="d1933-111">Required.</span></span> <span data-ttu-id="d1933-112">Nombre completo del espacio de nombres que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="d1933-112">The fully qualified name of the namespace being imported.</span></span> <span data-ttu-id="d1933-113">Puede ser una cadena de espacios de nombres anidados en cualquier nivel.</span><span class="sxs-lookup"><span data-stu-id="d1933-113">Can be a string of namespaces nested to any level.</span></span>|  
|`element`|<span data-ttu-id="d1933-114">Opcional.</span><span class="sxs-lookup"><span data-stu-id="d1933-114">Optional.</span></span> <span data-ttu-id="d1933-115">Nombre de un elemento de programación declarado en el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="d1933-115">The name of a programming element declared in the namespace.</span></span> <span data-ttu-id="d1933-116">Puede ser cualquier elemento contenedor.</span><span class="sxs-lookup"><span data-stu-id="d1933-116">Can be any container element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1933-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d1933-117">Remarks</span></span>  
 <span data-ttu-id="d1933-118">La `Imports` instrucción permite hacer referencia directamente a los tipos contenidos en un espacio de nombres determinado.</span><span class="sxs-lookup"><span data-stu-id="d1933-118">The `Imports`  statement enables types that are contained in a given namespace to be referenced directly.</span></span>  
  
 <span data-ttu-id="d1933-119">Puede proporcionar un único nombre de espacio de nombres o una cadena de espacios de nombres anidados.</span><span class="sxs-lookup"><span data-stu-id="d1933-119">You can supply a single namespace name or a string of nested namespaces.</span></span> <span data-ttu-id="d1933-120">Cada espacio de nombres anidado se separa del siguiente espacio de nombres de nivel superior`.`en un punto (), como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="d1933-120">Each nested namespace is separated from the next higher level namespace by a period (`.`), as the following example illustrates.</span></span>  
  
 `Imports System.Collections.Generic`  
  
 <span data-ttu-id="d1933-121">Cada archivo de código fuente puede contener cualquier `Imports` número de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="d1933-121">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="d1933-122">Estos deben seguir cualquier declaración de opción, como la `Option Strict` instrucción, y deben preceder a cualquier declaración de elemento de programación, `Module` como instrucciones `Class` o.</span><span class="sxs-lookup"><span data-stu-id="d1933-122">These must follow any option declarations, such as the `Option Strict` statement, and they must precede any programming element declarations, such as `Module` or `Class` statements.</span></span>  
  
 <span data-ttu-id="d1933-123">Solo se puede `Imports` usar en el nivel de archivo.</span><span class="sxs-lookup"><span data-stu-id="d1933-123">You can use `Imports` only at file level.</span></span> <span data-ttu-id="d1933-124">Esto significa que el contexto de la declaración para la importación debe ser un archivo de código fuente y no puede ser un espacio de nombres, una clase, una estructura, un módulo, una interfaz, un procedimiento o un bloque.</span><span class="sxs-lookup"><span data-stu-id="d1933-124">This means the declaration context for importation must be a source file, and cannot be a namespace, class, structure, module, interface, procedure, or block.</span></span>  
  
 <span data-ttu-id="d1933-125">Tenga en cuenta `Imports` que la instrucción no hace que los elementos de otros proyectos y ensamblados estén disponibles para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="d1933-125">Note that the `Imports` statement does not make elements from other projects and assemblies available to your project.</span></span> <span data-ttu-id="d1933-126">La importación no se ocupa del establecimiento de una referencia.</span><span class="sxs-lookup"><span data-stu-id="d1933-126">Importing does not take the place of setting a reference.</span></span> <span data-ttu-id="d1933-127">Solo elimina la necesidad de calificar nombres que ya están disponibles para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="d1933-127">It only removes the need to qualify names that are already available to your project.</span></span> <span data-ttu-id="d1933-128">Para obtener más información, vea "importar elementos contenedores" en [referencias a elementos](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)declarados.</span><span class="sxs-lookup"><span data-stu-id="d1933-128">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d1933-129">Puede definir instrucciones implícitas `Imports` mediante la [Página referencias, el diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="d1933-129">You can define implicit `Imports` statements by using the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span> <span data-ttu-id="d1933-130">Para obtener más información, consulte [Cómo Agregar o quitar espacios de nombres importados (Visual Basic](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic)).</span><span class="sxs-lookup"><span data-stu-id="d1933-130">For more information, see [How to: Add or Remove Imported Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span></span>  
  
## <a name="import-aliases"></a><span data-ttu-id="d1933-131">Alias de importación</span><span class="sxs-lookup"><span data-stu-id="d1933-131">Import Aliases</span></span>  
 <span data-ttu-id="d1933-132">Un *alias de importación* define el alias de un espacio de nombres o de un tipo.</span><span class="sxs-lookup"><span data-stu-id="d1933-132">An *import alias* defines the alias for a namespace or type.</span></span> <span data-ttu-id="d1933-133">Los alias de importación son útiles cuando es necesario usar elementos con el mismo nombre que se declaran en uno o varios espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="d1933-133">Import aliases are useful when you need to use items with the same name that are declared in one or more namespaces.</span></span> <span data-ttu-id="d1933-134">Para obtener más información y un ejemplo, vea "calificar un nombre de elemento" en [referencias a elementos](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)declarados.</span><span class="sxs-lookup"><span data-stu-id="d1933-134">For more information and an example, see "Qualifying an Element Name" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="d1933-135">No debe declarar un miembro en el nivel de módulo con el mismo nombre `aliasname`que.</span><span class="sxs-lookup"><span data-stu-id="d1933-135">You should not declare a member at module level with the same name as `aliasname`.</span></span> <span data-ttu-id="d1933-136">Si lo hace, el compilador `aliasname` de Visual Basic solo utiliza para el miembro declarado y ya no lo reconoce como un alias de importación.</span><span class="sxs-lookup"><span data-stu-id="d1933-136">If you do, the Visual Basic compiler uses `aliasname` only for the declared member and no longer recognizes it as an import alias.</span></span>  
  
 <span data-ttu-id="d1933-137">Aunque la sintaxis que se usa para declarar un alias de importación es similar a la que se usa para importar un prefijo de espacio de nombres XML, los resultados son diferentes.</span><span class="sxs-lookup"><span data-stu-id="d1933-137">Although the syntax used for declaring an import alias is like that used for importing an XML namespace prefix, the results are different.</span></span> <span data-ttu-id="d1933-138">Un alias de importación se puede usar como una expresión en el código, mientras que un prefijo de espacio de nombres XML solo se puede usar en literales XML o propiedades de eje XML como prefijo para un nombre de elemento o atributo calificado.</span><span class="sxs-lookup"><span data-stu-id="d1933-138">An import alias can be used as an expression in your code, whereas an XML namespace prefix can be used only in XML literals or XML axis properties as the prefix for a qualified element or attribute name.</span></span>  
  
### <a name="element-names"></a><span data-ttu-id="d1933-139">Nombres de elementos</span><span class="sxs-lookup"><span data-stu-id="d1933-139">Element Names</span></span>  
 <span data-ttu-id="d1933-140">Si proporciona `element`, debe representar un *elemento contenedor*, es decir, un elemento de programación que puede contener otros elementos.</span><span class="sxs-lookup"><span data-stu-id="d1933-140">If you supply `element`, it must represent a *container element*, that is, a programming element that can contain other elements.</span></span> <span data-ttu-id="d1933-141">Los elementos de contenedor incluyen clases, estructuras, módulos, interfaces y enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="d1933-141">Container elements include classes, structures, modules, interfaces, and enumerations.</span></span>  
  
 <span data-ttu-id="d1933-142">El ámbito de los elementos que se ponen a `Imports` disposición de una instrucción depende de `element`si se especifica.</span><span class="sxs-lookup"><span data-stu-id="d1933-142">The scope of the elements made available by an `Imports` statement depends on whether you specify `element`.</span></span> <span data-ttu-id="d1933-143">Si solo `namespace`especifica, todos los miembros con el nombre único de ese espacio de nombres y los miembros de los elementos contenedores dentro de ese espacio de nombres están disponibles sin calificación.</span><span class="sxs-lookup"><span data-stu-id="d1933-143">If you specify only `namespace`, all uniquely named members of that namespace, and members of container elements within that namespace, are available without qualification.</span></span> <span data-ttu-id="d1933-144">Si especifica `namespace` y `element`, solo estarán disponibles los miembros de ese elemento sin calificación.</span><span class="sxs-lookup"><span data-stu-id="d1933-144">If you specify both `namespace` and `element`, only the members of that element are available without qualification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1933-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d1933-145">Example</span></span>  
 <span data-ttu-id="d1933-146">En el ejemplo siguiente se devuelven todas las carpetas de C:\ directorio mediante la <xref:System.IO.DirectoryInfo> clase.</span><span class="sxs-lookup"><span data-stu-id="d1933-146">The following example returns all the folders in the C:\ directory by using the <xref:System.IO.DirectoryInfo> class.</span></span>  
  
 <span data-ttu-id="d1933-147">El código no tiene `Imports` ninguna instrucción en la parte superior del archivo.</span><span class="sxs-lookup"><span data-stu-id="d1933-147">The code has no `Imports` statements at the top of the file.</span></span> <span data-ttu-id="d1933-148">Por lo tanto `DirectoryInfo`, <xref:System.Text.StringBuilder>las referencias <xref:Microsoft.VisualBasic.ControlChars.CrLf> , y se califican totalmente con los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="d1933-148">Therefore, the `DirectoryInfo`, <xref:System.Text.StringBuilder>, and <xref:Microsoft.VisualBasic.ControlChars.CrLf> references are all fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#152](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#152)]  
  
## <a name="example"></a><span data-ttu-id="d1933-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d1933-149">Example</span></span>  
 <span data-ttu-id="d1933-150">En el ejemplo siguiente `Imports` se incluyen instrucciones para los espacios de nombres a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="d1933-150">The following example includes `Imports` statements for the referenced namespaces.</span></span> <span data-ttu-id="d1933-151">Por lo tanto, no es necesario que los tipos estén completos con los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="d1933-151">Therefore, the types do not have to be fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#153](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#153)]  
  
 [!code-vb[VbVbalrStatements#154](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#154)]  
  
## <a name="example"></a><span data-ttu-id="d1933-152">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d1933-152">Example</span></span>  
 <span data-ttu-id="d1933-153">En el ejemplo siguiente `Imports` se incluyen instrucciones que crean alias para los espacios de nombres a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="d1933-153">The following example includes `Imports` statements that create aliases for the referenced namespaces.</span></span> <span data-ttu-id="d1933-154">Los tipos se califican con los alias.</span><span class="sxs-lookup"><span data-stu-id="d1933-154">The types are qualified with the aliases.</span></span>  
  
 [!code-vb[VbVbalrStatements#155](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#155)]  
  
 [!code-vb[VbVbalrStatements#156](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#156)]  
  
## <a name="example"></a><span data-ttu-id="d1933-155">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d1933-155">Example</span></span>  
 <span data-ttu-id="d1933-156">En el ejemplo siguiente `Imports` se incluyen instrucciones que crean alias para los tipos a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="d1933-156">The following example includes `Imports` statements that create aliases for the referenced types.</span></span> <span data-ttu-id="d1933-157">Los alias se usan para especificar los tipos.</span><span class="sxs-lookup"><span data-stu-id="d1933-157">Aliases are used to specify the types.</span></span>  
  
 [!code-vb[VbVbalrStatements#157](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#157)]  
  
 [!code-vb[VbVbalrStatements#158](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#158)]  
  
## <a name="see-also"></a><span data-ttu-id="d1933-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1933-158">See also</span></span>

- [<span data-ttu-id="d1933-159">Namespace (instrucción)</span><span class="sxs-lookup"><span data-stu-id="d1933-159">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="d1933-160">Espacios de nombres en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d1933-160">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="d1933-161">Referencias y la instrucción Imports</span><span class="sxs-lookup"><span data-stu-id="d1933-161">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="d1933-162">Imports (instrucción), espacio de nombres XML</span><span class="sxs-lookup"><span data-stu-id="d1933-162">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [<span data-ttu-id="d1933-163">Referencias a elementos declarados</span><span class="sxs-lookup"><span data-stu-id="d1933-163">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)

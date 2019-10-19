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
ms.openlocfilehash: 62b208d4795d0370cb6eace7f45ef42551e6960f
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581779"
---
# <a name="imports-statement-net-namespace-and-type"></a><span data-ttu-id="fdebd-102">Instrucción Imports (Tipo y espacio de nombres de .NET)</span><span class="sxs-lookup"><span data-stu-id="fdebd-102">Imports Statement (.NET Namespace and Type)</span></span>
<span data-ttu-id="fdebd-103">Permite hacer referencia a los nombres de tipo sin la calificación de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="fdebd-103">Enables type names to be referenced without namespace qualification.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdebd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fdebd-104">Syntax</span></span>  
  
```vb  
Imports [ aliasname = ] namespace  
' -or-  
Imports [ aliasname = ] namespace.element  
```  
  
## <a name="parts"></a><span data-ttu-id="fdebd-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="fdebd-105">Parts</span></span>  
  
|<span data-ttu-id="fdebd-106">Término</span><span class="sxs-lookup"><span data-stu-id="fdebd-106">Term</span></span>|<span data-ttu-id="fdebd-107">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="fdebd-107">Definition</span></span>|  
|---|---|  
|`aliasname`|<span data-ttu-id="fdebd-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="fdebd-108">Optional.</span></span> <span data-ttu-id="fdebd-109">Un *alias de importación* o nombre con el que el código puede hacer referencia a `namespace` en lugar de la cadena de calificación completa.</span><span class="sxs-lookup"><span data-stu-id="fdebd-109">An *import alias* or name by which code can refer to `namespace` instead of the full qualification string.</span></span> <span data-ttu-id="fdebd-110">Vea [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="fdebd-110">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`namespace`|<span data-ttu-id="fdebd-111">Requerido.</span><span class="sxs-lookup"><span data-stu-id="fdebd-111">Required.</span></span> <span data-ttu-id="fdebd-112">Nombre completo del espacio de nombres que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="fdebd-112">The fully qualified name of the namespace being imported.</span></span> <span data-ttu-id="fdebd-113">Puede ser una cadena de espacios de nombres anidados en cualquier nivel.</span><span class="sxs-lookup"><span data-stu-id="fdebd-113">Can be a string of namespaces nested to any level.</span></span>|  
|`element`|<span data-ttu-id="fdebd-114">Opcional.</span><span class="sxs-lookup"><span data-stu-id="fdebd-114">Optional.</span></span> <span data-ttu-id="fdebd-115">Nombre de un elemento de programación declarado en el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="fdebd-115">The name of a programming element declared in the namespace.</span></span> <span data-ttu-id="fdebd-116">Puede ser cualquier elemento contenedor.</span><span class="sxs-lookup"><span data-stu-id="fdebd-116">Can be any container element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fdebd-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fdebd-117">Remarks</span></span>  
 <span data-ttu-id="fdebd-118">La instrucción `Imports` permite hacer referencia directamente a los tipos contenidos en un espacio de nombres determinado.</span><span class="sxs-lookup"><span data-stu-id="fdebd-118">The `Imports`  statement enables types that are contained in a given namespace to be referenced directly.</span></span>  
  
 <span data-ttu-id="fdebd-119">Puede proporcionar un único nombre de espacio de nombres o una cadena de espacios de nombres anidados.</span><span class="sxs-lookup"><span data-stu-id="fdebd-119">You can supply a single namespace name or a string of nested namespaces.</span></span> <span data-ttu-id="fdebd-120">Cada espacio de nombres anidado se separa del siguiente espacio de nombres de nivel superior en un punto (`.`), como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="fdebd-120">Each nested namespace is separated from the next higher level namespace by a period (`.`), as the following example illustrates.</span></span>  
  
 `Imports System.Collections.Generic`  
  
 <span data-ttu-id="fdebd-121">Cada archivo de código fuente puede contener cualquier número de instrucciones `Imports`.</span><span class="sxs-lookup"><span data-stu-id="fdebd-121">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="fdebd-122">Estos deben seguir cualquier declaración de opción, como la instrucción `Option Strict`, y deben preceder a las declaraciones de elementos de programación, como `Module` o `Class` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="fdebd-122">These must follow any option declarations, such as the `Option Strict` statement, and they must precede any programming element declarations, such as `Module` or `Class` statements.</span></span>  
  
 <span data-ttu-id="fdebd-123">Solo puede usar `Imports` en el nivel de archivo.</span><span class="sxs-lookup"><span data-stu-id="fdebd-123">You can use `Imports` only at file level.</span></span> <span data-ttu-id="fdebd-124">Esto significa que el contexto de la declaración para la importación debe ser un archivo de código fuente y no puede ser un espacio de nombres, una clase, una estructura, un módulo, una interfaz, un procedimiento o un bloque.</span><span class="sxs-lookup"><span data-stu-id="fdebd-124">This means the declaration context for importation must be a source file, and cannot be a namespace, class, structure, module, interface, procedure, or block.</span></span>  
  
 <span data-ttu-id="fdebd-125">Tenga en cuenta que la instrucción `Imports` no hace que los elementos de otros proyectos y ensamblados estén disponibles para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="fdebd-125">Note that the `Imports` statement does not make elements from other projects and assemblies available to your project.</span></span> <span data-ttu-id="fdebd-126">La importación no se ocupa del establecimiento de una referencia.</span><span class="sxs-lookup"><span data-stu-id="fdebd-126">Importing does not take the place of setting a reference.</span></span> <span data-ttu-id="fdebd-127">Solo elimina la necesidad de calificar nombres que ya están disponibles para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="fdebd-127">It only removes the need to qualify names that are already available to your project.</span></span> <span data-ttu-id="fdebd-128">Para obtener más información, vea "importar elementos contenedores" en [referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="fdebd-128">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fdebd-129">Puede definir instrucciones de `Imports` implícitas mediante la [Página referencias, el diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="fdebd-129">You can define implicit `Imports` statements by using the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span> <span data-ttu-id="fdebd-130">Para obtener más información, consulte [Cómo: agregar o quitar espacios de nombres importados (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="fdebd-130">For more information, see [How to: Add or Remove Imported Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span></span>  
  
## <a name="import-aliases"></a><span data-ttu-id="fdebd-131">Alias de importación</span><span class="sxs-lookup"><span data-stu-id="fdebd-131">Import Aliases</span></span>  
 <span data-ttu-id="fdebd-132">Un *alias de importación* define el alias de un espacio de nombres o de un tipo.</span><span class="sxs-lookup"><span data-stu-id="fdebd-132">An *import alias* defines the alias for a namespace or type.</span></span> <span data-ttu-id="fdebd-133">Los alias de importación son útiles cuando es necesario usar elementos con el mismo nombre que se declaran en uno o varios espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="fdebd-133">Import aliases are useful when you need to use items with the same name that are declared in one or more namespaces.</span></span> <span data-ttu-id="fdebd-134">Para obtener más información y un ejemplo, vea "calificar un nombre de elemento" en [referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="fdebd-134">For more information and an example, see "Qualifying an Element Name" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="fdebd-135">No debe declarar un miembro en el nivel de módulo con el mismo nombre que `aliasname`.</span><span class="sxs-lookup"><span data-stu-id="fdebd-135">You should not declare a member at module level with the same name as `aliasname`.</span></span> <span data-ttu-id="fdebd-136">Si lo hace, el compilador de Visual Basic utiliza `aliasname` solo para el miembro declarado y ya no lo reconoce como un alias de importación.</span><span class="sxs-lookup"><span data-stu-id="fdebd-136">If you do, the Visual Basic compiler uses `aliasname` only for the declared member and no longer recognizes it as an import alias.</span></span>  
  
 <span data-ttu-id="fdebd-137">Aunque la sintaxis que se usa para declarar un alias de importación es similar a la que se usa para importar un prefijo de espacio de nombres XML, los resultados son diferentes.</span><span class="sxs-lookup"><span data-stu-id="fdebd-137">Although the syntax used for declaring an import alias is like that used for importing an XML namespace prefix, the results are different.</span></span> <span data-ttu-id="fdebd-138">Un alias de importación se puede usar como una expresión en el código, mientras que un prefijo de espacio de nombres XML solo se puede usar en literales XML o propiedades de eje XML como prefijo para un nombre de elemento o atributo calificado.</span><span class="sxs-lookup"><span data-stu-id="fdebd-138">An import alias can be used as an expression in your code, whereas an XML namespace prefix can be used only in XML literals or XML axis properties as the prefix for a qualified element or attribute name.</span></span>  
  
### <a name="element-names"></a><span data-ttu-id="fdebd-139">Nombres de elementos</span><span class="sxs-lookup"><span data-stu-id="fdebd-139">Element Names</span></span>  
 <span data-ttu-id="fdebd-140">Si proporciona `element`, debe representar un *elemento contenedor*, es decir, un elemento de programación que puede contener otros elementos.</span><span class="sxs-lookup"><span data-stu-id="fdebd-140">If you supply `element`, it must represent a *container element*, that is, a programming element that can contain other elements.</span></span> <span data-ttu-id="fdebd-141">Los elementos de contenedor incluyen clases, estructuras, módulos, interfaces y enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="fdebd-141">Container elements include classes, structures, modules, interfaces, and enumerations.</span></span>  
  
 <span data-ttu-id="fdebd-142">El ámbito de los elementos que se ponen a disposición de una instrucción `Imports` depende de si se especifica `element`.</span><span class="sxs-lookup"><span data-stu-id="fdebd-142">The scope of the elements made available by an `Imports` statement depends on whether you specify `element`.</span></span> <span data-ttu-id="fdebd-143">Si solo especifica `namespace`, todos los miembros con el nombre único de ese espacio de nombres y los miembros de los elementos contenedores dentro de ese espacio de nombres están disponibles sin calificación.</span><span class="sxs-lookup"><span data-stu-id="fdebd-143">If you specify only `namespace`, all uniquely named members of that namespace, and members of container elements within that namespace, are available without qualification.</span></span> <span data-ttu-id="fdebd-144">Si especifica `namespace` y `element`, solo estarán disponibles los miembros de ese elemento sin calificación.</span><span class="sxs-lookup"><span data-stu-id="fdebd-144">If you specify both `namespace` and `element`, only the members of that element are available without qualification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fdebd-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fdebd-145">Example</span></span>  
 <span data-ttu-id="fdebd-146">En el ejemplo siguiente se devuelven todas las carpetas de C:\ directorio mediante la clase <xref:System.IO.DirectoryInfo>.</span><span class="sxs-lookup"><span data-stu-id="fdebd-146">The following example returns all the folders in the C:\ directory by using the <xref:System.IO.DirectoryInfo> class.</span></span>  
  
 <span data-ttu-id="fdebd-147">El código no tiene ninguna instrucción `Imports` en la parte superior del archivo.</span><span class="sxs-lookup"><span data-stu-id="fdebd-147">The code has no `Imports` statements at the top of the file.</span></span> <span data-ttu-id="fdebd-148">Por lo tanto, las referencias de `DirectoryInfo`, <xref:System.Text.StringBuilder> y <xref:Microsoft.VisualBasic.ControlChars.CrLf> están completas con los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="fdebd-148">Therefore, the `DirectoryInfo`, <xref:System.Text.StringBuilder>, and <xref:Microsoft.VisualBasic.ControlChars.CrLf> references are all fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#152](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#152)]  
  
## <a name="example"></a><span data-ttu-id="fdebd-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fdebd-149">Example</span></span>  
 <span data-ttu-id="fdebd-150">En el ejemplo siguiente se incluyen instrucciones de `Imports` para los espacios de nombres a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="fdebd-150">The following example includes `Imports` statements for the referenced namespaces.</span></span> <span data-ttu-id="fdebd-151">Por lo tanto, no es necesario que los tipos estén completos con los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="fdebd-151">Therefore, the types do not have to be fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#153](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#153)]  
  
 [!code-vb[VbVbalrStatements#154](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#154)]  
  
## <a name="example"></a><span data-ttu-id="fdebd-152">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fdebd-152">Example</span></span>  
 <span data-ttu-id="fdebd-153">En el ejemplo siguiente se incluyen `Imports` instrucciones que crean alias para los espacios de nombres a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="fdebd-153">The following example includes `Imports` statements that create aliases for the referenced namespaces.</span></span> <span data-ttu-id="fdebd-154">Los tipos se califican con los alias.</span><span class="sxs-lookup"><span data-stu-id="fdebd-154">The types are qualified with the aliases.</span></span>  
  
 [!code-vb[VbVbalrStatements#155](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#155)]  
  
 [!code-vb[VbVbalrStatements#156](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#156)]  
  
## <a name="example"></a><span data-ttu-id="fdebd-155">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fdebd-155">Example</span></span>  
 <span data-ttu-id="fdebd-156">En el ejemplo siguiente se incluyen `Imports` instrucciones que crean alias para los tipos a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="fdebd-156">The following example includes `Imports` statements that create aliases for the referenced types.</span></span> <span data-ttu-id="fdebd-157">Los alias se usan para especificar los tipos.</span><span class="sxs-lookup"><span data-stu-id="fdebd-157">Aliases are used to specify the types.</span></span>  
  
 [!code-vb[VbVbalrStatements#157](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#157)]  
  
 [!code-vb[VbVbalrStatements#158](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#158)]  
  
## <a name="see-also"></a><span data-ttu-id="fdebd-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="fdebd-158">See also</span></span>

- [<span data-ttu-id="fdebd-159">Namespace (instrucción)</span><span class="sxs-lookup"><span data-stu-id="fdebd-159">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="fdebd-160">Espacios de nombres en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fdebd-160">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="fdebd-161">Referencias y la instrucción Imports</span><span class="sxs-lookup"><span data-stu-id="fdebd-161">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="fdebd-162">Imports (instrucción), espacio de nombres XML</span><span class="sxs-lookup"><span data-stu-id="fdebd-162">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [<span data-ttu-id="fdebd-163">Referencias a elementos declarados</span><span class="sxs-lookup"><span data-stu-id="fdebd-163">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)

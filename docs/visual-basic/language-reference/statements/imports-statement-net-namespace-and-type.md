---
description: 'Más información sobre: instrucción Imports (espacio de nombres y tipo de .NET)'
title: 'Instrucción Imports: tipo y espacio de nombres .NET'
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
ms.openlocfilehash: 28b7608e250fdba9c39f0209154d5a3d8f725eea
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768979"
---
# <a name="imports-statement-net-namespace-and-type"></a><span data-ttu-id="6197b-103">Instrucción Imports (Tipo y espacio de nombres de .NET)</span><span class="sxs-lookup"><span data-stu-id="6197b-103">Imports Statement (.NET Namespace and Type)</span></span>

<span data-ttu-id="6197b-104">Permite hacer referencia a los nombres de tipo sin la calificación de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="6197b-104">Enables type names to be referenced without namespace qualification.</span></span>

## <a name="syntax"></a><span data-ttu-id="6197b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6197b-105">Syntax</span></span>

```vb
Imports [ aliasname = ] namespace
' -or-
Imports [ aliasname = ] namespace.element
```

## <a name="parts"></a><span data-ttu-id="6197b-106">Partes</span><span class="sxs-lookup"><span data-stu-id="6197b-106">Parts</span></span>

|<span data-ttu-id="6197b-107">Término</span><span class="sxs-lookup"><span data-stu-id="6197b-107">Term</span></span>|<span data-ttu-id="6197b-108">Definición</span><span class="sxs-lookup"><span data-stu-id="6197b-108">Definition</span></span>|
|---|---|
|`aliasname`|<span data-ttu-id="6197b-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6197b-109">Optional.</span></span> <span data-ttu-id="6197b-110">Un *alias de importación* o nombre con el que el código puede hacer referencia en `namespace` lugar de la cadena de calificación completa.</span><span class="sxs-lookup"><span data-stu-id="6197b-110">An *import alias* or name by which code can refer to `namespace` instead of the full qualification string.</span></span> <span data-ttu-id="6197b-111">Vea [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="6197b-111">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|
|`namespace`|<span data-ttu-id="6197b-112">Necesario.</span><span class="sxs-lookup"><span data-stu-id="6197b-112">Required.</span></span> <span data-ttu-id="6197b-113">Nombre completo del espacio de nombres que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="6197b-113">The fully qualified name of the namespace being imported.</span></span> <span data-ttu-id="6197b-114">Puede ser una cadena de espacios de nombres anidados en cualquier nivel.</span><span class="sxs-lookup"><span data-stu-id="6197b-114">Can be a string of namespaces nested to any level.</span></span>|
|`element`|<span data-ttu-id="6197b-115">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6197b-115">Optional.</span></span> <span data-ttu-id="6197b-116">Nombre de un elemento de programación declarado en el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="6197b-116">The name of a programming element declared in the namespace.</span></span> <span data-ttu-id="6197b-117">Puede ser cualquier elemento contenedor.</span><span class="sxs-lookup"><span data-stu-id="6197b-117">Can be any container element.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6197b-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6197b-118">Remarks</span></span>

<span data-ttu-id="6197b-119">La `Imports` instrucción permite hacer referencia directamente a los tipos contenidos en un espacio de nombres determinado.</span><span class="sxs-lookup"><span data-stu-id="6197b-119">The `Imports` statement enables types that are contained in a given namespace to be referenced directly.</span></span>

<span data-ttu-id="6197b-120">Puede proporcionar un único nombre de espacio de nombres o una cadena de espacios de nombres anidados.</span><span class="sxs-lookup"><span data-stu-id="6197b-120">You can supply a single namespace name or a string of nested namespaces.</span></span> <span data-ttu-id="6197b-121">Cada espacio de nombres anidado se separa del siguiente espacio de nombres de nivel superior en un punto ( `.` ), como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6197b-121">Each nested namespace is separated from the next higher level namespace by a period (`.`), as the following example illustrates:</span></span>

```vb
Imports System.Collections.Generic
```

<span data-ttu-id="6197b-122">Cada archivo de código fuente puede contener cualquier número de `Imports` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="6197b-122">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="6197b-123">Estos deben seguir cualquier declaración de opción, como la `Option Strict` instrucción, y deben preceder a cualquier declaración de elemento de programación, como `Module` `Class` instrucciones o.</span><span class="sxs-lookup"><span data-stu-id="6197b-123">These must follow any option declarations, such as the `Option Strict` statement, and they must precede any programming element declarations, such as `Module` or `Class` statements.</span></span>

<span data-ttu-id="6197b-124">Solo se puede usar `Imports` en el nivel de archivo.</span><span class="sxs-lookup"><span data-stu-id="6197b-124">You can use `Imports` only at file level.</span></span> <span data-ttu-id="6197b-125">Esto significa que el contexto de la declaración para la importación debe ser un archivo de código fuente y no puede ser un espacio de nombres, una clase, una estructura, un módulo, una interfaz, un procedimiento o un bloque.</span><span class="sxs-lookup"><span data-stu-id="6197b-125">This means the declaration context for importation must be a source file, and cannot be a namespace, class, structure, module, interface, procedure, or block.</span></span>

<span data-ttu-id="6197b-126">Tenga en cuenta que la instrucción no hace que los `Imports` elementos de otros proyectos y ensamblados estén disponibles para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="6197b-126">Note that the `Imports` statement does not make elements from other projects and assemblies available to your project.</span></span> <span data-ttu-id="6197b-127">La importación no se ocupa del establecimiento de una referencia.</span><span class="sxs-lookup"><span data-stu-id="6197b-127">Importing does not take the place of setting a reference.</span></span> <span data-ttu-id="6197b-128">Solo elimina la necesidad de calificar nombres que ya están disponibles para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="6197b-128">It only removes the need to qualify names that are already available to your project.</span></span> <span data-ttu-id="6197b-129">Para obtener más información, vea "importar elementos contenedores" en [referencias a elementos declarados](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="6197b-129">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6197b-130">Puede definir instrucciones implícitas mediante `Imports` la [Página referencias, el diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="6197b-130">You can define implicit `Imports` statements by using the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span> <span data-ttu-id="6197b-131">Para obtener más información, consulte [Cómo: agregar o quitar espacios de nombres importados (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="6197b-131">For more information, see [How to: Add or Remove Imported Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span></span>

## <a name="import-aliases"></a><span data-ttu-id="6197b-132">Alias de importación</span><span class="sxs-lookup"><span data-stu-id="6197b-132">Import Aliases</span></span>

<span data-ttu-id="6197b-133">Un *alias de importación* define el alias de un espacio de nombres o de un tipo.</span><span class="sxs-lookup"><span data-stu-id="6197b-133">An *import alias* defines the alias for a namespace or type.</span></span> <span data-ttu-id="6197b-134">Los alias de importación son útiles cuando es necesario usar elementos con el mismo nombre que se declaran en uno o varios espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="6197b-134">Import aliases are useful when you need to use items with the same name that are declared in one or more namespaces.</span></span> <span data-ttu-id="6197b-135">Para obtener más información y un ejemplo, vea "calificar un nombre de elemento" en [referencias a elementos declarados](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="6197b-135">For more information and an example, see "Qualifying an Element Name" in [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>

<span data-ttu-id="6197b-136">No debe declarar un miembro en el nivel de módulo con el mismo nombre que `aliasname` .</span><span class="sxs-lookup"><span data-stu-id="6197b-136">You should not declare a member at module level with the same name as `aliasname`.</span></span> <span data-ttu-id="6197b-137">Si lo hace, el compilador de Visual Basic `aliasname` solo utiliza para el miembro declarado y ya no lo reconoce como un alias de importación.</span><span class="sxs-lookup"><span data-stu-id="6197b-137">If you do, the Visual Basic compiler uses `aliasname` only for the declared member and no longer recognizes it as an import alias.</span></span>

<span data-ttu-id="6197b-138">Aunque la sintaxis que se usa para declarar un alias de importación es similar a la que se usa para importar un prefijo de espacio de nombres XML, los resultados son diferentes.</span><span class="sxs-lookup"><span data-stu-id="6197b-138">Although the syntax used for declaring an import alias is like that used for importing an XML namespace prefix, the results are different.</span></span> <span data-ttu-id="6197b-139">Un alias de importación se puede usar como una expresión en el código, mientras que un prefijo de espacio de nombres XML solo se puede usar en literales XML o propiedades de eje XML como prefijo para un nombre de elemento o atributo calificado.</span><span class="sxs-lookup"><span data-stu-id="6197b-139">An import alias can be used as an expression in your code, whereas an XML namespace prefix can be used only in XML literals or XML axis properties as the prefix for a qualified element or attribute name.</span></span>

### <a name="element-names"></a><span data-ttu-id="6197b-140">Nombres de elementos</span><span class="sxs-lookup"><span data-stu-id="6197b-140">Element Names</span></span>

<span data-ttu-id="6197b-141">Si proporciona `element` , debe representar un *elemento contenedor*, es decir, un elemento de programación que puede contener otros elementos.</span><span class="sxs-lookup"><span data-stu-id="6197b-141">If you supply `element`, it must represent a *container element*, that is, a programming element that can contain other elements.</span></span> <span data-ttu-id="6197b-142">Los elementos de contenedor incluyen clases, estructuras, módulos, interfaces y enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="6197b-142">Container elements include classes, structures, modules, interfaces, and enumerations.</span></span>

<span data-ttu-id="6197b-143">El ámbito de los elementos que se ponen a disposición de una `Imports` instrucción depende de si se especifica `element` .</span><span class="sxs-lookup"><span data-stu-id="6197b-143">The scope of the elements made available by an `Imports` statement depends on whether you specify `element`.</span></span> <span data-ttu-id="6197b-144">Si solo especifica `namespace` , todos los miembros con el nombre único de ese espacio de nombres y los miembros de los elementos contenedores dentro de ese espacio de nombres están disponibles sin calificación.</span><span class="sxs-lookup"><span data-stu-id="6197b-144">If you specify only `namespace`, all uniquely named members of that namespace, and members of container elements within that namespace, are available without qualification.</span></span> <span data-ttu-id="6197b-145">Si especifica `namespace` y `element` , solo estarán disponibles los miembros de ese elemento sin calificación.</span><span class="sxs-lookup"><span data-stu-id="6197b-145">If you specify both `namespace` and `element`, only the members of that element are available without qualification.</span></span>

## <a name="example"></a><span data-ttu-id="6197b-146">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6197b-146">Example</span></span>

<span data-ttu-id="6197b-147">En el ejemplo siguiente se devuelven todas las carpetas del directorio *C: \\* mediante la <xref:System.IO.DirectoryInfo> clase:</span><span class="sxs-lookup"><span data-stu-id="6197b-147">The following example returns all the folders in the *C:\\* directory by using the <xref:System.IO.DirectoryInfo> class:</span></span>

<span data-ttu-id="6197b-148">El código no tiene ninguna `Imports` instrucción en la parte superior del archivo.</span><span class="sxs-lookup"><span data-stu-id="6197b-148">The code has no `Imports` statements at the top of the file.</span></span> <span data-ttu-id="6197b-149">Por lo tanto, las <xref:System.IO.DirectoryInfo> <xref:System.Text.StringBuilder> referencias, y <xref:Microsoft.VisualBasic.ControlChars.CrLf> se califican totalmente con los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="6197b-149">Therefore, the <xref:System.IO.DirectoryInfo>, <xref:System.Text.StringBuilder>, and <xref:Microsoft.VisualBasic.ControlChars.CrLf> references are all fully qualified with the namespaces.</span></span>

[!code-vb[VbVbalrStatements#152](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#152)]

## <a name="example"></a><span data-ttu-id="6197b-150">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6197b-150">Example</span></span>

<span data-ttu-id="6197b-151">En el ejemplo siguiente `Imports` se incluyen instrucciones para los espacios de nombres a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="6197b-151">The following example includes `Imports` statements for the referenced namespaces.</span></span> <span data-ttu-id="6197b-152">Por lo tanto, no es necesario que los tipos estén completos con los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="6197b-152">Therefore, the types do not have to be fully qualified with the namespaces.</span></span>

[!code-vb[VbVbalrStatements#153](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#153)]

[!code-vb[VbVbalrStatements#154](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#154)]
  
## <a name="example"></a><span data-ttu-id="6197b-153">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6197b-153">Example</span></span>

<span data-ttu-id="6197b-154">En el ejemplo siguiente `Imports` se incluyen instrucciones que crean alias para los espacios de nombres a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="6197b-154">The following example includes `Imports` statements that create aliases for the referenced namespaces.</span></span> <span data-ttu-id="6197b-155">Los tipos se califican con los alias.</span><span class="sxs-lookup"><span data-stu-id="6197b-155">The types are qualified with the aliases.</span></span>

[!code-vb[VbVbalrStatements#155](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#155)]

[!code-vb[VbVbalrStatements#156](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#156)]

## <a name="example"></a><span data-ttu-id="6197b-156">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6197b-156">Example</span></span>

<span data-ttu-id="6197b-157">En el ejemplo siguiente `Imports` se incluyen instrucciones que crean alias para los tipos a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="6197b-157">The following example includes `Imports` statements that create aliases for the referenced types.</span></span> <span data-ttu-id="6197b-158">Los alias se usan para especificar los tipos.</span><span class="sxs-lookup"><span data-stu-id="6197b-158">Aliases are used to specify the types.</span></span>

[!code-vb[VbVbalrStatements#157](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#157)]

[!code-vb[VbVbalrStatements#158](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#158)]
  
## <a name="see-also"></a><span data-ttu-id="6197b-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="6197b-159">See also</span></span>

- [<span data-ttu-id="6197b-160">Namespace (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="6197b-160">Namespace Statement</span></span>](namespace-statement.md)
- [<span data-ttu-id="6197b-161">Espacios de nombres en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6197b-161">Namespaces in Visual Basic</span></span>](../../programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="6197b-162">Referencias y la instrucción Imports</span><span class="sxs-lookup"><span data-stu-id="6197b-162">References and the Imports Statement</span></span>](../../programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="6197b-163">Imports (Instrucción, Espacio de nombres XML)</span><span class="sxs-lookup"><span data-stu-id="6197b-163">Imports Statement (XML Namespace)</span></span>](imports-statement-xml-namespace.md)
- [<span data-ttu-id="6197b-164">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="6197b-164">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)

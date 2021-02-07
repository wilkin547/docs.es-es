---
description: 'Más información acerca de: lista de atributos (Visual Basic)'
title: Lista de atributos
ms.date: 07/20/2015
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
ms.openlocfilehash: bde9387a48001a2696a6f69454edc311e7597bb6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99674043"
---
# <a name="attribute-list-visual-basic"></a><span data-ttu-id="24756-103">Lista de atributos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="24756-103">Attribute List (Visual Basic)</span></span>

<span data-ttu-id="24756-104">Especifica los atributos que se van a aplicar a un elemento de programación declarado.</span><span class="sxs-lookup"><span data-stu-id="24756-104">Specifies the attributes to be applied to a declared programming element.</span></span> <span data-ttu-id="24756-105">Los diversos atributos se separan con comas.</span><span class="sxs-lookup"><span data-stu-id="24756-105">Multiple attributes are separated by commas.</span></span> <span data-ttu-id="24756-106">A continuación se encuentra la sintaxis de un atributo.</span><span class="sxs-lookup"><span data-stu-id="24756-106">Following is the syntax for one attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24756-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="24756-107">Syntax</span></span>  
  
```vb  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="24756-108">Partes</span><span class="sxs-lookup"><span data-stu-id="24756-108">Parts</span></span>  

|||
|---|---|
|`attributemodifier`|<span data-ttu-id="24756-109">Se requiere para los atributos aplicados al principio de un archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="24756-109">Required for attributes applied at the beginning of a source file.</span></span> <span data-ttu-id="24756-110">Puede ser un [ensamblado](../modifiers/assembly.md) o un [módulo](../modifiers/module-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="24756-110">Can be [Assembly](../modifiers/assembly.md) or [Module](../modifiers/module-keyword.md).</span></span>|
|`attributename`| <span data-ttu-id="24756-111">Necesario.</span><span class="sxs-lookup"><span data-stu-id="24756-111">Required.</span></span> <span data-ttu-id="24756-112">Nombre del atributo.</span><span class="sxs-lookup"><span data-stu-id="24756-112">Name of the attribute.</span></span>|
|`attributearguments`|<span data-ttu-id="24756-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="24756-113">Optional.</span></span> <span data-ttu-id="24756-114">Lista de argumentos posicionales para este atributo.</span><span class="sxs-lookup"><span data-stu-id="24756-114">List of positional arguments for this attribute.</span></span> <span data-ttu-id="24756-115">Los argumentos múltiples se separan mediante comas.</span><span class="sxs-lookup"><span data-stu-id="24756-115">Multiple arguments are separated by commas.</span></span>|
|`attributeinitializer`|<span data-ttu-id="24756-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="24756-116">Optional.</span></span> <span data-ttu-id="24756-117">Lista de inicializadores de variable o propiedad para este atributo.</span><span class="sxs-lookup"><span data-stu-id="24756-117">List of variable or property initializers for this attribute.</span></span> <span data-ttu-id="24756-118">Los inicializadores múltiples se separan mediante comas.</span><span class="sxs-lookup"><span data-stu-id="24756-118">Multiple initializers are separated by commas.</span></span>|
  
## <a name="remarks"></a><span data-ttu-id="24756-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="24756-119">Remarks</span></span>  

 <span data-ttu-id="24756-120">Puede aplicar uno o varios atributos a casi cualquier elemento de programación (tipos, procedimientos, propiedades, etc.).</span><span class="sxs-lookup"><span data-stu-id="24756-120">You can apply one or more attributes to nearly any programming element (types, procedures, properties, and so forth).</span></span> <span data-ttu-id="24756-121">Los atributos aparecen en los metadatos del ensamblado y pueden ayudarle a anotar el código o especificar cómo usar un elemento de programación determinado.</span><span class="sxs-lookup"><span data-stu-id="24756-121">Attributes appear in your assembly's metadata, and they can help you annotate your code or specify how to use a particular programming element.</span></span> <span data-ttu-id="24756-122">Puede aplicar atributos definidos por Visual Basic y el .NET Framework, y puede definir sus propios atributos.</span><span class="sxs-lookup"><span data-stu-id="24756-122">You can apply attributes defined by Visual Basic and the .NET Framework, and you can define your own attributes.</span></span>  

 <span data-ttu-id="24756-123">Para obtener más información sobre Cuándo usar atributos, vea [información general sobre los atributos](../../programming-guide/concepts/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="24756-123">For more information on when to use attributes, see [Attributes overview](../../programming-guide/concepts/attributes/index.md).</span></span> <span data-ttu-id="24756-124">Para obtener información sobre los nombres de atributo, vea [nombres de elementos declarados](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="24756-124">For information on attribute names, see [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="24756-125">Reglas</span><span class="sxs-lookup"><span data-stu-id="24756-125">Rules</span></span>  
  
- <span data-ttu-id="24756-126">**Ubicación.**</span><span class="sxs-lookup"><span data-stu-id="24756-126">**Placement.**</span></span> <span data-ttu-id="24756-127">Puede aplicar atributos a la mayoría de los elementos de programación declarados.</span><span class="sxs-lookup"><span data-stu-id="24756-127">You can apply attributes to most declared programming elements.</span></span> <span data-ttu-id="24756-128">Para aplicar uno o varios atributos, coloque un *bloque de atributos* al principio de la declaración del elemento.</span><span class="sxs-lookup"><span data-stu-id="24756-128">To apply one or more attributes, you place an *attribute block* at the beginning of the element declaration.</span></span> <span data-ttu-id="24756-129">Cada entrada de la lista de atributos especifica un atributo que se desea aplicar y el modificador y los argumentos que se usan para esta invocación del atributo.</span><span class="sxs-lookup"><span data-stu-id="24756-129">Each entry in the attribute list specifies an attribute you wish to apply, and the modifier and arguments you are using for this invocation of the attribute.</span></span>  
  
- <span data-ttu-id="24756-130">**Corchetes angulares.**</span><span class="sxs-lookup"><span data-stu-id="24756-130">**Angle Brackets.**</span></span> <span data-ttu-id="24756-131">Si proporciona una lista de atributos, debe encerrarla entre corchetes angulares (" `<` " y " `>` ").</span><span class="sxs-lookup"><span data-stu-id="24756-131">If you supply an attribute list, you must enclose it in angle brackets ("`<`" and "`>`").</span></span>  
  
- <span data-ttu-id="24756-132">**Parte de la declaración.**</span><span class="sxs-lookup"><span data-stu-id="24756-132">**Part of the Declaration.**</span></span> <span data-ttu-id="24756-133">El atributo debe formar parte de la declaración del elemento, no de una instrucción independiente.</span><span class="sxs-lookup"><span data-stu-id="24756-133">The attribute must be part of the element declaration, not a separate statement.</span></span> <span data-ttu-id="24756-134">Puede usar la secuencia de continuación de línea (" `_` ") para extender la instrucción de declaración en varias líneas de código fuente.</span><span class="sxs-lookup"><span data-stu-id="24756-134">You can use the line-continuation sequence (" `_`") to extend the declaration statement onto multiple source-code lines.</span></span>  
  
- <span data-ttu-id="24756-135">**Modificadores.**</span><span class="sxs-lookup"><span data-stu-id="24756-135">**Modifiers.**</span></span> <span data-ttu-id="24756-136">Se requiere un modificador `Assembly` de atributo (o `Module` ) en cada atributo aplicado a un elemento de programación al principio de un archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="24756-136">An attribute modifier (`Assembly` or `Module`) is required on every attribute applied to a programming element at the beginning of a source file.</span></span> <span data-ttu-id="24756-137">No se permiten modificadores de atributo en los atributos aplicados a los elementos que no están al principio de un archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="24756-137">Attribute modifiers are not allowed on attributes applied to elements that are not at the beginning of a source file.</span></span>  
  
- <span data-ttu-id="24756-138">**Argumentos.**</span><span class="sxs-lookup"><span data-stu-id="24756-138">**Arguments.**</span></span> <span data-ttu-id="24756-139">Todos los argumentos posicionales de un atributo deben preceder a cualquier inicializador de variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="24756-139">All positional arguments for an attribute must precede any variable or property initializers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24756-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="24756-140">Example</span></span>  

 <span data-ttu-id="24756-141">En el ejemplo siguiente se aplica el <xref:System.Runtime.InteropServices.DllImportAttribute> atributo a una definición de esquema de un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="24756-141">The following example applies the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute to a skeleton definition of a `Function` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#1)]  
  
 <span data-ttu-id="24756-142"><xref:System.Runtime.InteropServices.DllImportAttribute> indica que el procedimiento con atributos representa un punto de entrada de una biblioteca de vínculos dinámicos (DLL) no administrada.</span><span class="sxs-lookup"><span data-stu-id="24756-142"><xref:System.Runtime.InteropServices.DllImportAttribute> indicates that the attributed procedure represents an entry point in an unmanaged dynamic-link library (DLL).</span></span> <span data-ttu-id="24756-143">El atributo proporciona el nombre del archivo DLL como argumento posicional y la otra información como inicializadores de variables.</span><span class="sxs-lookup"><span data-stu-id="24756-143">The attribute supplies the DLL name as a positional argument and the other information as variable initializers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24756-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="24756-144">See also</span></span>

- [<span data-ttu-id="24756-145">Ensamblaje</span><span class="sxs-lookup"><span data-stu-id="24756-145">Assembly</span></span>](../modifiers/assembly.md)
- [<span data-ttu-id="24756-146">Destina \<keyword></span><span class="sxs-lookup"><span data-stu-id="24756-146">Module \<keyword></span></span>](../modifiers/module-keyword.md)
- [<span data-ttu-id="24756-147">Información general de atributos</span><span class="sxs-lookup"><span data-stu-id="24756-147">Attributes overview</span></span>](../../programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="24756-148">Procedimiento Interrupción y combinación de instrucciones en código</span><span class="sxs-lookup"><span data-stu-id="24756-148">How to: Break and Combine Statements in Code</span></span>](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)

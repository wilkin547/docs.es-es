---
title: Nombres de elementos declarados (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic], case sensitivity
- names [Visual Basic], Visual Basic rules
- naming conventions [Visual Basic]
- element names [Visual Basic]
- declared elements [Visual Basic], identifiers
- declarations [Visual Basic], elements
- declared elements [Visual Basic], valid names
- '[] escape characters [Visual Basic]'
- names [Visual Basic], elements
- declaration statements [Visual Basic], declared elements
- declaring elements [Visual Basic]
- identifiers [Visual Basic], declared elements
- case sensitivity, declared element names
- escape characters [Visual Basic]
- names [Visual Basic], declared elements
- declared elements [Visual Basic], about declared elements
- escaped names [Visual Basic]
- declared elements [Visual Basic], names
- names [Visual Basic], naming conventions
- identifiers [Visual Basic], elements
ms.assetid: 09d8843b-c0dc-4afe-9dab-87c439a69e66
ms.openlocfilehash: 5b1f8ccc402f7f5928a33f434664b0f28d108e6d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58814073"
---
# <a name="declared-element-names-visual-basic"></a><span data-ttu-id="6f5f7-102">Nombres de elementos declarados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f5f7-102">Declared Element Names (Visual Basic)</span></span>
<span data-ttu-id="6f5f7-103">Cada elemento declarado tiene un nombre, también denominado una *identificador*, que es lo que el código que se usa para hacer referencia a él.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-103">Every declared element has a name, also called an *identifier*, which is what the code uses to refer to it.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="6f5f7-104">Reglas</span><span class="sxs-lookup"><span data-stu-id="6f5f7-104">Rules</span></span>  
 <span data-ttu-id="6f5f7-105">El nombre de un elemento en Visual Basic debe observar las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="6f5f7-105">An element name in Visual Basic must observe the following rules:</span></span>  
  
-   <span data-ttu-id="6f5f7-106">Debe comenzar con un carácter alfabético o un carácter de subrayado (`_`).</span><span class="sxs-lookup"><span data-stu-id="6f5f7-106">It must begin with an alphabetic character or an underscore (`_`).</span></span>  
  
-   <span data-ttu-id="6f5f7-107">Solo debe contener caracteres alfabéticos, dígitos decimales y caracteres de subrayado.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-107">It must only contain alphabetic characters, decimal digits, and underscores.</span></span>  
  
-   <span data-ttu-id="6f5f7-108">Debe contener al menos un carácter alfabético o dígito decimal si empieza con un carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-108">It must contain at least one alphabetic character or decimal digit if it begins with an underscore.</span></span>  
  
-   <span data-ttu-id="6f5f7-109">No debe superar los 1023 caracteres.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-109">It must not be more than 1023 characters long.</span></span>  
  
 <span data-ttu-id="6f5f7-110">La longitud máxima de 1023 caracteres también se aplica a toda la cadena de un nombre completo, como `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-110">The length limit of 1023 characters also applies to the entire string of a fully qualified name, such as `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.</span></span>  
  
 <span data-ttu-id="6f5f7-111">El ejemplo siguiente muestra algunos nombres de elemento válido.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-111">The following example shows some valid element names.</span></span>  
  
 `aB123__45`  
  
 `_567`  
  
 <span data-ttu-id="6f5f7-112">El ejemplo siguiente muestra algunos nombres de elemento no válido.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-112">The following example shows some invalid element names.</span></span> <span data-ttu-id="6f5f7-113">El primero contiene sólo un carácter de subrayado, la segunda comienza con un dígito decimal y el tercero contiene un carácter no válido ($).</span><span class="sxs-lookup"><span data-stu-id="6f5f7-113">The first contains only an underscore, the second begins with a decimal digit, and the third contains an invalid character ($).</span></span>  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
>  <span data-ttu-id="6f5f7-114">Los nombres de elemento a partir de un carácter de subrayado (`_`) no forman parte de la [independencia del lenguaje y componentes independientes del lenguaje](../../../../standard/language-independence-and-language-independent-components.md) (CLS), por lo que el código conforme a CLS no puede utilizar un componente que define los nombres de este tipo.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-114">Element names starting with an underscore (`_`) are not part of the [Language Independence and Language-Independent Components](../../../../standard/language-independence-and-language-independent-components.md) (CLS), so CLS-compliant code cannot use a component that defines such names.</span></span> <span data-ttu-id="6f5f7-115">Sin embargo, un carácter de subrayado en cualquier otra posición de un nombre de elemento es conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-115">However, an underscore in any other position in an element name is CLS-compliant.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="6f5f7-116">Directrices de longitud de nombre</span><span class="sxs-lookup"><span data-stu-id="6f5f7-116">Name Length Guidelines</span></span>  
 <span data-ttu-id="6f5f7-117">A efectos prácticos, su nombre debe ser lo más corta posible al identificar claramente la naturaleza del elemento.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-117">As a practical matter, your name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="6f5f7-118">Esto mejora la legibilidad del código y reduce el tamaño de archivo de origen y de longitud de línea.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-118">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="6f5f7-119">Por otro lado, el nombre no debe ser tan corto que no adecuadamente describe lo que representa el elemento y cómo lo utiliza el código.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-119">On the other hand, your name should not be so short that it does not adequately describe what the element represents and how your code uses it.</span></span> <span data-ttu-id="6f5f7-120">Esto es importante para la legibilidad del código.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-120">This is important for the readability of your code.</span></span> <span data-ttu-id="6f5f7-121">Si alguien más está intentando entenderla, o si usted está examinando mucho tiempo después de que lo escribió, nombres de elementos adecuados pueden guardar una cantidad considerable de tiempo.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-121">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, suitable element names can save a considerable amount of time.</span></span>  
  
## <a name="escaped-names"></a><span data-ttu-id="6f5f7-122">Nombres de escape</span><span class="sxs-lookup"><span data-stu-id="6f5f7-122">Escaped Names</span></span>  
 <span data-ttu-id="6f5f7-123">Por lo general, un nombre de elemento no debe coincidir con cualquiera de las palabras clave reservadas, como Visual Basic, `Case` o `Friend`.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-123">Generally, an element name must not match any of the keywords reserved by Visual Basic, such as `Case` or `Friend`.</span></span> <span data-ttu-id="6f5f7-124">Sin embargo, puede definir un *nombre con escape*, que se encierra entre corchetes (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="6f5f7-124">However, you can define an *escaped name*, which is enclosed by brackets (`[ ]`).</span></span> <span data-ttu-id="6f5f7-125">Un nombre con escape puede coincidir con cualquier palabra clave de Visual Basic, puesto que los corchetes quitar cualquier ambigüedad.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-125">An escaped name can match any Visual Basic keyword, since the brackets remove any ambiguity.</span></span> <span data-ttu-id="6f5f7-126">También utiliza los corchetes cuando se hace referencia al nombre más adelante en el código.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-126">You also use the brackets when you refer to the name later in your code.</span></span>  
  
 <span data-ttu-id="6f5f7-127">En general, debe usar nombres de escape solo cuando:</span><span class="sxs-lookup"><span data-stu-id="6f5f7-127">In general, you should use escaped names only when:</span></span>  
  
-   <span data-ttu-id="6f5f7-128">El código se migrado desde una versión anterior de Visual Basic que no reservó la palabra clave que se va a usar como un nombre; o</span><span class="sxs-lookup"><span data-stu-id="6f5f7-128">Your code has migrated from a previous version of Visual Basic that did not reserve the keyword being used as a name; or</span></span>  
  
-   <span data-ttu-id="6f5f7-129">Trabaja con código escrito en otro idioma en el que no se reserva la palabra clave dada.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-129">You are working with code written in another language in which the given keyword is not reserved.</span></span>  
  
 <span data-ttu-id="6f5f7-130">De lo contrario, considere cambiar el nombre del elemento si su nombre entra en conflicto con una palabra clave.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-130">Otherwise, you should consider renaming the element if its name conflicts with a keyword.</span></span> <span data-ttu-id="6f5f7-131">El entorno de desarrollo integrado (IDE) proporciona una manera fácil de hacerlo.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-131">The integrated development environment (IDE) provides an easy way to do this.</span></span> <span data-ttu-id="6f5f7-132">Para obtener más información, consulte [refactorización](/visualstudio/vb-ide/refactoring-vb).</span><span class="sxs-lookup"><span data-stu-id="6f5f7-132">For more information, see [Refactoring](/visualstudio/vb-ide/refactoring-vb).</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="6f5f7-133">Mayúsculas y minúsculas en nombres</span><span class="sxs-lookup"><span data-stu-id="6f5f7-133">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="6f5f7-134">Los nombres de elemento en Visual Basic distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-134">Element names in Visual Basic are case-insensitive.</span></span> <span data-ttu-id="6f5f7-135">Esto significa que cuando el compilador compara dos nombres que difieran en mayúsculas o minúsculas, interpreta como el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-135">This means that when the compiler compares two names that differ in alphabetic case only, it interprets them as the same name.</span></span> <span data-ttu-id="6f5f7-136">Por ejemplo, considera que `ABC` y `abc` hacen referencia al mismo elemento declarado.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-136">For example, it considers `ABC` and `abc` to refer to the same declared element.</span></span>  
  
 <span data-ttu-id="6f5f7-137">Sin embargo, common language runtime (CLR) usa el enlace entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-137">However, the common language runtime (CLR) uses case-sensitive binding.</span></span> <span data-ttu-id="6f5f7-138">Por lo tanto, cuando genere un ensamblado o una DLL que pueda estar disponible para otros ensamblados, sus nombres ya no distinguirán entre mayúsculas o minúsculas.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-138">Therefore, when you produce an assembly or a DLL and make it available to other assemblies, your names are no longer case-insensitive.</span></span> <span data-ttu-id="6f5f7-139">Por ejemplo, si define una clase que tiene un elemento denominado `ABC`, y otros ensamblados usan la clase mediante Common Language Runtime, deberán hacer referencia al elemento como `ABC`.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-139">For example, if you define a class with an element called `ABC`, and other assemblies make use of your class through the common language runtime, they must refer to the element as `ABC`.</span></span> <span data-ttu-id="6f5f7-140">Si posteriormente vuelve a compilar la clase y cambiar el nombre del elemento a `abc`, los demás ensamblados mediante la clase ya no pudieran acceder a ese elemento.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-140">If you subsequently recompile your class and change the element's name to `abc`, the other assemblies using your class could no longer access that element.</span></span> <span data-ttu-id="6f5f7-141">Por lo tanto, cuando se lance una versión actualizada de un ensamblado, no se deben cambiar las mayúsculas o minúsculas de los elementos públicos.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-141">Therefore, when you release an updated version of an assembly, you should not change the alphabetic case of any public elements.</span></span>  
  
## <a name="names-and-locales"></a><span data-ttu-id="6f5f7-142">Los nombres y las configuraciones regionales</span><span class="sxs-lookup"><span data-stu-id="6f5f7-142">Names and Locales</span></span>  
 <span data-ttu-id="6f5f7-143">Comparación de nombres es independiente de la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-143">Comparison of names is independent of locale.</span></span> <span data-ttu-id="6f5f7-144">Si dos nombres coinciden en una configuración regional, se garantiza que deben coincidir en todas las configuraciones regionales.</span><span class="sxs-lookup"><span data-stu-id="6f5f7-144">If two names match in one locale, they are guaranteed to match in all locales.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f5f7-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f5f7-145">See also</span></span>

- [<span data-ttu-id="6f5f7-146">Elementos declarados</span><span class="sxs-lookup"><span data-stu-id="6f5f7-146">Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)
- [<span data-ttu-id="6f5f7-147">Características de los elementos declarados</span><span class="sxs-lookup"><span data-stu-id="6f5f7-147">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="6f5f7-148">Referencias a elementos declarados</span><span class="sxs-lookup"><span data-stu-id="6f5f7-148">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="6f5f7-149">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="6f5f7-149">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)

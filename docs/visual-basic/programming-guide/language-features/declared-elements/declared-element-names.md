---
title: Nombres de elementos declarados (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 59fee9eb79af86df7f01bd77c27a929ef61fcfe2
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2017
---
# <a name="declared-element-names-visual-basic"></a><span data-ttu-id="a2a01-102">Nombres de elementos declarados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2a01-102">Declared Element Names (Visual Basic)</span></span>
<span data-ttu-id="a2a01-103">Cada elemento declarado tiene un nombre, también denominado una *identificador*, que es lo que el código que se usa para hacer referencia a él.</span><span class="sxs-lookup"><span data-stu-id="a2a01-103">Every declared element has a name, also called an *identifier*, which is what the code uses to refer to it.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="a2a01-104">Reglas</span><span class="sxs-lookup"><span data-stu-id="a2a01-104">Rules</span></span>  
 <span data-ttu-id="a2a01-105">Un nombre de elemento en [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] debe cumplir las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="a2a01-105">An element name in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] must observe the following rules:</span></span>  
  
-   <span data-ttu-id="a2a01-106">Debe comenzar con un carácter alfabético o un carácter de subrayado (`_`).</span><span class="sxs-lookup"><span data-stu-id="a2a01-106">It must begin with an alphabetic character or an underscore (`_`).</span></span>  
  
-   <span data-ttu-id="a2a01-107">Solo debe contener caracteres alfabéticos, dígitos decimales y caracteres de subrayado.</span><span class="sxs-lookup"><span data-stu-id="a2a01-107">It must only contain alphabetic characters, decimal digits, and underscores.</span></span>  
  
-   <span data-ttu-id="a2a01-108">Debe contener al menos un carácter alfabético o dígito decimal si empieza con un carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="a2a01-108">It must contain at least one alphabetic character or decimal digit if it begins with an underscore.</span></span>  
  
-   <span data-ttu-id="a2a01-109">No debe ser más de 1023 caracteres.</span><span class="sxs-lookup"><span data-stu-id="a2a01-109">It must not be more than 1023 characters long.</span></span>  
  
 <span data-ttu-id="a2a01-110">El límite de longitud de 1023 caracteres también se aplica a toda la cadena de un nombre completo, como `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.</span><span class="sxs-lookup"><span data-stu-id="a2a01-110">The length limit of 1023 characters also applies to the entire string of a fully qualified name, such as `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.</span></span>  
  
 <span data-ttu-id="a2a01-111">El ejemplo siguiente muestra algunos nombres de elemento válido.</span><span class="sxs-lookup"><span data-stu-id="a2a01-111">The following example shows some valid element names.</span></span>  
  
 `aB123__45`  
  
 `_567`  
  
 <span data-ttu-id="a2a01-112">El ejemplo siguiente muestra algunos nombres de elemento no válido.</span><span class="sxs-lookup"><span data-stu-id="a2a01-112">The following example shows some invalid element names.</span></span> <span data-ttu-id="a2a01-113">La primera fila contiene sólo un carácter de subrayado, el segundo comienza con un dígito decimal y el tercero contiene un carácter no válido ($).</span><span class="sxs-lookup"><span data-stu-id="a2a01-113">The first contains only an underscore, the second begins with a decimal digit, and the third contains an invalid character ($).</span></span>  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
>  <span data-ttu-id="a2a01-114">Nombres de elemento a partir de un carácter de subrayado (`_`) no forman parte de la [independencia del lenguaje y componentes independientes del lenguaje](../../../../../docs/standard/language-independence-and-language-independent-components.md) (CLS), por lo que el código conforme a CLS no puede utilizar un componente que define los nombres de este tipo.</span><span class="sxs-lookup"><span data-stu-id="a2a01-114">Element names starting with an underscore (`_`) are not part of the [Language Independence and Language-Independent Components](../../../../../docs/standard/language-independence-and-language-independent-components.md) (CLS), so CLS-compliant code cannot use a component that defines such names.</span></span> <span data-ttu-id="a2a01-115">Sin embargo, un carácter de subrayado en cualquier otra posición de un nombre de elemento es conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="a2a01-115">However, an underscore in any other position in an element name is CLS-compliant.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="a2a01-116">Instrucciones de longitud de nombre</span><span class="sxs-lookup"><span data-stu-id="a2a01-116">Name Length Guidelines</span></span>  
 <span data-ttu-id="a2a01-117">A efectos prácticos, el nombre debe ser lo más corta posible al identificar claramente la naturaleza del elemento.</span><span class="sxs-lookup"><span data-stu-id="a2a01-117">As a practical matter, your name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="a2a01-118">Esto mejora la legibilidad del código y reduce el tamaño de archivo de origen y de longitud de línea.</span><span class="sxs-lookup"><span data-stu-id="a2a01-118">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="a2a01-119">Por otro lado, su nombre no debe ser tan corto que no adecuadamente describe lo que representa el elemento y cómo lo utiliza el código.</span><span class="sxs-lookup"><span data-stu-id="a2a01-119">On the other hand, your name should not be so short that it does not adequately describe what the element represents and how your code uses it.</span></span> <span data-ttu-id="a2a01-120">Esto es importante para la legibilidad del código.</span><span class="sxs-lookup"><span data-stu-id="a2a01-120">This is important for the readability of your code.</span></span> <span data-ttu-id="a2a01-121">Si alguien está intentando entenderla, o si usted está examinando mucho tiempo después de que lo ha escrito, nombres de elementos adecuados pueden ahorrar una cantidad considerable de tiempo.</span><span class="sxs-lookup"><span data-stu-id="a2a01-121">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, suitable element names can save a considerable amount of time.</span></span>  
  
## <a name="escaped-names"></a><span data-ttu-id="a2a01-122">Nombres de escape</span><span class="sxs-lookup"><span data-stu-id="a2a01-122">Escaped Names</span></span>  
 <span data-ttu-id="a2a01-123">Por lo general, un nombre de elemento no debe coincidir con cualquiera de las palabras clave reservadas por [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], como `Case` o `Friend`.</span><span class="sxs-lookup"><span data-stu-id="a2a01-123">Generally, an element name must not match any of the keywords reserved by [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], such as `Case` or `Friend`.</span></span> <span data-ttu-id="a2a01-124">Sin embargo, puede definir un *nombre con escape*, que está incluido entre corchetes (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="a2a01-124">However, you can define an *escaped name*, which is enclosed by brackets (`[ ]`).</span></span> <span data-ttu-id="a2a01-125">Un nombre con escape puede coincidir con cualquier [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] (palabra clave), puesto que los corchetes eliminan toda ambigüedad posible.</span><span class="sxs-lookup"><span data-stu-id="a2a01-125">An escaped name can match any [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] keyword, since the brackets remove any ambiguity.</span></span> <span data-ttu-id="a2a01-126">Utiliza también los corchetes cuando se hace referencia al nombre más adelante en el código.</span><span class="sxs-lookup"><span data-stu-id="a2a01-126">You also use the brackets when you refer to the name later in your code.</span></span>  
  
 <span data-ttu-id="a2a01-127">En general, debe usar nombres de escape solo cuando:</span><span class="sxs-lookup"><span data-stu-id="a2a01-127">In general, you should use escaped names only when:</span></span>  
  
-   <span data-ttu-id="a2a01-128">El código ha migrado desde una versión anterior de [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] que no reservó la palabra clave que se va a usar como un nombre; o</span><span class="sxs-lookup"><span data-stu-id="a2a01-128">Your code has migrated from a previous version of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] that did not reserve the keyword being used as a name; or</span></span>  
  
-   <span data-ttu-id="a2a01-129">Está trabajando con código escrito en otro idioma en el que no se reserva la palabra clave dada.</span><span class="sxs-lookup"><span data-stu-id="a2a01-129">You are working with code written in another language in which the given keyword is not reserved.</span></span>  
  
 <span data-ttu-id="a2a01-130">De lo contrario, considere cambiar el nombre del elemento si su nombre entra en conflicto con una palabra clave.</span><span class="sxs-lookup"><span data-stu-id="a2a01-130">Otherwise, you should consider renaming the element if its name conflicts with a keyword.</span></span> <span data-ttu-id="a2a01-131">El entorno de desarrollo integrado (IDE) proporciona una manera sencilla de hacerlo.</span><span class="sxs-lookup"><span data-stu-id="a2a01-131">The integrated development environment (IDE) provides an easy way to do this.</span></span> <span data-ttu-id="a2a01-132">Para obtener más información, consulte [refactorización](/visualstudio/vb-ide/refactoring-vb).</span><span class="sxs-lookup"><span data-stu-id="a2a01-132">For more information, see [Refactoring](/visualstudio/vb-ide/refactoring-vb).</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="a2a01-133">Mayúsculas y minúsculas en nombres</span><span class="sxs-lookup"><span data-stu-id="a2a01-133">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="a2a01-134">Los nombres de elemento de [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a2a01-134">Element names in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] are case-insensitive.</span></span> <span data-ttu-id="a2a01-135">Esto significa que cuando el compilador compara dos nombres que difieran en mayúsculas o minúsculas, interpreta como el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="a2a01-135">This means that when the compiler compares two names that differ in alphabetic case only, it interprets them as the same name.</span></span> <span data-ttu-id="a2a01-136">Por ejemplo, considera que `ABC` y `abc` hacen referencia al mismo elemento declarado.</span><span class="sxs-lookup"><span data-stu-id="a2a01-136">For example, it considers `ABC` and `abc` to refer to the same declared element.</span></span>  
  
 <span data-ttu-id="a2a01-137">No obstante, common language runtime (CLR) utiliza enlaces entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a2a01-137">However, the common language runtime (CLR) uses case-sensitive binding.</span></span> <span data-ttu-id="a2a01-138">Por lo tanto, cuando genere un ensamblado o una DLL que pueda estar disponible para otros ensamblados, sus nombres ya no distinguirán entre mayúsculas o minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a2a01-138">Therefore, when you produce an assembly or a DLL and make it available to other assemblies, your names are no longer case-insensitive.</span></span> <span data-ttu-id="a2a01-139">Por ejemplo, si define una clase que tiene un elemento denominado `ABC`, y otros ensamblados usan la clase mediante Common Language Runtime, deberán hacer referencia al elemento como `ABC`.</span><span class="sxs-lookup"><span data-stu-id="a2a01-139">For example, if you define a class with an element called `ABC`, and other assemblies make use of your class through the common language runtime, they must refer to the element as `ABC`.</span></span> <span data-ttu-id="a2a01-140">Si posteriormente vuelve a compilar la clase y cambia el nombre del elemento a `abc`, los otros ensamblados que utilicen la clase ya no pudieran tener acceso a ese elemento.</span><span class="sxs-lookup"><span data-stu-id="a2a01-140">If you subsequently recompile your class and change the element's name to `abc`, the other assemblies using your class could no longer access that element.</span></span> <span data-ttu-id="a2a01-141">Por lo tanto, cuando se lance una versión actualizada de un ensamblado, no se deben cambiar las mayúsculas o minúsculas de los elementos públicos.</span><span class="sxs-lookup"><span data-stu-id="a2a01-141">Therefore, when you release an updated version of an assembly, you should not change the alphabetic case of any public elements.</span></span>  
  
## <a name="names-and-locales"></a><span data-ttu-id="a2a01-142">Nombres y configuraciones regionales</span><span class="sxs-lookup"><span data-stu-id="a2a01-142">Names and Locales</span></span>  
 <span data-ttu-id="a2a01-143">Comparación de nombres es independiente de la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="a2a01-143">Comparison of names is independent of locale.</span></span> <span data-ttu-id="a2a01-144">Si dos nombres coinciden en una configuración regional, se garantiza que coincidan en todas las configuraciones regionales.</span><span class="sxs-lookup"><span data-stu-id="a2a01-144">If two names match in one locale, they are guaranteed to match in all locales.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2a01-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2a01-145">See Also</span></span>  
 [<span data-ttu-id="a2a01-146">Elementos declarados</span><span class="sxs-lookup"><span data-stu-id="a2a01-146">Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)  
 [<span data-ttu-id="a2a01-147">Características de los elementos declarados</span><span class="sxs-lookup"><span data-stu-id="a2a01-147">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [<span data-ttu-id="a2a01-148">Referencias a elementos declarados</span><span class="sxs-lookup"><span data-stu-id="a2a01-148">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="a2a01-149">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="a2a01-149">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)

---
description: 'Más información acerca de: nombres de elementos declarados (Visual Basic)'
title: Declared Element Names
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
ms.openlocfilehash: ba0a6d6b236c0c4e9ce81c37a1cca4e709cc5588
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100425690"
---
# <a name="declared-element-names-visual-basic"></a><span data-ttu-id="35040-103">Nombres de elementos declarados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="35040-103">Declared Element Names (Visual Basic)</span></span>

<span data-ttu-id="35040-104">Cada elemento declarado tiene un nombre, también denominado *identificador*, que es lo que el código utiliza para hacer referencia a él.</span><span class="sxs-lookup"><span data-stu-id="35040-104">Every declared element has a name, also called an *identifier*, which is what the code uses to refer to it.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="35040-105">Reglas</span><span class="sxs-lookup"><span data-stu-id="35040-105">Rules</span></span>  

 <span data-ttu-id="35040-106">Un nombre de elemento en Visual Basic debe respetar las siguientes reglas:</span><span class="sxs-lookup"><span data-stu-id="35040-106">An element name in Visual Basic must observe the following rules:</span></span>  
  
- <span data-ttu-id="35040-107">Debe empezar por un carácter alfabético o un carácter de subrayado ( `_` ).</span><span class="sxs-lookup"><span data-stu-id="35040-107">It must begin with an alphabetic character or an underscore (`_`).</span></span>  
  
- <span data-ttu-id="35040-108">Solo debe contener caracteres alfabéticos, dígitos decimales y caracteres de subrayado.</span><span class="sxs-lookup"><span data-stu-id="35040-108">It must only contain alphabetic characters, decimal digits, and underscores.</span></span>  
  
- <span data-ttu-id="35040-109">Debe contener al menos un carácter alfabético o un dígito decimal si comienza con un carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="35040-109">It must contain at least one alphabetic character or decimal digit if it begins with an underscore.</span></span>  
  
- <span data-ttu-id="35040-110">No debe tener más de 1023 caracteres de longitud.</span><span class="sxs-lookup"><span data-stu-id="35040-110">It must not be more than 1023 characters long.</span></span>  
  
 <span data-ttu-id="35040-111">El límite de longitud de 1023 caracteres también se aplica a toda la cadena de un nombre completo, como `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement` .</span><span class="sxs-lookup"><span data-stu-id="35040-111">The length limit of 1023 characters also applies to the entire string of a fully qualified name, such as `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.</span></span>  
  
 <span data-ttu-id="35040-112">En el ejemplo siguiente se muestran algunos nombres de elemento válidos.</span><span class="sxs-lookup"><span data-stu-id="35040-112">The following example shows some valid element names.</span></span>  
  
 `aB123__45`  
  
 `_567`  
  
 <span data-ttu-id="35040-113">En el ejemplo siguiente se muestran algunos nombres de elementos no válidos.</span><span class="sxs-lookup"><span data-stu-id="35040-113">The following example shows some invalid element names.</span></span> <span data-ttu-id="35040-114">La primera contiene solo un carácter de subrayado, la segunda comienza con un dígito decimal y la tercera contiene un carácter no válido ($).</span><span class="sxs-lookup"><span data-stu-id="35040-114">The first contains only an underscore, the second begins with a decimal digit, and the third contains an invalid character ($).</span></span>  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
> <span data-ttu-id="35040-115">Los nombres de elemento que comienzan por un carácter de subrayado ( `_` ) no forman parte de la [independencia del lenguaje y de los componentes de Language-Independent](../../../../standard/language-independence-and-language-independent-components.md) (CLS), por lo que el código conforme a CLS no puede usar un componente que defina dichos nombres.</span><span class="sxs-lookup"><span data-stu-id="35040-115">Element names starting with an underscore (`_`) are not part of the [Language Independence and Language-Independent Components](../../../../standard/language-independence-and-language-independent-components.md) (CLS), so CLS-compliant code cannot use a component that defines such names.</span></span> <span data-ttu-id="35040-116">Sin embargo, un carácter de subrayado en cualquier otra posición en un nombre de elemento es conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="35040-116">However, an underscore in any other position in an element name is CLS-compliant.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="35040-117">Instrucciones de longitud de nombre</span><span class="sxs-lookup"><span data-stu-id="35040-117">Name Length Guidelines</span></span>  

 <span data-ttu-id="35040-118">Como cuestión práctica, su nombre debe ser lo más corto posible y, al mismo tiempo, identificar claramente la naturaleza del elemento.</span><span class="sxs-lookup"><span data-stu-id="35040-118">As a practical matter, your name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="35040-119">Esto mejora la legibilidad del código y reduce la longitud de línea y el tamaño del archivo de origen.</span><span class="sxs-lookup"><span data-stu-id="35040-119">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="35040-120">Por otro lado, el nombre no debe ser tan corto que no describe adecuadamente lo que representa el elemento y cómo lo usa el código.</span><span class="sxs-lookup"><span data-stu-id="35040-120">On the other hand, your name should not be so short that it does not adequately describe what the element represents and how your code uses it.</span></span> <span data-ttu-id="35040-121">Esto es importante para la legibilidad del código.</span><span class="sxs-lookup"><span data-stu-id="35040-121">This is important for the readability of your code.</span></span> <span data-ttu-id="35040-122">Si alguien más está intentando comprenderlo, o si usted lo consulta mucho tiempo después de escribirlo, los nombres de elemento adecuados pueden ahorrar una cantidad considerable de tiempo.</span><span class="sxs-lookup"><span data-stu-id="35040-122">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, suitable element names can save a considerable amount of time.</span></span>  
  
## <a name="escaped-names"></a><span data-ttu-id="35040-123">Nombres con escape</span><span class="sxs-lookup"><span data-stu-id="35040-123">Escaped Names</span></span>  

 <span data-ttu-id="35040-124">Por lo general, un nombre de elemento no debe coincidir con ninguna de las palabras clave reservadas por Visual Basic, como `Case` o `Friend` .</span><span class="sxs-lookup"><span data-stu-id="35040-124">Generally, an element name must not match any of the keywords reserved by Visual Basic, such as `Case` or `Friend`.</span></span> <span data-ttu-id="35040-125">Sin embargo, puede definir un *nombre con escape*, entre corchetes ( `[ ]` ).</span><span class="sxs-lookup"><span data-stu-id="35040-125">However, you can define an *escaped name*, which is enclosed by brackets (`[ ]`).</span></span> <span data-ttu-id="35040-126">Un nombre con escape puede coincidir con cualquier palabra clave Visual Basic, ya que los corchetes quitan cualquier ambigüedad.</span><span class="sxs-lookup"><span data-stu-id="35040-126">An escaped name can match any Visual Basic keyword, since the brackets remove any ambiguity.</span></span> <span data-ttu-id="35040-127">También se usan los corchetes cuando se hace referencia al nombre más adelante en el código.</span><span class="sxs-lookup"><span data-stu-id="35040-127">You also use the brackets when you refer to the name later in your code.</span></span>  
  
 <span data-ttu-id="35040-128">En general, los nombres de escape solo se deben usar cuando:</span><span class="sxs-lookup"><span data-stu-id="35040-128">In general, you should use escaped names only when:</span></span>  
  
- <span data-ttu-id="35040-129">El código se migró desde una versión anterior de Visual Basic que no reservó la palabra clave que se usa como nombre. de</span><span class="sxs-lookup"><span data-stu-id="35040-129">Your code has migrated from a previous version of Visual Basic that did not reserve the keyword being used as a name; or</span></span>  
  
- <span data-ttu-id="35040-130">Está trabajando con código escrito en otro lenguaje en el que la palabra clave especificada no está reservada.</span><span class="sxs-lookup"><span data-stu-id="35040-130">You are working with code written in another language in which the given keyword is not reserved.</span></span>  
  
 <span data-ttu-id="35040-131">De lo contrario, debería considerar la posibilidad de cambiar el nombre del elemento si su nombre entra en conflicto con una palabra clave.</span><span class="sxs-lookup"><span data-stu-id="35040-131">Otherwise, you should consider renaming the element if its name conflicts with a keyword.</span></span> <span data-ttu-id="35040-132">El entorno de desarrollo integrado (IDE) proporciona una manera sencilla de hacerlo.</span><span class="sxs-lookup"><span data-stu-id="35040-132">The integrated development environment (IDE) provides an easy way to do this.</span></span> <span data-ttu-id="35040-133">Para obtener más información, consulte [refactorización](/visualstudio/ide/refactoring-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="35040-133">For more information, see [Refactoring](/visualstudio/ide/refactoring-in-visual-studio).</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="35040-134">Distinción de mayúsculas y minúsculas en nombres</span><span class="sxs-lookup"><span data-stu-id="35040-134">Case Sensitivity in Names</span></span>  

 <span data-ttu-id="35040-135">Los nombres de elementos de Visual Basic no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="35040-135">Element names in Visual Basic are case-insensitive.</span></span> <span data-ttu-id="35040-136">Esto significa que cuando el compilador compara dos nombres que solo se diferencian en el uso de mayúsculas y minúsculas, los interpreta como el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="35040-136">This means that when the compiler compares two names that differ in alphabetic case only, it interprets them as the same name.</span></span> <span data-ttu-id="35040-137">Por ejemplo, considera que `ABC` y `abc` hacen referencia al mismo elemento declarado.</span><span class="sxs-lookup"><span data-stu-id="35040-137">For example, it considers `ABC` and `abc` to refer to the same declared element.</span></span>  
  
 <span data-ttu-id="35040-138">Sin embargo, Common Language Runtime (CLR) usa enlaces que distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="35040-138">However, the common language runtime (CLR) uses case-sensitive binding.</span></span> <span data-ttu-id="35040-139">Por lo tanto, cuando genere un ensamblado o una DLL que pueda estar disponible para otros ensamblados, sus nombres ya no distinguirán entre mayúsculas o minúsculas.</span><span class="sxs-lookup"><span data-stu-id="35040-139">Therefore, when you produce an assembly or a DLL and make it available to other assemblies, your names are no longer case-insensitive.</span></span> <span data-ttu-id="35040-140">Por ejemplo, si define una clase que tiene un elemento denominado `ABC`, y otros ensamblados usan la clase mediante Common Language Runtime, deberán hacer referencia al elemento como `ABC`.</span><span class="sxs-lookup"><span data-stu-id="35040-140">For example, if you define a class with an element called `ABC`, and other assemblies make use of your class through the common language runtime, they must refer to the element as `ABC`.</span></span> <span data-ttu-id="35040-141">Si posteriormente vuelve a compilar la clase y cambia el nombre del elemento a `abc` , los otros ensamblados que usen la clase ya no podrán tener acceso a ese elemento.</span><span class="sxs-lookup"><span data-stu-id="35040-141">If you subsequently recompile your class and change the element's name to `abc`, the other assemblies using your class could no longer access that element.</span></span> <span data-ttu-id="35040-142">Por lo tanto, cuando se lance una versión actualizada de un ensamblado, no se deben cambiar las mayúsculas o minúsculas de los elementos públicos.</span><span class="sxs-lookup"><span data-stu-id="35040-142">Therefore, when you release an updated version of an assembly, you should not change the alphabetic case of any public elements.</span></span>  
  
## <a name="names-and-locales"></a><span data-ttu-id="35040-143">Nombres y configuraciones regionales</span><span class="sxs-lookup"><span data-stu-id="35040-143">Names and Locales</span></span>  

 <span data-ttu-id="35040-144">La comparación de nombres es independiente de la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="35040-144">Comparison of names is independent of locale.</span></span> <span data-ttu-id="35040-145">Si dos nombres coinciden en una configuración regional, se garantiza que coincidan en todas las configuraciones regionales.</span><span class="sxs-lookup"><span data-stu-id="35040-145">If two names match in one locale, they are guaranteed to match in all locales.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35040-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="35040-146">See also</span></span>

- [<span data-ttu-id="35040-147">Elementos declarados</span><span class="sxs-lookup"><span data-stu-id="35040-147">Declared Elements</span></span>](index.md)
- [<span data-ttu-id="35040-148">Características de los elementos declarados</span><span class="sxs-lookup"><span data-stu-id="35040-148">Declared Element Characteristics</span></span>](declared-element-characteristics.md)
- [<span data-ttu-id="35040-149">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="35040-149">References to Declared Elements</span></span>](references-to-declared-elements.md)
- [<span data-ttu-id="35040-150">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="35040-150">Statements</span></span>](../../../language-reference/statements/index.md)

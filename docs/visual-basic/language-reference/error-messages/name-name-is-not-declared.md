---
title: Nombre &#39; &lt;nombre&gt; &#39; no se ha declarado
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30451
- vbc30451
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 26245952a2dc5341dedba6c497c47773b882b49b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="name-39ltnamegt39-is-not-declared"></a><span data-ttu-id="f9299-102">Nombre &#39; &lt;nombre&gt; &#39; no se ha declarado</span><span class="sxs-lookup"><span data-stu-id="f9299-102">Name &#39;&lt;name&gt;&#39; is not declared</span></span>
<span data-ttu-id="f9299-103">Una instrucción hace referencia a un elemento de programación, pero el compilador no encuentra un elemento con ese nombre exacto.</span><span class="sxs-lookup"><span data-stu-id="f9299-103">A statement refers to a programming element, but the compiler cannot find an element with that exact name.</span></span>  
  
 <span data-ttu-id="f9299-104">**Id. de error:** BC30451</span><span class="sxs-lookup"><span data-stu-id="f9299-104">**Error ID:** BC30451</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f9299-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="f9299-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="f9299-106">Compruebe que el nombre de la instrucción de referencia esté bien escrito.</span><span class="sxs-lookup"><span data-stu-id="f9299-106">Check the spelling of the name in the referring statement.</span></span> <span data-ttu-id="f9299-107">Visual Basic distingue mayúsculas de minúsculas, pero cualquier otra variación en la ortografía se considera como un nombre completamente distinto.</span><span class="sxs-lookup"><span data-stu-id="f9299-107">Visual Basic is case-insensitive, but any other variation in the spelling is regarded as a completely different name.</span></span> <span data-ttu-id="f9299-108">Tenga en cuenta que el carácter de subrayado (`_`) es parte del nombre y, por tanto, parte de la ortografía.</span><span class="sxs-lookup"><span data-stu-id="f9299-108">Note that the underscore (`_`) is part of the name and therefore part of the spelling.</span></span>  
  
2.  <span data-ttu-id="f9299-109">Compruebe que tiene el operador de acceso de miembro (`.`) entre un objeto y su miembro.</span><span class="sxs-lookup"><span data-stu-id="f9299-109">Check that you have the member access operator (`.`) between an object and its member.</span></span> <span data-ttu-id="f9299-110">Por ejemplo, si tiene un control <xref:System.Windows.Forms.TextBox> denominado `TextBox1`, para tener acceso a su propiedad <xref:System.Windows.Forms.TextBoxBase.Text%2A> debe escribir `TextBox1.Text`.</span><span class="sxs-lookup"><span data-stu-id="f9299-110">For example, if you have a <xref:System.Windows.Forms.TextBox> control named `TextBox1`, to access its <xref:System.Windows.Forms.TextBoxBase.Text%2A> property you should type `TextBox1.Text`.</span></span> <span data-ttu-id="f9299-111">Si en su lugar escribe `TextBox1Text`, ha creado un nombre diferente.</span><span class="sxs-lookup"><span data-stu-id="f9299-111">If instead you type `TextBox1Text`, you have created a different name.</span></span>  
  
3.  <span data-ttu-id="f9299-112">Si la ortografía es correcta y la sintaxis de cualquier acceso a miembros de objeto es correcta, compruebe que se ha declarado el elemento.</span><span class="sxs-lookup"><span data-stu-id="f9299-112">If the spelling is correct and the syntax of any object member access is correct, verify that the element has been declared.</span></span> <span data-ttu-id="f9299-113">Para obtener más información, consulte [elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/index.md).</span><span class="sxs-lookup"><span data-stu-id="f9299-113">For more information, see [Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/index.md).</span></span>  
  
4.  <span data-ttu-id="f9299-114">Si se ha declarado el elemento de programación, compruebe que esté dentro del ámbito.</span><span class="sxs-lookup"><span data-stu-id="f9299-114">If the programming element has been declared, check that it is in scope.</span></span> <span data-ttu-id="f9299-115">Si la instrucción de referencia está fuera de la región que declara el elemento de programación, debe calificar el nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="f9299-115">If the referring statement is outside the region declaring the programming element, you might need to qualify the element name.</span></span> <span data-ttu-id="f9299-116">Para obtener más información, consulte [ámbito en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span><span class="sxs-lookup"><span data-stu-id="f9299-116">For more information, see [Scope in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9299-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9299-117">See Also</span></span>  
 [<span data-ttu-id="f9299-118">Resumen de constantes y declaraciones</span><span class="sxs-lookup"><span data-stu-id="f9299-118">Declarations and Constants Summary</span></span>](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)  
 [<span data-ttu-id="f9299-119">Convenciones de nomenclatura de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f9299-119">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [<span data-ttu-id="f9299-120">Nombres de elementos declarados</span><span class="sxs-lookup"><span data-stu-id="f9299-120">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="f9299-121">Referencias a elementos declarados</span><span class="sxs-lookup"><span data-stu-id="f9299-121">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)

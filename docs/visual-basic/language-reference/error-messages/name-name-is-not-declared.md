---
title: Nombre de &#39; &lt;nombre&gt;&#39; no se ha declarado
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30451
- vbc30451
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7a63ae74c7179d71756e2b9b4bf6b41a71ce12a6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="name-39ltnamegt39-is-not-declared"></a><span data-ttu-id="9672c-102">Nombre de &#39; &lt;nombre&gt;&#39; no se ha declarado</span><span class="sxs-lookup"><span data-stu-id="9672c-102">Name &#39;&lt;name&gt;&#39; is not declared</span></span>
<span data-ttu-id="9672c-103">Una instrucción hace referencia a un elemento de programación, pero el compilador no encuentra un elemento con ese nombre exacto.</span><span class="sxs-lookup"><span data-stu-id="9672c-103">A statement refers to a programming element, but the compiler cannot find an element with that exact name.</span></span>  
  
 <span data-ttu-id="9672c-104">**Id. de error:** BC30451</span><span class="sxs-lookup"><span data-stu-id="9672c-104">**Error ID:** BC30451</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9672c-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="9672c-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="9672c-106">Compruebe que el nombre de la instrucción de referencia esté bien escrito.</span><span class="sxs-lookup"><span data-stu-id="9672c-106">Check the spelling of the name in the referring statement.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="9672c-107">distingue mayúsculas de minúsculas, pero cualquier otra variación en la ortografía se considera como un nombre completamente distinto.</span><span class="sxs-lookup"><span data-stu-id="9672c-107"> is case-insensitive, but any other variation in the spelling is regarded as a completely different name.</span></span> <span data-ttu-id="9672c-108">Tenga en cuenta que el carácter de subrayado (`_`) es parte del nombre y, por tanto, parte de la ortografía.</span><span class="sxs-lookup"><span data-stu-id="9672c-108">Note that the underscore (`_`) is part of the name and therefore part of the spelling.</span></span>  
  
2.  <span data-ttu-id="9672c-109">Compruebe que tiene el operador de acceso de miembro (`.`) entre un objeto y su miembro.</span><span class="sxs-lookup"><span data-stu-id="9672c-109">Check that you have the member access operator (`.`) between an object and its member.</span></span> <span data-ttu-id="9672c-110">Por ejemplo, si tiene un control <xref:System.Windows.Forms.TextBox> denominado `TextBox1`, para tener acceso a su propiedad <xref:System.Windows.Forms.TextBoxBase.Text%2A> debe escribir `TextBox1.Text`.</span><span class="sxs-lookup"><span data-stu-id="9672c-110">For example, if you have a <xref:System.Windows.Forms.TextBox> control named `TextBox1`, to access its <xref:System.Windows.Forms.TextBoxBase.Text%2A> property you should type `TextBox1.Text`.</span></span> <span data-ttu-id="9672c-111">Si en su lugar escribe `TextBox1Text`, ha creado un nombre diferente.</span><span class="sxs-lookup"><span data-stu-id="9672c-111">If instead you type `TextBox1Text`, you have created a different name.</span></span>  
  
3.  <span data-ttu-id="9672c-112">Si la ortografía es correcta y la sintaxis de cualquier acceso a miembros de objeto es correcta, compruebe que se ha declarado el elemento.</span><span class="sxs-lookup"><span data-stu-id="9672c-112">If the spelling is correct and the syntax of any object member access is correct, verify that the element has been declared.</span></span> <span data-ttu-id="9672c-113">Para obtener más información, consulte [elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/index.md).</span><span class="sxs-lookup"><span data-stu-id="9672c-113">For more information, see [Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/index.md).</span></span>  
  
4.  <span data-ttu-id="9672c-114">Si se ha declarado el elemento de programación, compruebe que esté dentro del ámbito.</span><span class="sxs-lookup"><span data-stu-id="9672c-114">If the programming element has been declared, check that it is in scope.</span></span> <span data-ttu-id="9672c-115">Si la instrucción de referencia está fuera de la región que declara el elemento de programación, debe calificar el nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="9672c-115">If the referring statement is outside the region declaring the programming element, you might need to qualify the element name.</span></span> <span data-ttu-id="9672c-116">Para obtener más información, consulte [ámbito en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span><span class="sxs-lookup"><span data-stu-id="9672c-116">For more information, see [Scope in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9672c-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9672c-117">See Also</span></span>  
 [<span data-ttu-id="9672c-118">Resumen de constantes y declaraciones</span><span class="sxs-lookup"><span data-stu-id="9672c-118">Declarations and Constants Summary</span></span>](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)  
 [<span data-ttu-id="9672c-119">Convenciones de nomenclatura de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9672c-119">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [<span data-ttu-id="9672c-120">Nombres de elementos declarados</span><span class="sxs-lookup"><span data-stu-id="9672c-120">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="9672c-121">Referencias a elementos declarados</span><span class="sxs-lookup"><span data-stu-id="9672c-121">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)

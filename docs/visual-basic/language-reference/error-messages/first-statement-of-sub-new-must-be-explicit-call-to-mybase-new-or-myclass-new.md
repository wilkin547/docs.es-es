---
title: 'La primera instrucción de este &#39;Sub New&#39; debe ser una llamada explícita a &#39;MyBase.New&#39; o &#39;MyClass.New&#39; porque el &#39; &lt;nombreconstructor&gt; &#39; en la clase base &#39; &lt;nombredeclasebase&gt; &#39; de &#39; &lt;nombreclasederivada&gt; &#39; está marcado como obsoleto: &#39; &lt;errormessage&gt;&#39;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30920
- bc30920
helpviewer_keywords:
- BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7690c9dcdb97e63959d2f0e31791d55ee7b09ffc
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="first-statement-of-this-39sub-new39-must-be-an-explicit-call-to-39mybasenew39-or-39myclassnew39-because-the-39ltconstructornamegt39-in-the-base-class-39ltbaseclassnamegt39-of-39ltderivedclassnamegt39-is-marked-obsolete-39lterrormessagegt39"></a><span data-ttu-id="d6e78-102">La primera instrucción de este &#39;Sub New&#39; debe ser una llamada explícita a &#39;MyBase.New&#39; o &#39;MyClass.New&#39; porque el &#39; &lt;nombreconstructor&gt; &#39; en la clase base &#39; &lt;nombredeclasebase&gt; &#39; de &#39; &lt;nombreclasederivada&gt; &#39; está marcado como obsoleto: &#39; &lt;errormessage&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="d6e78-102">First statement of this &#39;Sub New&#39; must be an explicit call to &#39;MyBase.New&#39; or &#39;MyClass.New&#39; because the &#39;&lt;constructorname&gt;&#39; in the base class &#39;&lt;baseclassname&gt;&#39; of &#39;&lt;derivedclassname&gt;&#39; is marked obsolete: &#39;&lt;errormessage&gt;&#39;</span></span>
<span data-ttu-id="d6e78-103">Un constructor de clase no realiza una llamada de manera explícita a un constructor de clase base y el constructor de clase base se marca con el atributo <xref:System.ObsoleteAttribute> y la directiva para tratarlo como un error.</span><span class="sxs-lookup"><span data-stu-id="d6e78-103">A class constructor does not explicitly call a base class constructor, and the implicit base class constructor is marked with the <xref:System.ObsoleteAttribute> attribute and the directive to treat it as an error.</span></span>  
  
 <span data-ttu-id="d6e78-104">Cuando un constructor de clase derivada no llama a un constructor de clase base, Visual Basic intenta generar una llamada implícita a un constructor de clase base sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="d6e78-104">When a derived class constructor does not call a base class constructor, Visual Basic attempts to generate an implicit call to a parameterless base class constructor.</span></span> <span data-ttu-id="d6e78-105">Si no hay ningún constructor accesible en la clase base que se pueda llamar sin argumentos, Visual Basic no se puede generar una llamada implícita.</span><span class="sxs-lookup"><span data-stu-id="d6e78-105">If there is no accessible constructor in the base class that can be called without arguments, Visual Basic cannot generate an implicit call.</span></span> <span data-ttu-id="d6e78-106">En este caso, el constructor necesario se marca con el <xref:System.ObsoleteAttribute> de atributo, por lo que Visual Basic no puede llamarlo.</span><span class="sxs-lookup"><span data-stu-id="d6e78-106">In this case, the required constructor is marked with the <xref:System.ObsoleteAttribute> attribute, so Visual Basic cannot call it.</span></span>  
  
 <span data-ttu-id="d6e78-107">Para marcar que cualquier elemento de programación ya no está en uso, aplíquele <xref:System.ObsoleteAttribute> .</span><span class="sxs-lookup"><span data-stu-id="d6e78-107">You can mark any programming element as being no longer in use by applying <xref:System.ObsoleteAttribute> to it.</span></span> <span data-ttu-id="d6e78-108">Si lo hace, puede establecer la propiedad <xref:System.ObsoleteAttribute.IsError%2A> del atributo en `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="d6e78-108">If you do this, you can set the attribute's <xref:System.ObsoleteAttribute.IsError%2A> property to either `True` or `False`.</span></span> <span data-ttu-id="d6e78-109">Si se establece en `True`, el compilador trata como un error los intentos de usar el elemento.</span><span class="sxs-lookup"><span data-stu-id="d6e78-109">If you set it to `True`, the compiler treats an attempt to use the element as an error.</span></span> <span data-ttu-id="d6e78-110">Si se establece en `False`o se deja el valor predeterminado `False`, el compilador emite una advertencia si se produce un intento de usar el elemento.</span><span class="sxs-lookup"><span data-stu-id="d6e78-110">If you set it to `False`, or let it default to `False`, the compiler issues a warning if there is an attempt to use the element.</span></span>  
  
 <span data-ttu-id="d6e78-111">**Id. de error:** BC30920</span><span class="sxs-lookup"><span data-stu-id="d6e78-111">**Error ID:** BC30920</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d6e78-112">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="d6e78-112">To correct this error</span></span>  
  
1.  <span data-ttu-id="d6e78-113">Examine el mensaje de error indicado y tome las medidas adecuadas.</span><span class="sxs-lookup"><span data-stu-id="d6e78-113">Examine the quoted error message and take appropriate action.</span></span>  
  
2.  <span data-ttu-id="d6e78-114">Incluya una llamada a `MyBase.New()` o `MyClass.New()` como la primera instrucción de `Sub New` en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="d6e78-114">Include a call to `MyBase.New()` or `MyClass.New()` as the first statement of the `Sub New` in the derived class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6e78-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6e78-115">See Also</span></span>  
 [<span data-ttu-id="d6e78-116">Información general de atributos</span><span class="sxs-lookup"><span data-stu-id="d6e78-116">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
 

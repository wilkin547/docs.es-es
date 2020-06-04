---
title: "La primera instrucción de este 'Sub New' debe ser una llamada explícita a 'MyBase.New' o a 'MyClass.New' porque el constructor '<constructorname>' de la clase base '<baseclassname>' de '<derivedclassname>' está marcado como obsoleto: '<errormessage>'"
ms.date: 07/20/2015
f1_keywords:
- vbc30920
- bc30920
helpviewer_keywords:
- BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
ms.openlocfilehash: 33dd15e3f5f5538963597f2b00f4214895e1f47a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403010"
---
# <a name="first-statement-of-this-sub-new-must-be-an-explicit-call-to-mybasenew-or-myclassnew-because-the-constructorname-in-the-base-class-baseclassname-of-derivedclassname-is-marked-obsolete-errormessage"></a><span data-ttu-id="cd735-102">La primera instrucción de este 'Sub New' debe ser una llamada explícita a 'MyBase.New' o a 'MyClass.New' porque el constructor '\<constructorname>' de la clase base '\<baseclassname>' de '\<derivedclassname>' está marcado como obsoleto: '\<errormessage>'</span><span class="sxs-lookup"><span data-stu-id="cd735-102">First statement of this 'Sub New' must be an explicit call to 'MyBase.New' or 'MyClass.New' because the '\<constructorname>' in the base class '\<baseclassname>' of '\<derivedclassname>' is marked obsolete: '\<errormessage>'</span></span>
<span data-ttu-id="cd735-103">Un constructor de clase no realiza una llamada de manera explícita a un constructor de clase base y el constructor de clase base se marca con el atributo <xref:System.ObsoleteAttribute> y la directiva para tratarlo como un error.</span><span class="sxs-lookup"><span data-stu-id="cd735-103">A class constructor does not explicitly call a base class constructor, and the implicit base class constructor is marked with the <xref:System.ObsoleteAttribute> attribute and the directive to treat it as an error.</span></span>  
  
 <span data-ttu-id="cd735-104">Cuando un constructor de clase derivada no llama a un constructor de clase base, Visual Basic intenta generar una llamada implícita a un constructor de clase base sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="cd735-104">When a derived class constructor does not call a base class constructor, Visual Basic attempts to generate an implicit call to a parameterless base class constructor.</span></span> <span data-ttu-id="cd735-105">Si no hay ningún constructor accesible en la clase base al que se pueda llamar sin argumentos, Visual Basic no puede generar una llamada implícita.</span><span class="sxs-lookup"><span data-stu-id="cd735-105">If there is no accessible constructor in the base class that can be called without arguments, Visual Basic cannot generate an implicit call.</span></span> <span data-ttu-id="cd735-106">En este caso, el constructor necesario se marca con el <xref:System.ObsoleteAttribute> atributo, por lo que Visual Basic no puede llamarlo.</span><span class="sxs-lookup"><span data-stu-id="cd735-106">In this case, the required constructor is marked with the <xref:System.ObsoleteAttribute> attribute, so Visual Basic cannot call it.</span></span>  
  
 <span data-ttu-id="cd735-107">Para marcar que cualquier elemento de programación ya no está en uso, aplíquele <xref:System.ObsoleteAttribute> .</span><span class="sxs-lookup"><span data-stu-id="cd735-107">You can mark any programming element as being no longer in use by applying <xref:System.ObsoleteAttribute> to it.</span></span> <span data-ttu-id="cd735-108">Si lo hace, puede establecer la propiedad <xref:System.ObsoleteAttribute.IsError%2A> del atributo en `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="cd735-108">If you do this, you can set the attribute's <xref:System.ObsoleteAttribute.IsError%2A> property to either `True` or `False`.</span></span> <span data-ttu-id="cd735-109">Si se establece en `True`, el compilador trata como un error los intentos de usar el elemento.</span><span class="sxs-lookup"><span data-stu-id="cd735-109">If you set it to `True`, the compiler treats an attempt to use the element as an error.</span></span> <span data-ttu-id="cd735-110">Si se establece en `False`o se deja el valor predeterminado `False`, el compilador emite una advertencia si hay un intento de usar el elemento.</span><span class="sxs-lookup"><span data-stu-id="cd735-110">If you set it to `False`, or let it default to `False`, the compiler issues a warning if there is an attempt to use the element.</span></span>  
  
 <span data-ttu-id="cd735-111">**Identificador de error:** BC30920</span><span class="sxs-lookup"><span data-stu-id="cd735-111">**Error ID:** BC30920</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cd735-112">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="cd735-112">To correct this error</span></span>  
  
1. <span data-ttu-id="cd735-113">Examine el mensaje de error indicado y tome las medidas adecuadas.</span><span class="sxs-lookup"><span data-stu-id="cd735-113">Examine the quoted error message and take appropriate action.</span></span>  
  
2. <span data-ttu-id="cd735-114">Incluya una llamada a `MyBase.New()` o `MyClass.New()` como la primera instrucción de `Sub New` en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="cd735-114">Include a call to `MyBase.New()` or `MyClass.New()` as the first statement of the `Sub New` in the derived class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd735-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cd735-115">See also</span></span>

- [<span data-ttu-id="cd735-116">Información general de atributos</span><span class="sxs-lookup"><span data-stu-id="cd735-116">Attributes overview</span></span>](../../programming-guide/concepts/attributes/index.md)

---
title: "'<elementname>' está obsoleto (Advertencia de Visual Basic)"
ms.date: 07/20/2015
f1_keywords:
- vbc40008
- bc40008
helpviewer_keywords:
- BC40008
ms.assetid: 729e3eb5-76ac-4c55-9fdd-78350e0de55e
ms.openlocfilehash: 7914bc859966e17f3da41c9a13a01573b31baf91
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409678"
---
# <a name="elementname-is-obsolete-visual-basic-warning"></a><span data-ttu-id="2c1e8-102">'\<elementname>' está obsoleto (Advertencia de Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2c1e8-102">'\<elementname>' is obsolete (Visual Basic Warning)</span></span>
<span data-ttu-id="2c1e8-103">Una instrucción intenta obtener acceso a un elemento de programación que se ha marcado con el atributo <xref:System.ObsoleteAttribute> y la directiva para tratarlo como una advertencia.</span><span class="sxs-lookup"><span data-stu-id="2c1e8-103">A statement attempts to access a programming element which has been marked with the <xref:System.ObsoleteAttribute> attribute and the directive to treat it as a warning.</span></span>  
  
 <span data-ttu-id="2c1e8-104">Para marcar que cualquier elemento de programación ya no está en uso, aplíquele <xref:System.ObsoleteAttribute> .</span><span class="sxs-lookup"><span data-stu-id="2c1e8-104">You can mark any programming element as being no longer in use by applying <xref:System.ObsoleteAttribute> to it.</span></span> <span data-ttu-id="2c1e8-105">Si lo hace, puede establecer la propiedad <xref:System.ObsoleteAttribute.IsError%2A> del atributo en `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="2c1e8-105">If you do this, you can set the attribute's <xref:System.ObsoleteAttribute.IsError%2A> property to either `True` or `False`.</span></span> <span data-ttu-id="2c1e8-106">Si se establece en `True`, el compilador trata como un error los intentos de usar el elemento.</span><span class="sxs-lookup"><span data-stu-id="2c1e8-106">If you set it to `True`, the compiler treats an attempt to use the element as an error.</span></span> <span data-ttu-id="2c1e8-107">Si se establece en `False`o se deja el valor predeterminado `False`, el compilador emite una advertencia si hay un intento de usar el elemento.</span><span class="sxs-lookup"><span data-stu-id="2c1e8-107">If you set it to `False`, or let it default to `False`, the compiler issues a warning if there is an attempt to use the element.</span></span>  
  
 <span data-ttu-id="2c1e8-108">De forma predeterminada, este mensaje es una advertencia, ya que la propiedad <xref:System.ObsoleteAttribute.IsError%2A> de <xref:System.ObsoleteAttribute> es `False`.</span><span class="sxs-lookup"><span data-stu-id="2c1e8-108">By default, this message is a warning, because the <xref:System.ObsoleteAttribute.IsError%2A> property of <xref:System.ObsoleteAttribute> is `False`.</span></span> <span data-ttu-id="2c1e8-109">Para más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="2c1e8-109">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="2c1e8-110">**Identificador de error:** BC40008</span><span class="sxs-lookup"><span data-stu-id="2c1e8-110">**Error ID:** BC40008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2c1e8-111">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="2c1e8-111">To correct this error</span></span>  
  
- <span data-ttu-id="2c1e8-112">Asegúrese de que la referencia del código fuente escriba correctamente el nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="2c1e8-112">Ensure that the source-code reference is spelling the element name correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c1e8-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2c1e8-113">See also</span></span>

- [<span data-ttu-id="2c1e8-114">Información general de atributos</span><span class="sxs-lookup"><span data-stu-id="2c1e8-114">Attributes overview</span></span>](../../programming-guide/concepts/attributes/index.md)

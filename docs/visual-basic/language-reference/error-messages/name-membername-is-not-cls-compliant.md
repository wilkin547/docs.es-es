---
title: Nombre &lt;membername&gt; no es compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
ms.openlocfilehash: 26ff13de461d5a96724868b7928129a326cdf1d0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593347"
---
# <a name="name-ltmembernamegt-is-not-cls-compliant"></a><span data-ttu-id="1716d-102">Nombre &lt;membername&gt; no es compatible con CLS</span><span class="sxs-lookup"><span data-stu-id="1716d-102">Name &lt;membername&gt; is not CLS-compliant</span></span>
<span data-ttu-id="1716d-103">Un ensamblado está marcado como `<CLSCompliant(True)>` pero expone un miembro con un nombre que comienza con un carácter de subrayado (`_`).</span><span class="sxs-lookup"><span data-stu-id="1716d-103">An assembly is marked as `<CLSCompliant(True)>` but exposes a member with a name that begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="1716d-104">Un elemento de programación puede contener uno o más caracteres de subrayado, pero to sea compatible con la [independencia del lenguaje y componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS), no debe comenzar con un carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="1716d-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="1716d-105">Vea [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="1716d-105">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="1716d-106">Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad.</span><span class="sxs-lookup"><span data-stu-id="1716d-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="1716d-107">No hay ningún valor predeterminado para este parámetro y debe proporcionar un valor.</span><span class="sxs-lookup"><span data-stu-id="1716d-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="1716d-108">Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.</span><span class="sxs-lookup"><span data-stu-id="1716d-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="1716d-109">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="1716d-109">By default, this message is a warning.</span></span> <span data-ttu-id="1716d-110">Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="1716d-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="1716d-111">**Id. de error:** BC40031</span><span class="sxs-lookup"><span data-stu-id="1716d-111">**Error ID:** BC40031</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1716d-112">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="1716d-112">To correct this error</span></span>  
  
-   <span data-ttu-id="1716d-113">Si tiene control sobre el código fuente, cambie el nombre de miembro para que no comienza con un carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="1716d-113">If you have control over the source code, change the member name so that it does not begin with an underscore.</span></span>  
  
-   <span data-ttu-id="1716d-114">Si necesita que el nombre de miembro permanecen sin cambios, quite el <xref:System.CLSCompliantAttribute> de su definición o márquelo como `<CLSCompliant(False)>`.</span><span class="sxs-lookup"><span data-stu-id="1716d-114">If you require that the member name remain unchanged, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span> <span data-ttu-id="1716d-115">Todavía puede marcar el ensamblado como `<CLSCompliant(True)>`.</span><span class="sxs-lookup"><span data-stu-id="1716d-115">You can still mark the assembly as `<CLSCompliant(True)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1716d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1716d-116">See Also</span></span>  
 [<span data-ttu-id="1716d-117">Nombres de elementos declarados</span><span class="sxs-lookup"><span data-stu-id="1716d-117">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="1716d-118">Convenciones de nomenclatura de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1716d-118">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  


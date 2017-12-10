---
title: Nombre &lt;membername&gt; no es compatible con CLS
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords: BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 67d9d2dcee1d78ed965c40581029a86e54d91216
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2017
---
# <a name="name-ltmembernamegt-is-not-cls-compliant"></a><span data-ttu-id="3aed5-102">Nombre &lt;membername&gt; no es compatible con CLS</span><span class="sxs-lookup"><span data-stu-id="3aed5-102">Name &lt;membername&gt; is not CLS-compliant</span></span>
<span data-ttu-id="3aed5-103">Un ensamblado está marcado como `<CLSCompliant(True)>` pero expone un miembro con un nombre que comienza con un carácter de subrayado (`_`).</span><span class="sxs-lookup"><span data-stu-id="3aed5-103">An assembly is marked as `<CLSCompliant(True)>` but exposes a member with a name that begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="3aed5-104">Un elemento de programación puede contener uno o más caracteres de subrayado, pero to sea compatible con la [independencia del lenguaje y componentes independientes del lenguaje](../../../../docs/standard/language-independence-and-language-independent-components.md) (CLS), no debe comenzar con un carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="3aed5-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../../docs/standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="3aed5-105">Vea [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="3aed5-105">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="3aed5-106">Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad.</span><span class="sxs-lookup"><span data-stu-id="3aed5-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="3aed5-107">No hay ningún valor predeterminado para este parámetro y debe proporcionar un valor.</span><span class="sxs-lookup"><span data-stu-id="3aed5-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="3aed5-108">Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.</span><span class="sxs-lookup"><span data-stu-id="3aed5-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="3aed5-109">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="3aed5-109">By default, this message is a warning.</span></span> <span data-ttu-id="3aed5-110">Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="3aed5-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="3aed5-111">**Id. de error:** BC40031</span><span class="sxs-lookup"><span data-stu-id="3aed5-111">**Error ID:** BC40031</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3aed5-112">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="3aed5-112">To correct this error</span></span>  
  
-   <span data-ttu-id="3aed5-113">Si tiene control sobre el código fuente, cambie el nombre de miembro para que no comienza con un carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="3aed5-113">If you have control over the source code, change the member name so that it does not begin with an underscore.</span></span>  
  
-   <span data-ttu-id="3aed5-114">Si necesita que el nombre de miembro permanecen sin cambios, quite el <xref:System.CLSCompliantAttribute> de su definición o márquelo como `<CLSCompliant(False)>`.</span><span class="sxs-lookup"><span data-stu-id="3aed5-114">If you require that the member name remain unchanged, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span> <span data-ttu-id="3aed5-115">Todavía puede marcar el ensamblado como `<CLSCompliant(True)>`.</span><span class="sxs-lookup"><span data-stu-id="3aed5-115">You can still mark the assembly as `<CLSCompliant(True)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aed5-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="3aed5-116">See Also</span></span>  
 [<span data-ttu-id="3aed5-117">Nombres de elementos declarados</span><span class="sxs-lookup"><span data-stu-id="3aed5-117">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="3aed5-118">Convenciones de nomenclatura de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3aed5-118">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [<span data-ttu-id="3aed5-119">\<PAVE sobre > escribir código conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="3aed5-119">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)

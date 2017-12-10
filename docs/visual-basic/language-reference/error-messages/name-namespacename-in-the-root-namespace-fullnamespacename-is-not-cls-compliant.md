---
title: "Nombre &lt;namespacename&gt; en el espacio de nombres raíz &lt;fullnamespacename&gt; no es compatible con CLS"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40039
- bc40039
helpviewer_keywords: BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 36de8b6a27c47e9e7192aed10e6b561bb0c07acc
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2017
---
# <a name="name-ltnamespacenamegt-in-the-root-namespace-ltfullnamespacenamegt-is-not-cls-compliant"></a><span data-ttu-id="dcde7-102">Nombre &lt;namespacename&gt; en el espacio de nombres raíz &lt;fullnamespacename&gt; no es compatible con CLS</span><span class="sxs-lookup"><span data-stu-id="dcde7-102">Name &lt;namespacename&gt; in the root namespace &lt;fullnamespacename&gt; is not CLS-compliant</span></span>
<span data-ttu-id="dcde7-103">Un ensamblado está marcado como `<CLSCompliant(True)>`, pero un elemento del nombre de espacio de nombres raíz comienza con un carácter de subrayado (`_`).</span><span class="sxs-lookup"><span data-stu-id="dcde7-103">An assembly is marked as `<CLSCompliant(True)>`, but an element of the root namespace name begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="dcde7-104">Un elemento de programación puede contener uno o más caracteres de subrayado, pero to sea compatible con la [independencia del lenguaje y componentes independientes del lenguaje](../../../../docs/standard/language-independence-and-language-independent-components.md) (CLS), no debe comenzar con un carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="dcde7-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../../docs/standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="dcde7-105">Vea [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="dcde7-105">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="dcde7-106">Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad.</span><span class="sxs-lookup"><span data-stu-id="dcde7-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="dcde7-107">No hay ningún valor predeterminado para este parámetro y debe proporcionar un valor.</span><span class="sxs-lookup"><span data-stu-id="dcde7-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="dcde7-108">Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.</span><span class="sxs-lookup"><span data-stu-id="dcde7-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="dcde7-109">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="dcde7-109">By default, this message is a warning.</span></span> <span data-ttu-id="dcde7-110">Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="dcde7-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="dcde7-111">**Id. de error:** BC40039</span><span class="sxs-lookup"><span data-stu-id="dcde7-111">**Error ID:** BC40039</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="dcde7-112">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="dcde7-112">To correct this error</span></span>  
  
-   <span data-ttu-id="dcde7-113">Si necesita conformidad con CLS, cambie el nombre del espacio de nombres raíz para que ninguno de sus elementos comienza con un carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="dcde7-113">If you require CLS compliance, change the root namespace name so that none of its elements begins with an underscore.</span></span>  
  
-   <span data-ttu-id="dcde7-114">Si necesita que el espacio de nombres permanecen sin cambios, a continuación, quite el <xref:System.CLSCompliantAttribute> desde el ensamblado o márquelo como `<CLSCompliant(False)>`.</span><span class="sxs-lookup"><span data-stu-id="dcde7-114">If you require that the namespace name remain unchanged, then remove the <xref:System.CLSCompliantAttribute> from the assembly or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcde7-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="dcde7-115">See Also</span></span>  
 [<span data-ttu-id="dcde7-116">Namespace (instrucción)</span><span class="sxs-lookup"><span data-stu-id="dcde7-116">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="dcde7-117">Espacios de nombres en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dcde7-117">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="dcde7-118">/rootnamespace</span><span class="sxs-lookup"><span data-stu-id="dcde7-118">/rootnamespace</span></span>](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)  
 [<span data-ttu-id="dcde7-119">Página de aplicación, Diseñador de proyectos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dcde7-119">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)  
 [<span data-ttu-id="dcde7-120">Nombres de elementos declarados</span><span class="sxs-lookup"><span data-stu-id="dcde7-120">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="dcde7-121">Convenciones de nomenclatura de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dcde7-121">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [<span data-ttu-id="dcde7-122">\<PAVE sobre > escribir código conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="dcde7-122">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)

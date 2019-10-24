---
title: El nombre <namespacename> del espacio de nombres raíz <fullnamespacename> no es compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- vbc40039
- bc40039
helpviewer_keywords:
- BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
ms.openlocfilehash: 821044d3ee359a052fa6a763e9c5a89da5d6f607
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775583"
---
# <a name="name-namespacename-in-the-root-namespace-fullnamespacename-is-not-cls-compliant"></a><span data-ttu-id="e902b-102">Nombre \<namespacename > en el espacio de nombres raíz \<fullnamespacename > no es conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="e902b-102">Name \<namespacename> in the root namespace \<fullnamespacename> is not CLS-compliant</span></span>
<span data-ttu-id="e902b-103">Un ensamblado se marca como `<CLSCompliant(True)>`, pero un elemento del nombre del espacio de nombres raíz comienza con un carácter de subrayado (`_`).</span><span class="sxs-lookup"><span data-stu-id="e902b-103">An assembly is marked as `<CLSCompliant(True)>`, but an element of the root namespace name begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="e902b-104">Un elemento de programación puede contener uno o más guiones bajos, pero para que sea compatible con la [independencia del lenguaje y los componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS), no debe comenzar con un carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="e902b-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="e902b-105">Vea [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="e902b-105">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="e902b-106">Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad.</span><span class="sxs-lookup"><span data-stu-id="e902b-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="e902b-107">No hay ningún valor predeterminado para este parámetro, por lo que debe proporcionar uno.</span><span class="sxs-lookup"><span data-stu-id="e902b-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="e902b-108">Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.</span><span class="sxs-lookup"><span data-stu-id="e902b-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="e902b-109">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="e902b-109">By default, this message is a warning.</span></span> <span data-ttu-id="e902b-110">Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="e902b-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="e902b-111">**Identificador de error:** BC40039</span><span class="sxs-lookup"><span data-stu-id="e902b-111">**Error ID:** BC40039</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e902b-112">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="e902b-112">To correct this error</span></span>  
  
- <span data-ttu-id="e902b-113">Si requiere la conformidad con CLS, cambie el nombre del espacio de nombres raíz para que ninguno de sus elementos comience con un carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="e902b-113">If you require CLS compliance, change the root namespace name so that none of its elements begins with an underscore.</span></span>  
  
- <span data-ttu-id="e902b-114">Si requiere que el nombre del espacio de nombres permanezca inalterado, quite el <xref:System.CLSCompliantAttribute> del ensamblado o márquelo como `<CLSCompliant(False)>`.</span><span class="sxs-lookup"><span data-stu-id="e902b-114">If you require that the namespace name remain unchanged, then remove the <xref:System.CLSCompliantAttribute> from the assembly or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e902b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e902b-115">See also</span></span>

- [<span data-ttu-id="e902b-116">Namespace (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e902b-116">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="e902b-117">Espacios de nombres en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e902b-117">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="e902b-118">-rootnamespace</span><span class="sxs-lookup"><span data-stu-id="e902b-118">-rootnamespace</span></span>](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)
- [<span data-ttu-id="e902b-119">Página de aplicación, Diseñador de proyectos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e902b-119">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [<span data-ttu-id="e902b-120">Nombres de elementos declarados</span><span class="sxs-lookup"><span data-stu-id="e902b-120">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="e902b-121">Convenciones de nomenclatura de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e902b-121">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)

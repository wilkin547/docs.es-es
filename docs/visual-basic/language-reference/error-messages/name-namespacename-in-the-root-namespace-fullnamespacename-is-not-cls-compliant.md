---
title: El nombre <namespacename> del espacio de nombres raíz <fullnamespacename> no es compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- vbc40039
- bc40039
helpviewer_keywords:
- BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
ms.openlocfilehash: faed46eaf21513945ef4eb0c76d36780e960d380
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592023"
---
# <a name="name-namespacename-in-the-root-namespace-fullnamespacename-is-not-cls-compliant"></a><span data-ttu-id="2823f-102">Nombre \<namespacename > en el espacio de nombres raíz \<fullnamespacename > no es conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="2823f-102">Name \<namespacename> in the root namespace \<fullnamespacename> is not CLS-compliant</span></span>
<span data-ttu-id="2823f-103">Un ensamblado está marcado como `<CLSCompliant(True)>`, pero un elemento del nombre de espacio de nombres raíz comienza con un carácter de subrayado (`_`).</span><span class="sxs-lookup"><span data-stu-id="2823f-103">An assembly is marked as `<CLSCompliant(True)>`, but an element of the root namespace name begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="2823f-104">Un elemento de programación puede contener uno o más caracteres de subrayado, pero to sea compatible con la [independencia del lenguaje y componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS), no debe comenzar con un carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="2823f-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="2823f-105">Vea [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="2823f-105">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="2823f-106">Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad.</span><span class="sxs-lookup"><span data-stu-id="2823f-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="2823f-107">No hay ningún valor predeterminado para este parámetro, por lo que debe proporcionar uno.</span><span class="sxs-lookup"><span data-stu-id="2823f-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="2823f-108">Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.</span><span class="sxs-lookup"><span data-stu-id="2823f-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="2823f-109">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="2823f-109">By default, this message is a warning.</span></span> <span data-ttu-id="2823f-110">Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="2823f-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="2823f-111">**Identificador de error:** BC40039</span><span class="sxs-lookup"><span data-stu-id="2823f-111">**Error ID:** BC40039</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2823f-112">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="2823f-112">To correct this error</span></span>  
  
- <span data-ttu-id="2823f-113">Si requiere conformidad con CLS, cambie el nombre del espacio de nombres raíz para que ninguno de sus elementos comienza con un carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="2823f-113">If you require CLS compliance, change the root namespace name so that none of its elements begins with an underscore.</span></span>  
  
- <span data-ttu-id="2823f-114">Si necesita que el espacio de nombres permanecen sin cambios, a continuación, quite el <xref:System.CLSCompliantAttribute> desde el ensamblado o márquelo como `<CLSCompliant(False)>`.</span><span class="sxs-lookup"><span data-stu-id="2823f-114">If you require that the namespace name remain unchanged, then remove the <xref:System.CLSCompliantAttribute> from the assembly or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2823f-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="2823f-115">See also</span></span>

- [<span data-ttu-id="2823f-116">Namespace (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2823f-116">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="2823f-117">Espacios de nombres en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2823f-117">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="2823f-118">/rootnamespace</span><span class="sxs-lookup"><span data-stu-id="2823f-118">/rootnamespace</span></span>](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)
- [<span data-ttu-id="2823f-119">Página de aplicación, Diseñador de proyectos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2823f-119">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [<span data-ttu-id="2823f-120">Nombres de elementos declarados</span><span class="sxs-lookup"><span data-stu-id="2823f-120">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="2823f-121">Convenciones de nomenclatura de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2823f-121">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)

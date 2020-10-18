---
title: El nombre <namespacename> del espacio de nombres raíz <fullnamespacename> no es compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- vbc40039
- bc40039
helpviewer_keywords:
- BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
ms.openlocfilehash: 48e020cb74641279a4f402e47034514d78dfc4fc
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160215"
---
# <a name="bc40039-name-namespacename-in-the-root-namespace-fullnamespacename-is-not-cls-compliant"></a><span data-ttu-id="51b85-102">BC40039: el nombre del \<namespacename> espacio de nombres raíz \<fullnamespacename> no es conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="51b85-102">BC40039: Name \<namespacename> in the root namespace \<fullnamespacename> is not CLS-compliant</span></span>

<span data-ttu-id="51b85-103">Un ensamblado está marcado como `<CLSCompliant(True)>` , pero un elemento del nombre del espacio de nombres raíz comienza con un carácter de subrayado ( `_` ).</span><span class="sxs-lookup"><span data-stu-id="51b85-103">An assembly is marked as `<CLSCompliant(True)>`, but an element of the root namespace name begins with an underscore (`_`).</span></span>

 <span data-ttu-id="51b85-104">Un elemento de programación puede contener uno o más subrayados, pero para ser compatible con la [independencia del lenguaje y los componentes de Language-Independent](../../../standard/language-independence-and-language-independent-components.md) (CLS), no debe comenzar con un carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="51b85-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="51b85-105">Vea [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="51b85-105">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

 <span data-ttu-id="51b85-106">Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad.</span><span class="sxs-lookup"><span data-stu-id="51b85-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="51b85-107">No hay ningún valor predeterminado para este parámetro, por lo que debe proporcionar uno.</span><span class="sxs-lookup"><span data-stu-id="51b85-107">There is no default for this parameter, and you must supply a value.</span></span>

 <span data-ttu-id="51b85-108">Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.</span><span class="sxs-lookup"><span data-stu-id="51b85-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>

 <span data-ttu-id="51b85-109">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="51b85-109">By default, this message is a warning.</span></span> <span data-ttu-id="51b85-110">Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="51b85-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="51b85-111">**Identificador de error:** BC40039</span><span class="sxs-lookup"><span data-stu-id="51b85-111">**Error ID:** BC40039</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="51b85-112">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="51b85-112">To correct this error</span></span>

- <span data-ttu-id="51b85-113">Si requiere la conformidad con CLS, cambie el nombre del espacio de nombres raíz para que ninguno de sus elementos comience con un carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="51b85-113">If you require CLS compliance, change the root namespace name so that none of its elements begins with an underscore.</span></span>

- <span data-ttu-id="51b85-114">Si requiere que el nombre del espacio de nombres permanezca inalterado, quite el del <xref:System.CLSCompliantAttribute> ensamblado o márquelo como `<CLSCompliant(False)>` .</span><span class="sxs-lookup"><span data-stu-id="51b85-114">If you require that the namespace name remain unchanged, then remove the <xref:System.CLSCompliantAttribute> from the assembly or mark it as `<CLSCompliant(False)>`.</span></span>

## <a name="see-also"></a><span data-ttu-id="51b85-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="51b85-115">See also</span></span>

- [<span data-ttu-id="51b85-116">Namespace (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="51b85-116">Namespace Statement</span></span>](../statements/namespace-statement.md)
- [<span data-ttu-id="51b85-117">Espacios de nombres en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="51b85-117">Namespaces in Visual Basic</span></span>](../../programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="51b85-118">-rootnamespace</span><span class="sxs-lookup"><span data-stu-id="51b85-118">-rootnamespace</span></span>](../../reference/command-line-compiler/rootnamespace.md)
- [<span data-ttu-id="51b85-119">Página de aplicación, Diseñador de proyectos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51b85-119">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [<span data-ttu-id="51b85-120">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="51b85-120">Declared Element Names</span></span>](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="51b85-121">Convenciones de nomenclatura de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="51b85-121">Visual Basic Naming Conventions</span></span>](../../programming-guide/program-structure/naming-conventions.md)

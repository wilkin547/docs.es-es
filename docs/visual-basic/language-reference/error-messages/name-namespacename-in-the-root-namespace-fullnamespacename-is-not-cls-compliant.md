---
description: 'Más información sobre: BC40039: el nombre del <namespacename> espacio de nombres raíz <fullnamespacename> no es conforme a CLS'
title: El nombre <namespacename> del espacio de nombres raíz <fullnamespacename> no es compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- vbc40039
- bc40039
helpviewer_keywords:
- BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
ms.openlocfilehash: 2560c5c056c70909a08a48a0ff8b2859b178cc8a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795734"
---
# <a name="bc40039-name-namespacename-in-the-root-namespace-fullnamespacename-is-not-cls-compliant"></a><span data-ttu-id="0f486-103">BC40039: el nombre del \<namespacename> espacio de nombres raíz \<fullnamespacename> no es conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="0f486-103">BC40039: Name \<namespacename> in the root namespace \<fullnamespacename> is not CLS-compliant</span></span>

<span data-ttu-id="0f486-104">Un ensamblado está marcado como `<CLSCompliant(True)>` , pero un elemento del nombre del espacio de nombres raíz comienza con un carácter de subrayado ( `_` ).</span><span class="sxs-lookup"><span data-stu-id="0f486-104">An assembly is marked as `<CLSCompliant(True)>`, but an element of the root namespace name begins with an underscore (`_`).</span></span>

 <span data-ttu-id="0f486-105">Un elemento de programación puede contener uno o más subrayados, pero para ser compatible con la [independencia del lenguaje y los componentes de Language-Independent](../../../standard/language-independence-and-language-independent-components.md) (CLS), no debe comenzar con un carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="0f486-105">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="0f486-106">Vea [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="0f486-106">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

 <span data-ttu-id="0f486-107">Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad.</span><span class="sxs-lookup"><span data-stu-id="0f486-107">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="0f486-108">No hay ningún valor predeterminado para este parámetro, por lo que debe proporcionar uno.</span><span class="sxs-lookup"><span data-stu-id="0f486-108">There is no default for this parameter, and you must supply a value.</span></span>

 <span data-ttu-id="0f486-109">Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.</span><span class="sxs-lookup"><span data-stu-id="0f486-109">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>

 <span data-ttu-id="0f486-110">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="0f486-110">By default, this message is a warning.</span></span> <span data-ttu-id="0f486-111">Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="0f486-111">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="0f486-112">**Identificador de error:** BC40039</span><span class="sxs-lookup"><span data-stu-id="0f486-112">**Error ID:** BC40039</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="0f486-113">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="0f486-113">To correct this error</span></span>

- <span data-ttu-id="0f486-114">Si requiere la conformidad con CLS, cambie el nombre del espacio de nombres raíz para que ninguno de sus elementos comience con un carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="0f486-114">If you require CLS compliance, change the root namespace name so that none of its elements begins with an underscore.</span></span>

- <span data-ttu-id="0f486-115">Si requiere que el nombre del espacio de nombres permanezca inalterado, quite el del <xref:System.CLSCompliantAttribute> ensamblado o márquelo como `<CLSCompliant(False)>` .</span><span class="sxs-lookup"><span data-stu-id="0f486-115">If you require that the namespace name remain unchanged, then remove the <xref:System.CLSCompliantAttribute> from the assembly or mark it as `<CLSCompliant(False)>`.</span></span>

## <a name="see-also"></a><span data-ttu-id="0f486-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f486-116">See also</span></span>

- [<span data-ttu-id="0f486-117">Namespace (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="0f486-117">Namespace Statement</span></span>](../statements/namespace-statement.md)
- [<span data-ttu-id="0f486-118">Espacios de nombres en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0f486-118">Namespaces in Visual Basic</span></span>](../../programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="0f486-119">-rootnamespace</span><span class="sxs-lookup"><span data-stu-id="0f486-119">-rootnamespace</span></span>](../../reference/command-line-compiler/rootnamespace.md)
- [<span data-ttu-id="0f486-120">Página de aplicación, Diseñador de proyectos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f486-120">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [<span data-ttu-id="0f486-121">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="0f486-121">Declared Element Names</span></span>](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="0f486-122">Convenciones de nomenclatura de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0f486-122">Visual Basic Naming Conventions</span></span>](../../programming-guide/program-structure/naming-conventions.md)

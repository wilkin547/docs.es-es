---
description: 'Más información sobre: BC40031: el nombre <membername> no es conforme a CLS'
title: El nombre <membername> no es compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
ms.openlocfilehash: 7abc4aee8bb468b523e5bdd2ac13947d19c926bc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795760"
---
# <a name="bc40031-name-membername-is-not-cls-compliant"></a><span data-ttu-id="c9af7-103">BC40031: el nombre \<membername> no es conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="c9af7-103">BC40031: Name \<membername> is not CLS-compliant</span></span>

<span data-ttu-id="c9af7-104">Un ensamblado se marca como `<CLSCompliant(True)>` pero expone un miembro con un nombre que comienza con un carácter de subrayado ( `_` ).</span><span class="sxs-lookup"><span data-stu-id="c9af7-104">An assembly is marked as `<CLSCompliant(True)>` but exposes a member with a name that begins with an underscore (`_`).</span></span>

 <span data-ttu-id="c9af7-105">Un elemento de programación puede contener uno o más subrayados, pero para ser compatible con la [independencia del lenguaje y los componentes de Language-Independent](../../../standard/language-independence-and-language-independent-components.md) (CLS), no debe comenzar con un carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="c9af7-105">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="c9af7-106">Vea [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="c9af7-106">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

 <span data-ttu-id="c9af7-107">Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad.</span><span class="sxs-lookup"><span data-stu-id="c9af7-107">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="c9af7-108">No hay ningún valor predeterminado para este parámetro, por lo que debe proporcionar uno.</span><span class="sxs-lookup"><span data-stu-id="c9af7-108">There is no default for this parameter, and you must supply a value.</span></span>

 <span data-ttu-id="c9af7-109">Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.</span><span class="sxs-lookup"><span data-stu-id="c9af7-109">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>

 <span data-ttu-id="c9af7-110">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="c9af7-110">By default, this message is a warning.</span></span> <span data-ttu-id="c9af7-111">Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="c9af7-111">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="c9af7-112">**Identificador de error:** BC40031</span><span class="sxs-lookup"><span data-stu-id="c9af7-112">**Error ID:** BC40031</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="c9af7-113">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="c9af7-113">To correct this error</span></span>

- <span data-ttu-id="c9af7-114">Si tiene control sobre el código fuente, cambie el nombre del miembro para que no comience por un carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="c9af7-114">If you have control over the source code, change the member name so that it does not begin with an underscore.</span></span>

- <span data-ttu-id="c9af7-115">Si necesita que el nombre de miembro permanezca inalterado, quite el <xref:System.CLSCompliantAttribute> de su definición o márquelo como `<CLSCompliant(False)>` .</span><span class="sxs-lookup"><span data-stu-id="c9af7-115">If you require that the member name remain unchanged, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span> <span data-ttu-id="c9af7-116">Todavía puede marcar el ensamblado como `<CLSCompliant(True)>` .</span><span class="sxs-lookup"><span data-stu-id="c9af7-116">You can still mark the assembly as `<CLSCompliant(True)>`.</span></span>

## <a name="see-also"></a><span data-ttu-id="c9af7-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9af7-117">See also</span></span>

- [<span data-ttu-id="c9af7-118">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="c9af7-118">Declared Element Names</span></span>](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="c9af7-119">Convenciones de nomenclatura de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c9af7-119">Visual Basic Naming Conventions</span></span>](../../programming-guide/program-structure/naming-conventions.md)

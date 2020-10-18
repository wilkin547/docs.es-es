---
title: <membername> no compatible con CLS no se permite en una interfaz compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
ms.openlocfilehash: aa7944e90857436553435ce783c0820770496a49
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159994"
---
# <a name="bc40033-non-cls-compliant-membername-is-not-allowed-in-a-cls-compliant-interface"></a><span data-ttu-id="db3fb-102">BC40033: no conforme a CLS \<membername> no se permite en una interfaz conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="db3fb-102">BC40033: Non-CLS-compliant \<membername> is not allowed in a CLS-compliant interface</span></span>

<span data-ttu-id="db3fb-103">Una propiedad, un procedimiento o un evento de una interfaz se marca como `<CLSCompliant(True)>` cuando la propia interfaz está marcada como `<CLSCompliant(False)>` o no está marcada.</span><span class="sxs-lookup"><span data-stu-id="db3fb-103">A property, procedure, or event in an interface is marked as `<CLSCompliant(True)>` when the interface itself is marked as `<CLSCompliant(False)>` or is not marked.</span></span>

 <span data-ttu-id="db3fb-104">Para que una interfaz sea compatible con la [independencia del lenguaje y los componentes de Language-Independent](../../../standard/language-independence-and-language-independent-components.md) (CLS), todos sus miembros deben ser conformes.</span><span class="sxs-lookup"><span data-stu-id="db3fb-104">For an interface to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), all its members must be compliant.</span></span>

 <span data-ttu-id="db3fb-105">Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad.</span><span class="sxs-lookup"><span data-stu-id="db3fb-105">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="db3fb-106">No hay ningún valor predeterminado para este parámetro, por lo que debe proporcionar uno.</span><span class="sxs-lookup"><span data-stu-id="db3fb-106">There is no default for this parameter, and you must supply a value.</span></span>

 <span data-ttu-id="db3fb-107">Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.</span><span class="sxs-lookup"><span data-stu-id="db3fb-107">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>

 <span data-ttu-id="db3fb-108">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="db3fb-108">By default, this message is a warning.</span></span> <span data-ttu-id="db3fb-109">Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="db3fb-109">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="db3fb-110">**Identificador de error:** BC40033</span><span class="sxs-lookup"><span data-stu-id="db3fb-110">**Error ID:** BC40033</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="db3fb-111">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="db3fb-111">To correct this error</span></span>

- <span data-ttu-id="db3fb-112">Si requiere la conformidad con CLS y tiene control sobre el código fuente de la interfaz, marque la interfaz como `<CLSCompliant(True)>` si todos sus miembros son conformes.</span><span class="sxs-lookup"><span data-stu-id="db3fb-112">If you require CLS compliance and have control over the interface source code, mark the interface as `<CLSCompliant(True)>` if all its members are compliant.</span></span>

- <span data-ttu-id="db3fb-113">Si requiere conformidad con CLS y no tiene control sobre el código fuente de la interfaz, o si no cumple los requisitos, defina este miembro dentro de una interfaz diferente.</span><span class="sxs-lookup"><span data-stu-id="db3fb-113">If you require CLS compliance and do not have control over the interface source code, or if it does not qualify to be compliant, define this member within a different interface.</span></span>

- <span data-ttu-id="db3fb-114">Si requiere que este miembro permanezca dentro de su interfaz actual, quite el <xref:System.CLSCompliantAttribute> de su definición o márquelo como `<CLSCompliant(False)>` .</span><span class="sxs-lookup"><span data-stu-id="db3fb-114">If you require that this member remain within its current interface, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span>

## <a name="see-also"></a><span data-ttu-id="db3fb-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="db3fb-115">See also</span></span>

- [<span data-ttu-id="db3fb-116">Instrucción Interface</span><span class="sxs-lookup"><span data-stu-id="db3fb-116">Interface Statement</span></span>](../statements/interface-statement.md)

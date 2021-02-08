---
description: 'Más información sobre: BC40033: no conforme a CLS <membername> no se permite en una interfaz conforme a CLS'
title: <membername> no compatible con CLS no se permite en una interfaz compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
ms.openlocfilehash: 070b56a8bf9df930de5bb5e363a9b157fcdc7ad7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795643"
---
# <a name="bc40033-non-cls-compliant-membername-is-not-allowed-in-a-cls-compliant-interface"></a><span data-ttu-id="e99d4-103">BC40033: no conforme a CLS \<membername> no se permite en una interfaz conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="e99d4-103">BC40033: Non-CLS-compliant \<membername> is not allowed in a CLS-compliant interface</span></span>

<span data-ttu-id="e99d4-104">Una propiedad, un procedimiento o un evento de una interfaz se marca como `<CLSCompliant(True)>` cuando la propia interfaz está marcada como `<CLSCompliant(False)>` o no está marcada.</span><span class="sxs-lookup"><span data-stu-id="e99d4-104">A property, procedure, or event in an interface is marked as `<CLSCompliant(True)>` when the interface itself is marked as `<CLSCompliant(False)>` or is not marked.</span></span>

 <span data-ttu-id="e99d4-105">Para que una interfaz sea compatible con la [independencia del lenguaje y los componentes de Language-Independent](../../../standard/language-independence-and-language-independent-components.md) (CLS), todos sus miembros deben ser conformes.</span><span class="sxs-lookup"><span data-stu-id="e99d4-105">For an interface to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), all its members must be compliant.</span></span>

 <span data-ttu-id="e99d4-106">Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad.</span><span class="sxs-lookup"><span data-stu-id="e99d4-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="e99d4-107">No hay ningún valor predeterminado para este parámetro, por lo que debe proporcionar uno.</span><span class="sxs-lookup"><span data-stu-id="e99d4-107">There is no default for this parameter, and you must supply a value.</span></span>

 <span data-ttu-id="e99d4-108">Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.</span><span class="sxs-lookup"><span data-stu-id="e99d4-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>

 <span data-ttu-id="e99d4-109">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="e99d4-109">By default, this message is a warning.</span></span> <span data-ttu-id="e99d4-110">Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="e99d4-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="e99d4-111">**Identificador de error:** BC40033</span><span class="sxs-lookup"><span data-stu-id="e99d4-111">**Error ID:** BC40033</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="e99d4-112">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="e99d4-112">To correct this error</span></span>

- <span data-ttu-id="e99d4-113">Si requiere la conformidad con CLS y tiene control sobre el código fuente de la interfaz, marque la interfaz como `<CLSCompliant(True)>` si todos sus miembros son conformes.</span><span class="sxs-lookup"><span data-stu-id="e99d4-113">If you require CLS compliance and have control over the interface source code, mark the interface as `<CLSCompliant(True)>` if all its members are compliant.</span></span>

- <span data-ttu-id="e99d4-114">Si requiere conformidad con CLS y no tiene control sobre el código fuente de la interfaz, o si no cumple los requisitos, defina este miembro dentro de una interfaz diferente.</span><span class="sxs-lookup"><span data-stu-id="e99d4-114">If you require CLS compliance and do not have control over the interface source code, or if it does not qualify to be compliant, define this member within a different interface.</span></span>

- <span data-ttu-id="e99d4-115">Si requiere que este miembro permanezca dentro de su interfaz actual, quite el <xref:System.CLSCompliantAttribute> de su definición o márquelo como `<CLSCompliant(False)>` .</span><span class="sxs-lookup"><span data-stu-id="e99d4-115">If you require that this member remain within its current interface, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span>

## <a name="see-also"></a><span data-ttu-id="e99d4-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e99d4-116">See also</span></span>

- [<span data-ttu-id="e99d4-117">Instrucción Interface</span><span class="sxs-lookup"><span data-stu-id="e99d4-117">Interface Statement</span></span>](../statements/interface-statement.md)

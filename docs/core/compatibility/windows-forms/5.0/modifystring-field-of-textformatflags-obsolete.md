---
title: 'Cambio importante: TextFormatFlags.ModifyString está obsoleto'
description: Obtenga información sobre el cambio importante en .NET 5 donde el campo TextFormatFlags.ModifyString está obsoleto como una advertencia.
ms.date: 11/05/2020
ms.openlocfilehash: 9fe1e04b1ad36070b08af2affdca1e058ec74bb8
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256171"
---
# <a name="textformatflagsmodifystring-is-obsolete"></a><span data-ttu-id="f1d73-103">TextFormatFlags.ModifyString está obsoleto</span><span class="sxs-lookup"><span data-stu-id="f1d73-103">TextFormatFlags.ModifyString is obsolete</span></span>

<span data-ttu-id="f1d73-104">El campo <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> está obsoleto, como advertencia, y es posible que se quite en una versión futura de .NET.</span><span class="sxs-lookup"><span data-stu-id="f1d73-104">The <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> field is obsolete, as a warning, and may be removed in a future .NET version.</span></span>

## <a name="change-description"></a><span data-ttu-id="f1d73-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="f1d73-105">Change description</span></span>

<span data-ttu-id="f1d73-106">En versiones anteriores de .NET, el campo de enumeración <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> no está marcado como obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f1d73-106">In previous .NET versions, the <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> enumeration field is not marked obsolete.</span></span> <span data-ttu-id="f1d73-107">En .NET 5 y versiones posteriores, está marcado como obsoleto como advertencia.</span><span class="sxs-lookup"><span data-stu-id="f1d73-107">In .NET 5 and later versions, it is marked obsolete as a warning.</span></span> <span data-ttu-id="f1d73-108">Es posible que este campo se quite en una versión futura de .NET.</span><span class="sxs-lookup"><span data-stu-id="f1d73-108">This field may be removed in a future .NET version.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="f1d73-109">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="f1d73-109">Reason for change</span></span>

<span data-ttu-id="f1d73-110">Pasar una cadena a <xref:System.Windows.Forms.TextRenderer.MeasureText%2A?displayProperty=nameWithType> con <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> modifica la cadena en algunas situaciones.</span><span class="sxs-lookup"><span data-stu-id="f1d73-110">Passing a string to <xref:System.Windows.Forms.TextRenderer.MeasureText%2A?displayProperty=nameWithType> with <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> alters the string in some situations.</span></span> <span data-ttu-id="f1d73-111">Este comportamiento incumple la promesa de inmutabilidad de la cadena y puede provocar daños graves en el estado del entorno de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="f1d73-111">This behavior breaks the string immutability promise and may lead to a fatal .NET runtime state corruption.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="f1d73-112">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="f1d73-112">Version introduced</span></span>

<span data-ttu-id="f1d73-113">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="f1d73-113">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="f1d73-114">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="f1d73-114">Recommended action</span></span>

<span data-ttu-id="f1d73-115">Actualice cualquier código que se base en <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f1d73-115">Update any code that relies on <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType>.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="f1d73-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="f1d73-116">Affected APIs</span></span>

- <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=fullName>

<!--

### Affected APIs

- `F:System.Windows.Forms.TextFormatFlags.ModifyString`

### Category

Windows Forms

-->

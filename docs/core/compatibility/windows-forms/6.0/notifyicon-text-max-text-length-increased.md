---
title: 'Cambio importante: Longitud máxima de texto de NotifyIcon.Text aumentada'
description: Obtenga información sobre el cambio importante de.NET 6.0 que provoca un aumento de la longitud máxima del texto de la propiedad NotifyIcon.Text.
ms.date: 01/19/2021
ms.openlocfilehash: 0029556f3ec2795fb079575b329e7fbd187d486f
ms.sourcegitcommit: 632818f4b527e5bf3c48fc04e0c7f3b4bdb8a248
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2021
ms.locfileid: "98617982"
---
# <a name="notifyicontext-maximum-text-length-increased"></a><span data-ttu-id="d320f-103">Longitud máxima de texto de NotifyIcon.Text aumentada</span><span class="sxs-lookup"><span data-stu-id="d320f-103">NotifyIcon.Text maximum text length increased</span></span>

<span data-ttu-id="d320f-104">La longitud máxima de texto permitida para la propiedad <xref:System.Windows.Forms.NotifyIcon.Text?displayProperty=nameWithType> aumentó de 63 a 127.</span><span class="sxs-lookup"><span data-stu-id="d320f-104">The maximum text length allowed for the <xref:System.Windows.Forms.NotifyIcon.Text?displayProperty=nameWithType> property increased from 63 to 127.</span></span>

## <a name="change-description"></a><span data-ttu-id="d320f-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="d320f-105">Change description</span></span>

<span data-ttu-id="d320f-106">En versiones anteriores de .NET, la longitud de texto máxima permitida para la propiedad <xref:System.Windows.Forms.NotifyIcon.Text?displayProperty=nameWithType> era de 63 caracteres.</span><span class="sxs-lookup"><span data-stu-id="d320f-106">In previous .NET versions, the maximum text length allowed for the <xref:System.Windows.Forms.NotifyIcon.Text?displayProperty=nameWithType> property is 63 characters.</span></span> <span data-ttu-id="d320f-107">A partir de .NET 6.0, la longitud máxima permitida del texto es de 127 caracteres.</span><span class="sxs-lookup"><span data-stu-id="d320f-107">Starting in .NET 6.0, the maximum allowed text length is 127 characters.</span></span> <span data-ttu-id="d320f-108">En cualquier versión, se produce una excepción <xref:System.ArgumentException> cuando se intenta establecer un valor que supera el límite.</span><span class="sxs-lookup"><span data-stu-id="d320f-108">In any version, an <xref:System.ArgumentException> is thrown when you attempt to set a value that's longer than the limit.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="d320f-109">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="d320f-109">Reason for change</span></span>

<span data-ttu-id="d320f-110">La longitud máxima permitida del texto se ha incrementado en consonancia con la [API subyacente de Windows](/windows/win32/api/shellapi/ns-shellapi-notifyicondataw#nif_showtip-0x00000080).</span><span class="sxs-lookup"><span data-stu-id="d320f-110">The maximum allowed text length was increased to be in line with the [underlying Windows API](/windows/win32/api/shellapi/ns-shellapi-notifyicondataw#nif_showtip-0x00000080).</span></span> <span data-ttu-id="d320f-111">La API de Windows se actualizó en Windows 2000, pero, debido a problemas de compatibilidad, el límite de tamaño de esta propiedad no se ha actualizado en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d320f-111">The Windows API was updated in Windows 2000, but due to compatibility reasons, the size limit for this property wasn't updated in .NET Framework.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="d320f-112">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="d320f-112">Version introduced</span></span>

<span data-ttu-id="d320f-113">.NET 6.0 (versión preliminar 1)</span><span class="sxs-lookup"><span data-stu-id="d320f-113">.NET 6.0 Preview 1</span></span>

## <a name="recommended-action"></a><span data-ttu-id="d320f-114">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="d320f-114">Recommended action</span></span>

<span data-ttu-id="d320f-115">Revise el código y modifique las condiciones de protección existentes, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="d320f-115">Review your code and relax any existing guard conditions, if necessary.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="d320f-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="d320f-116">Affected APIs</span></span>

<xref:System.Windows.Forms.NotifyIcon.Text?displayProperty=fullName>

<!--

### Affected APIs

- `P:System.Windows.Forms.NotifyIcon.Text`

### Category

Windows Forms

-->

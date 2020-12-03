---
title: 'Cambio importante: Cambio del valor FeedbackSize predeterminado para las instancias creadas por TripleDES.Create'
description: Obtenga información sobre el cambio importante en .NET 5.0, donde el valor predeterminado de la propiedad FeedbackSize en la instancia de TripleDES devuelta desde TripleDES.Create() ha cambiado de 64 a 8.
ms.date: 10/16/2020
ms.openlocfilehash: 4179da17bf2e5cc5fcc7d64d83ba92119f912042
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760224"
---
# <a name="default-feedbacksize-value-for-instances-created-by-tripledescreate-changed"></a><span data-ttu-id="d2cf2-103">Cambio del valor FeedbackSize predeterminado para las instancias creadas por TripleDES.Create</span><span class="sxs-lookup"><span data-stu-id="d2cf2-103">Default FeedbackSize value for instances created by TripleDES.Create changed</span></span>

<span data-ttu-id="d2cf2-104">El valor predeterminado de la propiedad <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize?displayProperty=nameWithType> en la instancia de <xref:System.Security.Cryptography.TripleDES> devuelta desde <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType> ha cambiado de 64 a 8 para facilitar la migración de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-104">The default value for the <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize?displayProperty=nameWithType> property on the <xref:System.Security.Cryptography.TripleDES> instance returned from <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType> has changed from 64 to 8 to make migration from .NET Framework easier.</span></span> <span data-ttu-id="d2cf2-105">Esta propiedad, a menos que se use directamente en el código del autor de la llamada, solo se utiliza cuando la propiedad <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode> es <xref:System.Security.Cryptography.CipherMode.CFB?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-105">This property, unless used directly in caller code, is used only when the <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode> property is <xref:System.Security.Cryptography.CipherMode.CFB?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="d2cf2-106">La compatibilidad con el modo <xref:System.Security.Cryptography.CipherMode.CFB> se agregó por primera vez a .NET para la versión 5.0 RC1, por lo que solo las aplicaciones de .NET 5.0 RC1 y .NET 5.0 RC2 se verán afectadas por este cambio.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-106">Support for the <xref:System.Security.Cryptography.CipherMode.CFB> mode was first added to .NET for the 5.0 RC1 release, so only .NET 5.0 RC1 and .NET 5.0 RC2 applications should be impacted by this change.</span></span>

## <a name="change-description"></a><span data-ttu-id="d2cf2-107">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="d2cf2-107">Change description</span></span>

<span data-ttu-id="d2cf2-108">En .NET Core y versiones preliminares anteriores de .NET 5.0, `TripleDES.Create().FeedbackSize` tiene un valor predeterminado de 64.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-108">In .NET Core and previous pre-release versions of .NET 5.0, `TripleDES.Create().FeedbackSize` has a default value of 64.</span></span> <span data-ttu-id="d2cf2-109">A partir de la versión RTM de .NET 5.0, `TripleDES.Create().FeedbackSize` tiene un valor predeterminado de 8.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-109">Starting in the RTM version of .NET 5.0, `TripleDES.Create().FeedbackSize` has a default value of 8.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="d2cf2-110">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="d2cf2-110">Reason for change</span></span>

<span data-ttu-id="d2cf2-111">En .NET Framework, la clase base <xref:System.Security.Cryptography.TripleDES> establece de forma predeterminada el valor de <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> en 64, pero la clase <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider> lo sobrescribe en 8.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-111">In .NET Framework, the <xref:System.Security.Cryptography.TripleDES> base class defaults the value of <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> to 64, but the <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider> class overwrites the default to 8.</span></span> <span data-ttu-id="d2cf2-112">Cuando la propiedad <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> se agregó a .NET Core en la versión 2.0, se conservó este mismo comportamiento.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-112">When the <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> property was introduced to .NET Core in version 2.0, this same behavior was preserved.</span></span> <span data-ttu-id="d2cf2-113">Pero en .NET Framework, <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType> devuelve una instancia de <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider>, por lo que el valor predeterminado del generador de algoritmos es 8.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-113">However, in .NET Framework, <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType> returns an instance of <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider>, so the default value from the algorithm factory is 8.</span></span> <span data-ttu-id="d2cf2-114">En .NET Core, y .NET 5 y versiones posteriores, el generador de algoritmos devuelve una implementación no pública que, hasta ahora, ha tenido un valor predeterminado de 64.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-114">For .NET Core and .NET 5+, the algorithm factory returns a non-public implementation, which, until now, had a default value of 64.</span></span>

<span data-ttu-id="d2cf2-115">Al cambiar el valor <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> de la clase de implementación <xref:System.Security.Cryptography.TripleDES> a 8, las aplicaciones escritas para .NET Framework en las que se ha especificado el modo de cifrado como <xref:System.Security.Cryptography.CipherMode.CFB>, pero en las que no se ha asignado explícitamente la propiedad <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>, pueden seguir funcionando en .NET 5.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-115">Changing the <xref:System.Security.Cryptography.TripleDES> implementation class' <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> value to 8 allows for applications written for .NET Framework that specified the cipher mode as <xref:System.Security.Cryptography.CipherMode.CFB> but didn't explicitly assign the <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> property, to continue to function on .NET 5.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="d2cf2-116">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="d2cf2-116">Version introduced</span></span>

<span data-ttu-id="d2cf2-117">5.0</span><span class="sxs-lookup"><span data-stu-id="d2cf2-117">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="d2cf2-118">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="d2cf2-118">Recommended action</span></span>

<span data-ttu-id="d2cf2-119">Las aplicaciones que cifran o descifran datos en las versiones RC1 o RC2 de .NET 5.0 lo hacen con CFB64, cuando se cumplen las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="d2cf2-119">Applications that encrypt or decrypt data in the RC1 or RC2 versions of .NET 5.0 do so with CFB64, when the following conditions are met:</span></span>

- <span data-ttu-id="d2cf2-120">Con una instancia de <xref:System.Security.Cryptography.TripleDES> a partir de <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-120">With a <xref:System.Security.Cryptography.TripleDES> instance from <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="d2cf2-121">Con el valor predeterminado para <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-121">Using the default value for <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>.</span></span>
- <span data-ttu-id="d2cf2-122">Con la propiedad <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode> establecida en <xref:System.Security.Cryptography.CipherMode.CFB?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-122">With the <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode> property set to <xref:System.Security.Cryptography.CipherMode.CFB?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="d2cf2-123">Para mantener este comportamiento, asigne la propiedad <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> a `64`.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-123">To maintain this behavior, assign the <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> property to `64`.</span></span>

<span data-ttu-id="d2cf2-124">No todas las implementaciones de `TripleDES` usan el mismo valor predeterminado para <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-124">Not all `TripleDES` implementations use the same default for <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>.</span></span> <span data-ttu-id="d2cf2-125">Se recomienda que, si usa el modo de cifrado <xref:System.Security.Cryptography.CipherMode.CFB> en las instancias de <xref:System.Security.Cryptography.TripleDES>, siempre asigne de forma explícita el valor de la propiedad <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-125">We recommend that if you use the <xref:System.Security.Cryptography.CipherMode.CFB> cipher mode on <xref:System.Security.Cryptography.TripleDES> instances, you should always explicitly assign the <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> property value.</span></span>

```csharp
TripleDES cipher = TripleDES.Create();
cipher.Mode = CipherMode.CFB;
// Explicitly set the FeedbackSize for CFB to control between CFB8 and CFB64.
cipher.FeedbackSize = 8;
```

## <a name="affected-apis"></a><span data-ttu-id="d2cf2-126">API afectadas</span><span class="sxs-lookup"><span data-stu-id="d2cf2-126">Affected APIs</span></span>

- <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Security.Cryptography.TripleDES.Create`
- `P:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize`

### Category

- Cryptography

-->

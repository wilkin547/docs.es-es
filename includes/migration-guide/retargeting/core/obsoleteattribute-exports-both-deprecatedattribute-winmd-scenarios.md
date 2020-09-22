---
ms.openlocfilehash: 7d7424b3ca0d295022999e95ed9862b5226b6220
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606349"
---
### <a name="obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a><span data-ttu-id="e5eb5-101">ObsoleteAttribute se exporta como ObsoleteAttribute y DeprecatedAttribute en escenarios de WinMD</span><span class="sxs-lookup"><span data-stu-id="e5eb5-101">ObsoleteAttribute exports as both ObsoleteAttribute and DeprecatedAttribute in WinMD scenarios</span></span>

#### <a name="details"></a><span data-ttu-id="e5eb5-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="e5eb5-102">Details</span></span>

<span data-ttu-id="e5eb5-103">Cuando se crea una biblioteca de metadatos de Windows (archivo .winmd), el atributo <xref:System.ObsoleteAttribute?displayProperty=fullName> se exporta como <xref:System.ObsoleteAttribute?displayProperty=fullName> y como [Windows.Foundation.DeprecatedAttribute](/uwp/api/windows.foundation.metadata.deprecatedattribute).</span><span class="sxs-lookup"><span data-stu-id="e5eb5-103">When you create a Windows Metadata library (.winmd file), the <xref:System.ObsoleteAttribute?displayProperty=fullName> attribute is exported as both <xref:System.ObsoleteAttribute?displayProperty=fullName> and [Windows.Foundation.DeprecatedAttribute](/uwp/api/windows.foundation.metadata.deprecatedattribute).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e5eb5-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="e5eb5-104">Suggestion</span></span>

<span data-ttu-id="e5eb5-105">Volver a compilar el código fuente existente que usa el atributo <xref:System.ObsoleteAttribute?displayProperty=fullName> puede generar advertencias cuando ese código se usa desde C++/CX o JavaScript. No se recomienda aplicar <xref:System.ObsoleteAttribute?displayProperty=fullName> y [Windows.Foundation.DeprecatedAttribute](/uwp/api/windows.foundation.metadata.deprecatedattribute) al código en los ensamblados administrados; se podrían producir advertencias de compilación.</span><span class="sxs-lookup"><span data-stu-id="e5eb5-105">Recompilation of existing source code that uses the <xref:System.ObsoleteAttribute?displayProperty=fullName> attribute may generate warnings when consuming that code from C++/CX or JavaScript.We do not recommend applying both <xref:System.ObsoleteAttribute?displayProperty=fullName> and [Windows.Foundation.DeprecatedAttribute](/uwp/api/windows.foundation.metadata.deprecatedattribute) to code in managed assemblies; it may result in build warnings.</span></span>

| <span data-ttu-id="e5eb5-106">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="e5eb5-106">Name</span></span>    | <span data-ttu-id="e5eb5-107">Valor</span><span class="sxs-lookup"><span data-stu-id="e5eb5-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e5eb5-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="e5eb5-108">Scope</span></span>   | <span data-ttu-id="e5eb5-109">Borde</span><span class="sxs-lookup"><span data-stu-id="e5eb5-109">Edge</span></span>        |
| <span data-ttu-id="e5eb5-110">Versión</span><span class="sxs-lookup"><span data-stu-id="e5eb5-110">Version</span></span> | <span data-ttu-id="e5eb5-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="e5eb5-111">4.5.1</span></span>       |
| <span data-ttu-id="e5eb5-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="e5eb5-112">Type</span></span>    | <span data-ttu-id="e5eb5-113">Redestinación</span><span class="sxs-lookup"><span data-stu-id="e5eb5-113">Retargeting</span></span> |

---
ms.openlocfilehash: 424e8ff704b888aa3d2c1254ac712da4034f59b8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616116"
---
### <a name="obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a><span data-ttu-id="9877b-101">ObsoleteAttribute se exporta como ObsoleteAttribute y DeprecatedAttribute en escenarios de WinMD</span><span class="sxs-lookup"><span data-stu-id="9877b-101">ObsoleteAttribute exports as both ObsoleteAttribute and DeprecatedAttribute in WinMD scenarios</span></span>

#### <a name="details"></a><span data-ttu-id="9877b-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="9877b-102">Details</span></span>

<span data-ttu-id="9877b-103">Cuando se crea una biblioteca de metadatos de Windows (archivo .winmd), el atributo <xref:System.ObsoleteAttribute?displayProperty=fullName> se exporta como <xref:System.ObsoleteAttribute?displayProperty=fullName> y como [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute).</span><span class="sxs-lookup"><span data-stu-id="9877b-103">When you create a Windows Metadata library (.winmd file), the <xref:System.ObsoleteAttribute?displayProperty=fullName> attribute is exported as both <xref:System.ObsoleteAttribute?displayProperty=fullName> and [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9877b-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="9877b-104">Suggestion</span></span>

<span data-ttu-id="9877b-105">Volver a compilar el código fuente existente que usa el atributo <xref:System.ObsoleteAttribute?displayProperty=fullName> puede generar advertencias cuando ese código se usa desde C++/CX o JavaScript. No se recomienda aplicar <xref:System.ObsoleteAttribute?displayProperty=fullName> y [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) al código en los ensamblados administrados; se podrían producir advertencias de compilación.</span><span class="sxs-lookup"><span data-stu-id="9877b-105">Recompilation of existing source code that uses the <xref:System.ObsoleteAttribute?displayProperty=fullName> attribute may generate warnings when consuming that code from C++/CX or JavaScript.We do not recommend applying both <xref:System.ObsoleteAttribute?displayProperty=fullName> and [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) to code in managed assemblies; it may result in build warnings.</span></span>

| <span data-ttu-id="9877b-106">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="9877b-106">Name</span></span>    | <span data-ttu-id="9877b-107">Valor</span><span class="sxs-lookup"><span data-stu-id="9877b-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9877b-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="9877b-108">Scope</span></span>   | <span data-ttu-id="9877b-109">Borde</span><span class="sxs-lookup"><span data-stu-id="9877b-109">Edge</span></span>        |
| <span data-ttu-id="9877b-110">Versión</span><span class="sxs-lookup"><span data-stu-id="9877b-110">Version</span></span> | <span data-ttu-id="9877b-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="9877b-111">4.5.1</span></span>       |
| <span data-ttu-id="9877b-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="9877b-112">Type</span></span>    | <span data-ttu-id="9877b-113">Redestinación</span><span class="sxs-lookup"><span data-stu-id="9877b-113">Retargeting</span></span> |

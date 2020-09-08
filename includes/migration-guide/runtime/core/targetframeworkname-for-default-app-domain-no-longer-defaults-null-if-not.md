---
ms.openlocfilehash: 4e685722271a8079e727ea9c2e0e501f68b30fc9
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497226"
---
### <a name="targetframeworkname-for-default-app-domain-no-longer-defaults-to-null-if-not-set"></a><span data-ttu-id="18654-101">TargetFrameworkName para el dominio de aplicación predeterminado ya no tiene un valor NULL como valor predeterminado si no se establece</span><span class="sxs-lookup"><span data-stu-id="18654-101">TargetFrameworkName for default app domain no longer defaults to null if not set</span></span>

#### <a name="details"></a><span data-ttu-id="18654-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="18654-102">Details</span></span>

<span data-ttu-id="18654-103"><xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> anteriormente tenía un valor NULL en el dominio de aplicación predeterminado, a menos que se estableciera de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="18654-103">The <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> was previously null in the default app domain, unless it was explicitly set.</span></span> <span data-ttu-id="18654-104">A partir de la versión 4.6, la propiedad <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> del dominio de aplicación predeterminado tendrá un valor predeterminado derivado del elemento TargetFrameworkAttribute (si hay alguno presente).</span><span class="sxs-lookup"><span data-stu-id="18654-104">Beginning in 4.6, the <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> property for the default app domain will have a default value derived from the TargetFrameworkAttribute (if one is present).</span></span> <span data-ttu-id="18654-105">Los dominios de aplicación no predeterminados continuarán heredando su propiedad <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> del dominio de aplicación predeterminado (que no tendrá un valor NULL como valor predeterminado en la versión 4.6) a menos que se invalide de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="18654-105">Non-default app domains will continue to inherit their <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> from the default app domain (which will not default to null in 4.6) unless it is explicitly overridden.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="18654-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="18654-106">Suggestion</span></span>

<span data-ttu-id="18654-107">El código debería actualizarse para no depender de que <xref:System.AppDomainSetup.TargetFrameworkName> establezca un valor nulo como valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="18654-107">Code should be updated to not depend on <xref:System.AppDomainSetup.TargetFrameworkName> defaulting to null.</span></span> <span data-ttu-id="18654-108">Si es necesario que esta propiedad continúe evaluándose como un valor nulo, puede establecerse en dicho valor de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="18654-108">If it is required that this property continue to evaluate to null, it can be explicitly set to that value.</span></span>

| <span data-ttu-id="18654-109">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="18654-109">Name</span></span>    | <span data-ttu-id="18654-110">Valor</span><span class="sxs-lookup"><span data-stu-id="18654-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="18654-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="18654-111">Scope</span></span>   |<span data-ttu-id="18654-112">Borde</span><span class="sxs-lookup"><span data-stu-id="18654-112">Edge</span></span>|
|<span data-ttu-id="18654-113">Versión</span><span class="sxs-lookup"><span data-stu-id="18654-113">Version</span></span>|<span data-ttu-id="18654-114">4.6</span><span class="sxs-lookup"><span data-stu-id="18654-114">4.6</span></span>|
|<span data-ttu-id="18654-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="18654-115">Type</span></span>|<span data-ttu-id="18654-116">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="18654-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="18654-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="18654-117">Affected APIs</span></span>

- <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.AppDomainSetup.TargetFrameworkName`

-->

---
ms.openlocfilehash: 26c50ac8b0e570e31a38b1913f73acbe21fae08b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497652"
---
### <a name="appdomainsetupdynamicbase-is-no-longer-randomized-by-userandomizedstringhashalgorithm"></a><span data-ttu-id="6b1f0-101">AppDomainSetup.DynamicBase ya no es aleatorio debido a UseRandomizedStringHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="6b1f0-101">AppDomainSetup.DynamicBase is no longer randomized by UseRandomizedStringHashAlgorithm</span></span>

#### <a name="details"></a><span data-ttu-id="6b1f0-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="6b1f0-102">Details</span></span>

<span data-ttu-id="6b1f0-103">Antes de .NET Framework 4.6, el valor de <xref:System.AppDomainSetup.DynamicBase> era aleatorio entre los dominios de aplicación, o bien entre los procesos si UseRandomizedStringHashAlgorithm estaba habilitado en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6b1f0-103">Prior to the .NET Framework 4.6, the value of <xref:System.AppDomainSetup.DynamicBase> would be randomized between application domains, or between processes, if UseRandomizedStringHashAlgorithm was enabled in the app's config file.</span></span> <span data-ttu-id="6b1f0-104">A partir de .NET Framework 4.6, <xref:System.AppDomainSetup.DynamicBase> devolverá un resultado estable entre otras instancias de una aplicación en ejecución y entre otros dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="6b1f0-104">Beginning in the .NET Framework 4.6, <xref:System.AppDomainSetup.DynamicBase> will return a stable result between different instances of an app running, and between different app domains.</span></span> <span data-ttu-id="6b1f0-105">Las bases dinámicas seguirán siendo diferentes para cada aplicación; este cambio solo quita el elemento de nomenclatura aleatorio para otras instancias de la misma aplicación.</span><span class="sxs-lookup"><span data-stu-id="6b1f0-105">Dynamic bases will still differ for different apps; this change only removes the random naming element for different instances of the same app.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6b1f0-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="6b1f0-106">Suggestion</span></span>

<span data-ttu-id="6b1f0-107">Tenga en cuenta que habilitar <code>UseRandomizedStringHashAlgorithm</code> no dará como resultado que <xref:System.AppDomainSetup.DynamicBase> sea aleatorio.</span><span class="sxs-lookup"><span data-stu-id="6b1f0-107">Be aware that enabling <code>UseRandomizedStringHashAlgorithm</code> will not result in <xref:System.AppDomainSetup.DynamicBase> being randomized.</span></span> <span data-ttu-id="6b1f0-108">Si se necesita una base aleatoria, se debe generar en el código de la aplicación, en lugar de hacerlo a través de esta API.</span><span class="sxs-lookup"><span data-stu-id="6b1f0-108">If a random base is needed, it must be produced in your app's code rather than via this API.</span></span>

| <span data-ttu-id="6b1f0-109">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="6b1f0-109">Name</span></span>    | <span data-ttu-id="6b1f0-110">Valor</span><span class="sxs-lookup"><span data-stu-id="6b1f0-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6b1f0-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="6b1f0-111">Scope</span></span>   |<span data-ttu-id="6b1f0-112">Borde</span><span class="sxs-lookup"><span data-stu-id="6b1f0-112">Edge</span></span>|
|<span data-ttu-id="6b1f0-113">Versión</span><span class="sxs-lookup"><span data-stu-id="6b1f0-113">Version</span></span>|<span data-ttu-id="6b1f0-114">4.6</span><span class="sxs-lookup"><span data-stu-id="6b1f0-114">4.6</span></span>|
|<span data-ttu-id="6b1f0-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="6b1f0-115">Type</span></span>|<span data-ttu-id="6b1f0-116">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="6b1f0-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="6b1f0-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="6b1f0-117">Affected APIs</span></span>

- <xref:System.AppDomainSetup.DynamicBase?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.AppDomainSetup.DynamicBase`

-->

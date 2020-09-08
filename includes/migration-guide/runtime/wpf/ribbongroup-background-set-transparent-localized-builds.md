---
ms.openlocfilehash: d6405573e476ce18513938b500041adefbeeef1b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496841"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a><span data-ttu-id="1071e-101">El fondo de RibbonGroup se establece en transparente en las compilaciones localizadas</span><span class="sxs-lookup"><span data-stu-id="1071e-101">RibbonGroup background is set to transparent in localized builds</span></span>

#### <a name="details"></a><span data-ttu-id="1071e-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="1071e-102">Details</span></span>

<span data-ttu-id="1071e-103">El fondo de <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> en las compilaciones localizadas siempre se pinta con el pincel transparente, lo que produce una experiencia de interfaz de usuario deficiente.</span><span class="sxs-lookup"><span data-stu-id="1071e-103"><xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> background on localized builds was always painted with Transparent brush, resulting in poor UI experience.</span></span> <span data-ttu-id="1071e-104">Esto se corrigió en WPF en .NET Framework 4.7 mediante la actualización de los recursos localizados para <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> lo que, a su vez, garantiza que se seleccione el pincel correcto.</span><span class="sxs-lookup"><span data-stu-id="1071e-104">This is fixed in .NET Framework 4.7 WPF fix by updating the localized resources for <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName>, which in turn ensures that the correct brush is selected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1071e-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="1071e-105">Suggestion</span></span>

<span data-ttu-id="1071e-106">Actualizar a .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="1071e-106">Upgrade to .NET Framework 4.7</span></span>

| <span data-ttu-id="1071e-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="1071e-107">Name</span></span>    | <span data-ttu-id="1071e-108">Valor</span><span class="sxs-lookup"><span data-stu-id="1071e-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1071e-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="1071e-109">Scope</span></span>   |<span data-ttu-id="1071e-110">Borde</span><span class="sxs-lookup"><span data-stu-id="1071e-110">Edge</span></span>|
|<span data-ttu-id="1071e-111">Versión</span><span class="sxs-lookup"><span data-stu-id="1071e-111">Version</span></span>|<span data-ttu-id="1071e-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="1071e-112">4.6.2</span></span>|
|<span data-ttu-id="1071e-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="1071e-113">Type</span></span>|<span data-ttu-id="1071e-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="1071e-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="1071e-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="1071e-115">Affected APIs</span></span>

<span data-ttu-id="1071e-116">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="1071e-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->

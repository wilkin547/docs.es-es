---
ms.openlocfilehash: a3ba42868577ac20ea2e082f90fc4973a1bfe108
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622382"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a><span data-ttu-id="28ab3-101">El fondo de RibbonGroup se establece en transparente en las compilaciones localizadas</span><span class="sxs-lookup"><span data-stu-id="28ab3-101">RibbonGroup background is set to transparent in localized builds</span></span>

#### <a name="details"></a><span data-ttu-id="28ab3-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="28ab3-102">Details</span></span>

<span data-ttu-id="28ab3-103">El fondo de <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> en las compilaciones localizadas siempre se pinta con el pincel transparente, lo que produce una experiencia de interfaz de usuario deficiente.</span><span class="sxs-lookup"><span data-stu-id="28ab3-103"><xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> background on localized builds was always painted with Transparent brush, resulting in poor UI experience.</span></span> <span data-ttu-id="28ab3-104">Esto se corrigió en WPF en .NET Framework 4.7 mediante la actualización de los recursos localizados para <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> lo que, a su vez, garantiza que se seleccione el pincel correcto.</span><span class="sxs-lookup"><span data-stu-id="28ab3-104">This is fixed in .NET Framework 4.7 WPF fix by updating the localized resources for <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName>, which in turn ensures that the correct brush is selected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="28ab3-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="28ab3-105">Suggestion</span></span>

<span data-ttu-id="28ab3-106">Actualizar a .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="28ab3-106">Upgrade to .NET Framework 4.7</span></span>

| <span data-ttu-id="28ab3-107">Nombre</span><span class="sxs-lookup"><span data-stu-id="28ab3-107">Name</span></span>    | <span data-ttu-id="28ab3-108">Valor</span><span class="sxs-lookup"><span data-stu-id="28ab3-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="28ab3-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="28ab3-109">Scope</span></span>   |<span data-ttu-id="28ab3-110">Borde</span><span class="sxs-lookup"><span data-stu-id="28ab3-110">Edge</span></span>|
|<span data-ttu-id="28ab3-111">Versión</span><span class="sxs-lookup"><span data-stu-id="28ab3-111">Version</span></span>|<span data-ttu-id="28ab3-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="28ab3-112">4.6.2</span></span>|
|<span data-ttu-id="28ab3-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="28ab3-113">Type</span></span>|<span data-ttu-id="28ab3-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="28ab3-114">Runtime</span></span>|

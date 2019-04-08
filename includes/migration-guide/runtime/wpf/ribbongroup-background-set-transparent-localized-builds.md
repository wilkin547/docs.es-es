---
ms.openlocfilehash: 9500907c6a1ba5b27008dcad4c9b47aef9092106
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760684"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a><span data-ttu-id="049d5-101">El fondo de RibbonGroup se establece en transparente en las compilaciones localizadas</span><span class="sxs-lookup"><span data-stu-id="049d5-101">RibbonGroup background is set to transparent in localized builds</span></span>

|   |   |
|---|---|
|<span data-ttu-id="049d5-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="049d5-102">Details</span></span>|<span data-ttu-id="049d5-103">El fondo de <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> en las compilaciones localizadas siempre se pinta con el pincel transparente, lo que produce una experiencia de interfaz de usuario deficiente.</span><span class="sxs-lookup"><span data-stu-id="049d5-103"><xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> background on localized builds was always painted with Transparent brush, resulting in poor UI experience.</span></span> <span data-ttu-id="049d5-104">Esto se corrigió en WPF en .NET Framework 4.7 mediante la actualización de los recursos localizados para <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> lo que, a su vez, garantiza que se seleccione el pincel correcto.</span><span class="sxs-lookup"><span data-stu-id="049d5-104">This is fixed in .NET Framework 4.7 WPF fix by updating the localized resources for <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>, which in turn ensures that the correct brush is selected.</span></span>|
|<span data-ttu-id="049d5-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="049d5-105">Suggestion</span></span>|<span data-ttu-id="049d5-106">Actualizar a .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="049d5-106">Upgrade to .NET Framework 4.7</span></span>|
|<span data-ttu-id="049d5-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="049d5-107">Scope</span></span>|<span data-ttu-id="049d5-108">Borde</span><span class="sxs-lookup"><span data-stu-id="049d5-108">Edge</span></span>|
|<span data-ttu-id="049d5-109">Versión</span><span class="sxs-lookup"><span data-stu-id="049d5-109">Version</span></span>|<span data-ttu-id="049d5-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="049d5-110">4.6.2</span></span>|
|<span data-ttu-id="049d5-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="049d5-111">Type</span></span>|<span data-ttu-id="049d5-112">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="049d5-112">Runtime</span></span>|


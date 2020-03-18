---
ms.openlocfilehash: 921baed7381fad363cc832c6b6af69068c2c8f43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802458"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a><span data-ttu-id="16262-101">El fondo de RibbonGroup se establece en transparente en las compilaciones localizadas</span><span class="sxs-lookup"><span data-stu-id="16262-101">RibbonGroup background is set to transparent in localized builds</span></span>

|   |   |
|---|---|
|<span data-ttu-id="16262-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="16262-102">Details</span></span>|<span data-ttu-id="16262-103">El fondo de <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> en las compilaciones localizadas siempre se pinta con el pincel transparente, lo que produce una experiencia de interfaz de usuario deficiente.</span><span class="sxs-lookup"><span data-stu-id="16262-103"><xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> background on localized builds was always painted with Transparent brush, resulting in poor UI experience.</span></span> <span data-ttu-id="16262-104">Esto se corrigió en WPF en .NET Framework 4.7 mediante la actualización de los recursos localizados para <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> lo que, a su vez, garantiza que se seleccione el pincel correcto.</span><span class="sxs-lookup"><span data-stu-id="16262-104">This is fixed in .NET Framework 4.7 WPF fix by updating the localized resources for <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>, which in turn ensures that the correct brush is selected.</span></span>|
|<span data-ttu-id="16262-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="16262-105">Suggestion</span></span>|<span data-ttu-id="16262-106">Actualizar a .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="16262-106">Upgrade to .NET Framework 4.7</span></span>|
|<span data-ttu-id="16262-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="16262-107">Scope</span></span>|<span data-ttu-id="16262-108">Borde</span><span class="sxs-lookup"><span data-stu-id="16262-108">Edge</span></span>|
|<span data-ttu-id="16262-109">Versión</span><span class="sxs-lookup"><span data-stu-id="16262-109">Version</span></span>|<span data-ttu-id="16262-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="16262-110">4.6.2</span></span>|
|<span data-ttu-id="16262-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="16262-111">Type</span></span>|<span data-ttu-id="16262-112">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="16262-112">Runtime</span></span>|

---
ms.openlocfilehash: 2e974d277d6659aaada321b2a7e7a604df78a7bd
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761325"
---
### <a name="wpf-windows-are-rendered-without-clipping-when-extending-outside-a-single-monitor"></a><span data-ttu-id="2aee3-101">Las ventanas de WPF se representan sin recortes al ampliarse fuera de un monitor</span><span class="sxs-lookup"><span data-stu-id="2aee3-101">WPF windows are rendered without clipping when extending outside a single monitor</span></span>

|   |   |
|---|---|
|<span data-ttu-id="2aee3-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="2aee3-102">Details</span></span>|<span data-ttu-id="2aee3-103">En .NET Framework 4.6 ejecutado en Windows 8 y versiones posteriores, se representa toda la ventana sin recortes cuando se amplía más allá de una única pantalla en un escenario de varios monitores.</span><span class="sxs-lookup"><span data-stu-id="2aee3-103">In the .NET Framework 4.6 running on Windows 8 and above, the entire window is rendered without clipping when it extends outside of single display in a multi-monitor scenario.</span></span> <span data-ttu-id="2aee3-104">Esto es diferente de las versiones anteriores de .NET Framework, en las que se recortaban las ventanas de WPF que se ampliaban más allá de una pantalla.</span><span class="sxs-lookup"><span data-stu-id="2aee3-104">This is different from previous versions of the .NET Framework which would clip WPF windows that extended beyond a single display.</span></span>|
|<span data-ttu-id="2aee3-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="2aee3-105">Suggestion</span></span>|<span data-ttu-id="2aee3-106">Este comportamiento (si hay que recortar o no) se puede establecer de manera explícita mediante el elemento <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> de <code>&lt;appSettings&gt;</code> en el archivo de configuración de la aplicación, o bien estableciendo la propiedad <code>EnableMultiMonitorDisplayClipping</code> al inicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2aee3-106">This behavior (whether to clip or not) can be explicitly set using the <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> element in <code>&lt;appSettings&gt;</code> in an application's configuration file, or by setting the <code>EnableMultiMonitorDisplayClipping</code> property at app startup.</span></span>|
|<span data-ttu-id="2aee3-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="2aee3-107">Scope</span></span>|<span data-ttu-id="2aee3-108">Secundaria</span><span class="sxs-lookup"><span data-stu-id="2aee3-108">Minor</span></span>|
|<span data-ttu-id="2aee3-109">Versión</span><span class="sxs-lookup"><span data-stu-id="2aee3-109">Version</span></span>|<span data-ttu-id="2aee3-110">4.6</span><span class="sxs-lookup"><span data-stu-id="2aee3-110">4.6</span></span>|
|<span data-ttu-id="2aee3-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="2aee3-111">Type</span></span>|<span data-ttu-id="2aee3-112">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="2aee3-112">Runtime</span></span>|


---
ms.openlocfilehash: a133c2ea48df11915f8708029c70549e8a1ccefd
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496912"
---
### <a name="wpf-windows-are-rendered-without-clipping-when-extending-outside-a-single-monitor"></a><span data-ttu-id="09369-101">Las ventanas de WPF se representan sin recortes al ampliarse fuera de un monitor</span><span class="sxs-lookup"><span data-stu-id="09369-101">WPF windows are rendered without clipping when extending outside a single monitor</span></span>

#### <a name="details"></a><span data-ttu-id="09369-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="09369-102">Details</span></span>

<span data-ttu-id="09369-103">En .NET Framework 4.6 ejecutado en Windows 8 y versiones posteriores, se representa toda la ventana sin recortes cuando se amplía más allá de una única pantalla en un escenario de varios monitores.</span><span class="sxs-lookup"><span data-stu-id="09369-103">In the .NET Framework 4.6 running on Windows 8 and above, the entire window is rendered without clipping when it extends outside of single display in a multi-monitor scenario.</span></span> <span data-ttu-id="09369-104">Esto es diferente de las versiones anteriores de .NET Framework, en las que se recortaban las ventanas de WPF que se ampliaban más allá de una pantalla.</span><span class="sxs-lookup"><span data-stu-id="09369-104">This is different from previous versions of the .NET Framework which would clip WPF windows that extended beyond a single display.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="09369-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="09369-105">Suggestion</span></span>

<span data-ttu-id="09369-106">Este comportamiento (si hay que recortar o no) se puede establecer de manera explícita mediante el elemento <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> de <code>&lt;appSettings&gt;</code> en el archivo de configuración de la aplicación, o bien estableciendo la propiedad <code>EnableMultiMonitorDisplayClipping</code> al inicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="09369-106">This behavior (whether to clip or not) can be explicitly set using the <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> element in <code>&lt;appSettings&gt;</code> in an application's configuration file, or by setting the <code>EnableMultiMonitorDisplayClipping</code> property at app startup.</span></span>

| <span data-ttu-id="09369-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="09369-107">Name</span></span>    | <span data-ttu-id="09369-108">Valor</span><span class="sxs-lookup"><span data-stu-id="09369-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="09369-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="09369-109">Scope</span></span>   |<span data-ttu-id="09369-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="09369-110">Minor</span></span>|
|<span data-ttu-id="09369-111">Versión</span><span class="sxs-lookup"><span data-stu-id="09369-111">Version</span></span>|<span data-ttu-id="09369-112">4.6</span><span class="sxs-lookup"><span data-stu-id="09369-112">4.6</span></span>|
|<span data-ttu-id="09369-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="09369-113">Type</span></span>|<span data-ttu-id="09369-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="09369-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="09369-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="09369-115">Affected APIs</span></span>

<span data-ttu-id="09369-116">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="09369-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->

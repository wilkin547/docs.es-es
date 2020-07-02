---
ms.openlocfilehash: d276e2bbf24c8b2389a0a8078c62c327c3729d50
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621446"
---
### <a name="wpf-windows-are-rendered-without-clipping-when-extending-outside-a-single-monitor"></a><span data-ttu-id="bf704-101">Las ventanas de WPF se representan sin recortes al ampliarse fuera de un monitor</span><span class="sxs-lookup"><span data-stu-id="bf704-101">WPF windows are rendered without clipping when extending outside a single monitor</span></span>

#### <a name="details"></a><span data-ttu-id="bf704-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="bf704-102">Details</span></span>

<span data-ttu-id="bf704-103">En .NET Framework 4.6 ejecutado en Windows 8 y versiones posteriores, se representa toda la ventana sin recortes cuando se amplía más allá de una única pantalla en un escenario de varios monitores.</span><span class="sxs-lookup"><span data-stu-id="bf704-103">In the .NET Framework 4.6 running on Windows 8 and above, the entire window is rendered without clipping when it extends outside of single display in a multi-monitor scenario.</span></span> <span data-ttu-id="bf704-104">Esto es diferente de las versiones anteriores de .NET Framework, en las que se recortaban las ventanas de WPF que se ampliaban más allá de una pantalla.</span><span class="sxs-lookup"><span data-stu-id="bf704-104">This is different from previous versions of the .NET Framework which would clip WPF windows that extended beyond a single display.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="bf704-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="bf704-105">Suggestion</span></span>

<span data-ttu-id="bf704-106">Este comportamiento (si hay que recortar o no) se puede establecer de manera explícita mediante el elemento <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> de <code>&lt;appSettings&gt;</code> en el archivo de configuración de la aplicación, o bien estableciendo la propiedad <code>EnableMultiMonitorDisplayClipping</code> al inicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bf704-106">This behavior (whether to clip or not) can be explicitly set using the <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> element in <code>&lt;appSettings&gt;</code> in an application's configuration file, or by setting the <code>EnableMultiMonitorDisplayClipping</code> property at app startup.</span></span>

| <span data-ttu-id="bf704-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="bf704-107">Name</span></span>    | <span data-ttu-id="bf704-108">Valor</span><span class="sxs-lookup"><span data-stu-id="bf704-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="bf704-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="bf704-109">Scope</span></span>   |<span data-ttu-id="bf704-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="bf704-110">Minor</span></span>|
|<span data-ttu-id="bf704-111">Versión</span><span class="sxs-lookup"><span data-stu-id="bf704-111">Version</span></span>|<span data-ttu-id="bf704-112">4.6</span><span class="sxs-lookup"><span data-stu-id="bf704-112">4.6</span></span>|
|<span data-ttu-id="bf704-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="bf704-113">Type</span></span>|<span data-ttu-id="bf704-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="bf704-114">Runtime</span></span>|

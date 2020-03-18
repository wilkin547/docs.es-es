---
ms.openlocfilehash: e7154919d6a09a04e650d5546feb2ae6c6cc912f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859182"
---
### <a name="httpruntimeappdomainapppath-throws-a-nullreferenceexception"></a><span data-ttu-id="05278-101">HttpRuntime.AppDomainAppPath inicia una excepción NullReferenceException</span><span class="sxs-lookup"><span data-stu-id="05278-101">HttpRuntime.AppDomainAppPath Throws a NullReferenceException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="05278-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="05278-102">Details</span></span>|<span data-ttu-id="05278-103">En .NET Framework 4.6.2, el entorno de ejecución inicia una excepción <code>T:System.NullReferenceException</code> al recuperar un valor <code>P:System.Web.HttpRuntime.AppDomainAppPath</code> que incluye caracteres NULL. En .NET Framework 4.6.1 y versiones anteriores, el entorno de ejecución inicia una excepción <code>T:System.ArgumentNullException</code>.</span><span class="sxs-lookup"><span data-stu-id="05278-103">In the .NET Framework 4.6.2, the runtime throws a <code>T:System.NullReferenceException</code> when retrieving a <code>P:System.Web.HttpRuntime.AppDomainAppPath</code> value that includes null characters.In the .NET Framework 4.6.1 and earlier versions, the runtime throws an <code>T:System.ArgumentNullException</code>.</span></span>|
|<span data-ttu-id="05278-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="05278-104">Suggestion</span></span>|<span data-ttu-id="05278-105">Puede hacer lo siguiente para responder a este cambio:</span><span class="sxs-lookup"><span data-stu-id="05278-105">You can do either of the follow to respond to this change:</span></span><ul><li><span data-ttu-id="05278-106">Controle <code>T:System.NullReferenceException</code> si la aplicación se ejecuta en .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="05278-106">Handle the <code>T:System.NullReferenceException</code> if you application is running on the .NET Framework 4.6.2.</span></span></li><li><span data-ttu-id="05278-107">Actualice a .NET Framework 4.7, que restaura el comportamiento anterior e inicia una excepción <code>T:System.ArgumentNullException</code>.</span><span class="sxs-lookup"><span data-stu-id="05278-107">Upgrade to the .NET Framework 4.7, which restores the previous behavior and throws an <code>T:System.ArgumentNullException</code>.</span></span></li></ul>|
|<span data-ttu-id="05278-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="05278-108">Scope</span></span>|<span data-ttu-id="05278-109">Borde</span><span class="sxs-lookup"><span data-stu-id="05278-109">Edge</span></span>|
|<span data-ttu-id="05278-110">Versión</span><span class="sxs-lookup"><span data-stu-id="05278-110">Version</span></span>|<span data-ttu-id="05278-111">4.6.2</span><span class="sxs-lookup"><span data-stu-id="05278-111">4.6.2</span></span>|
|<span data-ttu-id="05278-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="05278-112">Type</span></span>|<span data-ttu-id="05278-113">Redestinación</span><span class="sxs-lookup"><span data-stu-id="05278-113">Retargeting</span></span>|
|<span data-ttu-id="05278-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="05278-114">Affected APIs</span></span>|<ul><li><xref:System.Web.HttpRuntime.AppDomainAppPath?displayProperty=nameWithType></li></ul>|

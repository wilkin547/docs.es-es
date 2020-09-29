---
ms.openlocfilehash: 9f5f238e3d4222af1da3a1713e1b3e65de6e6f49
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "91025150"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a><span data-ttu-id="b2c50-101">En PipeConnection.GetHashAlgorithm de WCF ahora se usa SHA256</span><span class="sxs-lookup"><span data-stu-id="b2c50-101">WCF PipeConnection.GetHashAlgorithm now uses SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="b2c50-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="b2c50-102">Details</span></span>

<span data-ttu-id="b2c50-103">A partir de .NET Framework 4.7.1, Windows Communication Foundation usa un código hash SHA256 para generar nombres aleatorios para las canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="b2c50-103">Starting with the .NET Framework 4.7.1, Windows Communication Foundation uses a SHA256 hash to generate random names for named pipes.</span></span> <span data-ttu-id="b2c50-104">En .NET Framework 4.7 y versiones anteriores, usaba un hash SHA1.</span><span class="sxs-lookup"><span data-stu-id="b2c50-104">In the .NET Framework 4.7 and earlier versions, it used a SHA1 hash.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b2c50-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="b2c50-105">Suggestion</span></span>

<span data-ttu-id="b2c50-106">Si tiene problemas de compatibilidad con este cambio en .NET Framework 4.7.1 o una versión posterior, puede excluirlo mediante la adición de la línea siguiente a la sección `<runtime>` del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="b2c50-106">If you run into compatibility issue with this change on the .NET Framework 4.7.1 or later, you can opt-out it by adding the following line to the `<runtime>` section of your app.config file:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="b2c50-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="b2c50-107">Name</span></span>    | <span data-ttu-id="b2c50-108">Valor</span><span class="sxs-lookup"><span data-stu-id="b2c50-108">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="b2c50-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="b2c50-109">Scope</span></span>   | <span data-ttu-id="b2c50-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="b2c50-110">Minor</span></span>   |
| <span data-ttu-id="b2c50-111">Versión</span><span class="sxs-lookup"><span data-stu-id="b2c50-111">Version</span></span> | <span data-ttu-id="b2c50-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="b2c50-112">4.7.1</span></span>   |
| <span data-ttu-id="b2c50-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="b2c50-113">Type</span></span>    | <span data-ttu-id="b2c50-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="b2c50-114">Runtime</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="b2c50-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="b2c50-115">Affected APIs</span></span>

<span data-ttu-id="b2c50-116">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="b2c50-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->

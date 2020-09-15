---
ms.openlocfilehash: c646372104457e8bc5d418744847f3ee771c8d8b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614802"
---
### <a name="wcf-message-security-now-is-able-to-use-tls11-and-tls12"></a><span data-ttu-id="d96ab-101">La seguridad de los mensajes de WCF ahora puede usar TLS1.1 y TLS1.2</span><span class="sxs-lookup"><span data-stu-id="d96ab-101">WCF message security now is able to use TLS1.1 and TLS1.2</span></span>

#### <a name="details"></a><span data-ttu-id="d96ab-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="d96ab-102">Details</span></span>

<span data-ttu-id="d96ab-103">A partir de .NET Framework 4.7, los clientes pueden configurar TLS1.1 o TLS1.2 en la seguridad de los mensajes de WCF además de SSL3.0 y TLS1.0 a través de ajustes de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d96ab-103">Starting in the .NET Framework 4.7, customers can configure either TLS1.1 or TLS1.2 in WCF message security in addition to SSL3.0 and TLS1.0 through application configuration settings.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d96ab-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="d96ab-104">Suggestion</span></span>

<span data-ttu-id="d96ab-105">En .NET Framework 4.7, la compatibilidad con TLS1.1 y TLS1.2 en la seguridad de los mensajes de WCF está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d96ab-105">In the .NET Framework 4.7, support for TLS1.1 and TLS1.2 in WCF message security is disabled by default.</span></span> <span data-ttu-id="d96ab-106">Se puede habilitar si se agrega la línea siguiente a la sección `<runtime>` del archivo app.config o web.config:</span><span class="sxs-lookup"><span data-stu-id="d96ab-106">You can enable it by adding the following line to the `<runtime>` section of the app.config or web.config file:</span></span>

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false" />
</runtime>
```

| <span data-ttu-id="d96ab-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="d96ab-107">Name</span></span>    | <span data-ttu-id="d96ab-108">Valor</span><span class="sxs-lookup"><span data-stu-id="d96ab-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d96ab-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="d96ab-109">Scope</span></span>   | <span data-ttu-id="d96ab-110">Borde</span><span class="sxs-lookup"><span data-stu-id="d96ab-110">Edge</span></span>        |
| <span data-ttu-id="d96ab-111">Versión</span><span class="sxs-lookup"><span data-stu-id="d96ab-111">Version</span></span> | <span data-ttu-id="d96ab-112">4.7</span><span class="sxs-lookup"><span data-stu-id="d96ab-112">4.7</span></span>         |
| <span data-ttu-id="d96ab-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="d96ab-113">Type</span></span>    | <span data-ttu-id="d96ab-114">Redestinación</span><span class="sxs-lookup"><span data-stu-id="d96ab-114">Retargeting</span></span> |

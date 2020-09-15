---
ms.openlocfilehash: 0e949cbdeda99dd7b94e919b903a21171a57f527
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614728"
---
### <a name="wcf-binding-with-the-transportwithmessagecredential-security-mode"></a><span data-ttu-id="bc427-101">Enlace de WCF con el modo de seguridad de TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="bc427-101">WCF binding with the TransportWithMessageCredential security mode</span></span>

#### <a name="details"></a><span data-ttu-id="bc427-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="bc427-102">Details</span></span>

<span data-ttu-id="bc427-103">A partir de .NET Framework 4.6.1, el enlace de WCF que usa el modo de seguridad de TransportWithMessageCredential se puede configurar para recibir mensajes con encabezados &quot;para&quot; sin firmar para las claves de seguridad asimétricas. De forma predeterminada, en .NET Framework 4.6.1 se seguirán rechazando los encabezados &quot;para&quot; sin firmar.</span><span class="sxs-lookup"><span data-stu-id="bc427-103">Beginning in the .NET Framework 4.6.1, WCF binding that uses the TransportWithMessageCredential security mode can be set up to receive messages with unsigned &quot;to&quot; headers for asymmetric security keys.By default, unsigned &quot;to&quot; headers will continue to be rejected in .NET Framework 4.6.1.</span></span> <span data-ttu-id="bc427-104">Solo se aceptarán si una aplicación incluye este modo de operación nuevo mediante el modificador de configuración Switch.System.ServiceModel.AllowUnsignedToHeader.</span><span class="sxs-lookup"><span data-stu-id="bc427-104">They will only be accepted if an application opts into this new mode of operation using the Switch.System.ServiceModel.AllowUnsignedToHeader configuration switch.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="bc427-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="bc427-105">Suggestion</span></span>

<span data-ttu-id="bc427-106">Como es una característica opcional, no debería afectar al comportamiento de las aplicaciones existentes.</span><span class="sxs-lookup"><span data-stu-id="bc427-106">Because this is an opt-in feature, it should not affect the behavior of existing apps.</span></span><br/><span data-ttu-id="bc427-107">Para controlar si se usa el comportamiento nuevo o no, use la opción de configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="bc427-107">To control whether the new behavior is used or not, use the following configuration setting:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.ServiceModel.AllowUnsignedToHeader=true" />
</runtime>
```

| <span data-ttu-id="bc427-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="bc427-108">Name</span></span>    | <span data-ttu-id="bc427-109">Valor</span><span class="sxs-lookup"><span data-stu-id="bc427-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="bc427-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="bc427-110">Scope</span></span>   | <span data-ttu-id="bc427-111">Transparente</span><span class="sxs-lookup"><span data-stu-id="bc427-111">Transparent</span></span> |
| <span data-ttu-id="bc427-112">Versión</span><span class="sxs-lookup"><span data-stu-id="bc427-112">Version</span></span> | <span data-ttu-id="bc427-113">4.6.1</span><span class="sxs-lookup"><span data-stu-id="bc427-113">4.6.1</span></span>       |
| <span data-ttu-id="bc427-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="bc427-114">Type</span></span>    | <span data-ttu-id="bc427-115">Redestinación</span><span class="sxs-lookup"><span data-stu-id="bc427-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="bc427-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="bc427-116">Affected APIs</span></span>

- <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpsSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.WSFederationHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>

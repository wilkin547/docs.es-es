---
ms.openlocfilehash: 7c0227980aa5d90f3788783088bcd7cd9509ed66
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770846"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a><span data-ttu-id="639ab-101">El valor predeterminado de MsmqSecureHashAlgorithm de WCF ahora es SHA256</span><span class="sxs-lookup"><span data-stu-id="639ab-101">WCF MsmqSecureHashAlgorithm default value is now SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="639ab-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="639ab-102">Details</span></span>

<span data-ttu-id="639ab-103">A partir de .NET Framework 4.7.1, el algoritmo de firma de mensajes predeterminado de WCF para los mensajes de Msmq es SHA256.</span><span class="sxs-lookup"><span data-stu-id="639ab-103">Starting with the .NET Framework 4.7.1, the default message signing algorithm in WCF for Msmq messages is SHA256.</span></span> <span data-ttu-id="639ab-104">En .NET Framework 4.7 y versiones anteriores, el algoritmo de firma de mensajes predeterminado es SHA1.</span><span class="sxs-lookup"><span data-stu-id="639ab-104">In the .NET Framework 4.7 and earlier versions, the default message signing algorithm is SHA1.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="639ab-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="639ab-105">Suggestion</span></span>

<span data-ttu-id="639ab-106">Si tiene problemas de compatibilidad con este cambio en .NET Framework 4.7.1 o una versión posterior, puede excluirlo mediante la adición de la línea siguiente a la sección `<runtime>` del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="639ab-106">If you run into compatibility issues with this change on the .NET Framework 4.7.1 or later, you can opt-out the change by adding the following line to the `<runtime>` section of your app.config file:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; />
  </runtime>
</configuration>
```

| <span data-ttu-id="639ab-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="639ab-107">Name</span></span>    | <span data-ttu-id="639ab-108">Valor</span><span class="sxs-lookup"><span data-stu-id="639ab-108">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="639ab-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="639ab-109">Scope</span></span>   | <span data-ttu-id="639ab-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="639ab-110">Minor</span></span>   |
| <span data-ttu-id="639ab-111">Versión</span><span class="sxs-lookup"><span data-stu-id="639ab-111">Version</span></span> | <span data-ttu-id="639ab-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="639ab-112">4.7.1</span></span>   |
| <span data-ttu-id="639ab-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="639ab-113">Type</span></span>    | <span data-ttu-id="639ab-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="639ab-114">Runtime</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="639ab-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="639ab-115">Affected APIs</span></span>

<span data-ttu-id="639ab-116">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="639ab-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->

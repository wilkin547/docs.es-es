---
ms.openlocfilehash: 986b647047aaa4a185c1403e96e499ae587bea98
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617550"
---
### <a name="httpruntimeappdomainapppath-throws-a-nullreferenceexception"></a><span data-ttu-id="4ef34-101">HttpRuntime.AppDomainAppPath inicia una excepción NullReferenceException</span><span class="sxs-lookup"><span data-stu-id="4ef34-101">HttpRuntime.AppDomainAppPath Throws a NullReferenceException</span></span>

#### <a name="details"></a><span data-ttu-id="4ef34-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="4ef34-102">Details</span></span>

<span data-ttu-id="4ef34-103">En .NET Framework 4.6.2, el entorno de ejecución inicia una excepción `T:System.NullReferenceException` al recuperar un valor `P:System.Web.HttpRuntime.AppDomainAppPath` que incluye caracteres NULL. En .NET Framework 4.6.1 y versiones anteriores, el entorno de ejecución inicia una excepción `T:System.ArgumentNullException`.</span><span class="sxs-lookup"><span data-stu-id="4ef34-103">In the .NET Framework 4.6.2, the runtime throws a `T:System.NullReferenceException` when retrieving a `P:System.Web.HttpRuntime.AppDomainAppPath` value that includes null characters.In the .NET Framework 4.6.1 and earlier versions, the runtime throws an `T:System.ArgumentNullException`.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4ef34-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="4ef34-104">Suggestion</span></span>

<span data-ttu-id="4ef34-105">Puede hacer lo siguiente para responder a este cambio:</span><span class="sxs-lookup"><span data-stu-id="4ef34-105">You can do either of the follow to respond to this change:</span></span>

- <span data-ttu-id="4ef34-106">Controle `T:System.NullReferenceException` si la aplicación se ejecuta en .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="4ef34-106">Handle the `T:System.NullReferenceException` if you application is running on the .NET Framework 4.6.2.</span></span>
- <span data-ttu-id="4ef34-107">Actualice a .NET Framework 4.7, que restaura el comportamiento anterior e inicia una excepción `T:System.ArgumentNullException`.</span><span class="sxs-lookup"><span data-stu-id="4ef34-107">Upgrade to the .NET Framework 4.7, which restores the previous behavior and throws an `T:System.ArgumentNullException`.</span></span>

| <span data-ttu-id="4ef34-108">Nombre</span><span class="sxs-lookup"><span data-stu-id="4ef34-108">Name</span></span>    | <span data-ttu-id="4ef34-109">Valor</span><span class="sxs-lookup"><span data-stu-id="4ef34-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4ef34-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="4ef34-110">Scope</span></span>   | <span data-ttu-id="4ef34-111">Borde</span><span class="sxs-lookup"><span data-stu-id="4ef34-111">Edge</span></span>        |
| <span data-ttu-id="4ef34-112">Versión</span><span class="sxs-lookup"><span data-stu-id="4ef34-112">Version</span></span> | <span data-ttu-id="4ef34-113">4.6.2</span><span class="sxs-lookup"><span data-stu-id="4ef34-113">4.6.2</span></span>       |
| <span data-ttu-id="4ef34-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="4ef34-114">Type</span></span>    | <span data-ttu-id="4ef34-115">Redestinación</span><span class="sxs-lookup"><span data-stu-id="4ef34-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="4ef34-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="4ef34-116">Affected APIs</span></span>

- <xref:System.Web.HttpRuntime.AppDomainAppPath?displayProperty=nameWithType>

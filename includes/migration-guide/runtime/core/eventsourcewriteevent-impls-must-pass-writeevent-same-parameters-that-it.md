---
ms.openlocfilehash: 99a7fa0fcfce6d490a182f85709b5dd0e0e8c86f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496750"
---
### <a name="eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a><span data-ttu-id="86a78-101">Las implementaciones EventSource.WriteEvent deben pasar a WriteEvent los mismos parámetros que recibió (además del identificador)</span><span class="sxs-lookup"><span data-stu-id="86a78-101">EventSource.WriteEvent impls must pass WriteEvent the same parameters that it received (plus ID)</span></span>

#### <a name="details"></a><span data-ttu-id="86a78-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="86a78-102">Details</span></span>

<span data-ttu-id="86a78-103">El runtime ahora aplica el contrato que especifica lo siguiente: una clase derivada de <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> que define un método de evento ETW debe llamar al método <code>EventSource.WriteEvent</code> de la clase base con el identificador de evento, seguido de los mismos argumentos que se pasaron al método de evento ETW.</span><span class="sxs-lookup"><span data-stu-id="86a78-103">The runtime now enforces the contract that specifies the following: A class derived from <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> that defines an ETW event method must call the base class <code>EventSource.WriteEvent</code> method with the event ID followed by the same arguments that the ETW event method was passed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="86a78-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="86a78-104">Suggestion</span></span>

<span data-ttu-id="86a78-105">Se produce una excepción <xref:System.IndexOutOfRangeException?displayProperty=fullName> si un objeto <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> lee datos <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> en proceso para un origen de eventos que infringe este contrato.</span><span class="sxs-lookup"><span data-stu-id="86a78-105">An <xref:System.IndexOutOfRangeException?displayProperty=fullName> exception is thrown if an <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> reads <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> data in process for an event source that violates this contract.</span></span>

| <span data-ttu-id="86a78-106">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="86a78-106">Name</span></span>    | <span data-ttu-id="86a78-107">Valor</span><span class="sxs-lookup"><span data-stu-id="86a78-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="86a78-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="86a78-108">Scope</span></span>   |<span data-ttu-id="86a78-109">Secundaria</span><span class="sxs-lookup"><span data-stu-id="86a78-109">Minor</span></span>|
|<span data-ttu-id="86a78-110">Versión</span><span class="sxs-lookup"><span data-stu-id="86a78-110">Version</span></span>|<span data-ttu-id="86a78-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="86a78-111">4.5.1</span></span>|
|<span data-ttu-id="86a78-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="86a78-112">Type</span></span>|<span data-ttu-id="86a78-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="86a78-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="86a78-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="86a78-114">Affected APIs</span></span>

<span data-ttu-id="86a78-115">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="86a78-115">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->

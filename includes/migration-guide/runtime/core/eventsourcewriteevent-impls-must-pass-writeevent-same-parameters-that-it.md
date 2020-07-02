---
ms.openlocfilehash: 662c140f019add66ff6605d47ad1f32c3f50d711
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620575"
---
### <a name="eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a><span data-ttu-id="69fba-101">Las implementaciones EventSource.WriteEvent deben pasar a WriteEvent los mismos parámetros que recibió (además del identificador)</span><span class="sxs-lookup"><span data-stu-id="69fba-101">EventSource.WriteEvent impls must pass WriteEvent the same parameters that it received (plus ID)</span></span>

#### <a name="details"></a><span data-ttu-id="69fba-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="69fba-102">Details</span></span>

<span data-ttu-id="69fba-103">El runtime ahora aplica el contrato que especifica lo siguiente: una clase derivada de <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> que define un método de evento ETW debe llamar al método <code>EventSource.WriteEvent</code> de la clase base con el identificador de evento, seguido de los mismos argumentos que se pasaron al método de evento ETW.</span><span class="sxs-lookup"><span data-stu-id="69fba-103">The runtime now enforces the contract that specifies the following: A class derived from <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> that defines an ETW event method must call the base class <code>EventSource.WriteEvent</code> method with the event ID followed by the same arguments that the ETW event method was passed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="69fba-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="69fba-104">Suggestion</span></span>

<span data-ttu-id="69fba-105">Se produce una excepción <xref:System.IndexOutOfRangeException?displayProperty=fullName> si un objeto <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> lee datos <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> en proceso para un origen de eventos que infringe este contrato.</span><span class="sxs-lookup"><span data-stu-id="69fba-105">An <xref:System.IndexOutOfRangeException?displayProperty=fullName> exception is thrown if an <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> reads <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> data in process for an event source that violates this contract.</span></span>

| <span data-ttu-id="69fba-106">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="69fba-106">Name</span></span>    | <span data-ttu-id="69fba-107">Valor</span><span class="sxs-lookup"><span data-stu-id="69fba-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="69fba-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="69fba-108">Scope</span></span>   |<span data-ttu-id="69fba-109">Secundaria</span><span class="sxs-lookup"><span data-stu-id="69fba-109">Minor</span></span>|
|<span data-ttu-id="69fba-110">Versión</span><span class="sxs-lookup"><span data-stu-id="69fba-110">Version</span></span>|<span data-ttu-id="69fba-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="69fba-111">4.5.1</span></span>|
|<span data-ttu-id="69fba-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="69fba-112">Type</span></span>|<span data-ttu-id="69fba-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="69fba-113">Runtime</span></span>|

---
ms.openlocfilehash: 3aafb14b65f7c0f9e5d77927809547f9d4b96e1c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620653"
---
### <a name="error-codes-for-maxrequestlength-or-maxreceivedmessagesize-are-different"></a><span data-ttu-id="536b4-101">Los códigos de error para maxRequestLength o maxReceivedMessageSize son diferentes</span><span class="sxs-lookup"><span data-stu-id="536b4-101">Error codes for maxRequestLength or maxReceivedMessageSize are different</span></span>

#### <a name="details"></a><span data-ttu-id="536b4-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="536b4-102">Details</span></span>

<span data-ttu-id="536b4-103">Los mensajes de servicios web de WCF hospedados en Internet Information Services (IIS) o Servidor de desarrollo de ASP.NET que superan maxRequestLength (en ASP.NET) o maxReceivedMessageSize (en WCF) tienen otro código de error. El código de estado HTTP ha cambiado de 400 (Solicitud incorrecta) a 413 (Entidad de solicitud demasiado grande), y los mensajes que superan el valor maxRequestLength o maxReceivedMessageSize inician una excepción <xref:System.ServiceModel.ProtocolException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="536b4-103">Messages in WCF web services hosted in Internet Information Services (IIS) or ASP.NET Development Server that exceed maxRequestLength (in ASP.NET) or maxReceivedMessageSize (in WCF) have different error codeThe HTTP status code has changed from 400 (Bad Request) to 413 (Request Entity Too Large), and messages that exceed either the maxRequestLength or the maxReceivedMessageSize setting throw a <xref:System.ServiceModel.ProtocolException?displayProperty=fullName> exception.</span></span> <span data-ttu-id="536b4-104">Esto incluye los casos en los que el modo de transferencia es Streamed.</span><span class="sxs-lookup"><span data-stu-id="536b4-104">This includes cases in which the transfer mode is Streamed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="536b4-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="536b4-105">Suggestion</span></span>

<span data-ttu-id="536b4-106">Este cambio facilita la depuración en casos donde la longitud del mensaje supera los límites permitidos por ASP.NET o WCF. Debe modificar cualquier código que realice el procesamiento en función de un código de estado HTTP 400.</span><span class="sxs-lookup"><span data-stu-id="536b4-106">This change facilitates debugging in cases where the message length exceeds the limits allowed by ASP.NET or WCF.You must modify any code that performs processing based on an HTTP 400 status code.</span></span>

| <span data-ttu-id="536b4-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="536b4-107">Name</span></span>    | <span data-ttu-id="536b4-108">Valor</span><span class="sxs-lookup"><span data-stu-id="536b4-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="536b4-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="536b4-109">Scope</span></span>   |<span data-ttu-id="536b4-110">Borde</span><span class="sxs-lookup"><span data-stu-id="536b4-110">Edge</span></span>|
|<span data-ttu-id="536b4-111">Versión</span><span class="sxs-lookup"><span data-stu-id="536b4-111">Version</span></span>|<span data-ttu-id="536b4-112">4.5</span><span class="sxs-lookup"><span data-stu-id="536b4-112">4.5</span></span>|
|<span data-ttu-id="536b4-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="536b4-113">Type</span></span>|<span data-ttu-id="536b4-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="536b4-114">Runtime</span></span>|

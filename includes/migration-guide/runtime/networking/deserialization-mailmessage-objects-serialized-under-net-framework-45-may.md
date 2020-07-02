---
ms.openlocfilehash: ad953a1562db407c04d7860c60eb5964fe6fe2ca
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620638"
---
### <a name="deserialization-of-mailmessage-objects-serialized-under-the-net-framework-45-may-fail"></a><span data-ttu-id="c8a13-101">Se puede producir un error en las deserialización de los objetos MailMessage serializados en .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="c8a13-101">Deserialization of MailMessage objects serialized under the .NET Framework 4.5 may fail</span></span>

#### <a name="details"></a><span data-ttu-id="c8a13-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="c8a13-102">Details</span></span>

<span data-ttu-id="c8a13-103">A partir de .NET Framework 4.5, los objetos <xref:System.Web.Mail.MailMessage> pueden incluir caracteres que no sean ASCII.</span><span class="sxs-lookup"><span data-stu-id="c8a13-103">Starting with the .NET Framework 4.5, <xref:System.Web.Mail.MailMessage> objects can include non-ASCII characters.</span></span> <span data-ttu-id="c8a13-104">En .NET Framework 4, solo se admiten caracteres ASCII.</span><span class="sxs-lookup"><span data-stu-id="c8a13-104">In the .NET Framework 4, only ASCII characters are supported.</span></span> <span data-ttu-id="c8a13-105">Los objetos <xref:System.Web.Mail.MailMessage> que contienen caracteres que no son ASCII y que están serializados en .NET Framework 4.5 o una versión posterior no se pueden deserializar en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="c8a13-105"><xref:System.Web.Mail.MailMessage> objects that contain non-ASCII characters and that are serialized under the .NET Framework 4.5 or later cannot be deserialized under the .NET Framework 4.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c8a13-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="c8a13-106">Suggestion</span></span>

<span data-ttu-id="c8a13-107">Asegúrese de que el código proporciona control de excepciones al deserializar un objeto <xref:System.Web.Mail.MailMessage>.</span><span class="sxs-lookup"><span data-stu-id="c8a13-107">Ensure that your code provides exception handling when deserializing a <xref:System.Web.Mail.MailMessage> object.</span></span>

| <span data-ttu-id="c8a13-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="c8a13-108">Name</span></span>    | <span data-ttu-id="c8a13-109">Valor</span><span class="sxs-lookup"><span data-stu-id="c8a13-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c8a13-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="c8a13-110">Scope</span></span>   |<span data-ttu-id="c8a13-111">Secundaria</span><span class="sxs-lookup"><span data-stu-id="c8a13-111">Minor</span></span>|
|<span data-ttu-id="c8a13-112">Versión</span><span class="sxs-lookup"><span data-stu-id="c8a13-112">Version</span></span>|<span data-ttu-id="c8a13-113">4.5</span><span class="sxs-lookup"><span data-stu-id="c8a13-113">4.5</span></span>|
|<span data-ttu-id="c8a13-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="c8a13-114">Type</span></span>|<span data-ttu-id="c8a13-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="c8a13-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c8a13-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="c8a13-116">Affected APIs</span></span>

-<xref:System.Web.Mail.MailMessage?displayProperty=nameWithType></li></ul>|

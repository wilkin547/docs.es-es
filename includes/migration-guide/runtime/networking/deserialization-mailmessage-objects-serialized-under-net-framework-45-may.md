---
ms.openlocfilehash: 2c44c2e1658f8de556d3f7222de3fa6d4594163a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497219"
---
### <a name="deserialization-of-mailmessage-objects-serialized-under-the-net-framework-45-may-fail"></a><span data-ttu-id="aa25d-101">Se puede producir un error en las deserialización de los objetos MailMessage serializados en .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="aa25d-101">Deserialization of MailMessage objects serialized under the .NET Framework 4.5 may fail</span></span>

#### <a name="details"></a><span data-ttu-id="aa25d-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="aa25d-102">Details</span></span>

<span data-ttu-id="aa25d-103">A partir de .NET Framework 4.5, los objetos <xref:System.Web.Mail.MailMessage> pueden incluir caracteres que no sean ASCII.</span><span class="sxs-lookup"><span data-stu-id="aa25d-103">Starting with the .NET Framework 4.5, <xref:System.Web.Mail.MailMessage> objects can include non-ASCII characters.</span></span> <span data-ttu-id="aa25d-104">En .NET Framework 4, solo se admiten caracteres ASCII.</span><span class="sxs-lookup"><span data-stu-id="aa25d-104">In the .NET Framework 4, only ASCII characters are supported.</span></span> <span data-ttu-id="aa25d-105">Los objetos <xref:System.Web.Mail.MailMessage> que contienen caracteres que no son ASCII y que están serializados en .NET Framework 4.5 o una versión posterior no se pueden deserializar en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="aa25d-105"><xref:System.Web.Mail.MailMessage> objects that contain non-ASCII characters and that are serialized under the .NET Framework 4.5 or later cannot be deserialized under the .NET Framework 4.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="aa25d-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="aa25d-106">Suggestion</span></span>

<span data-ttu-id="aa25d-107">Asegúrese de que el código proporciona control de excepciones al deserializar un objeto <xref:System.Web.Mail.MailMessage>.</span><span class="sxs-lookup"><span data-stu-id="aa25d-107">Ensure that your code provides exception handling when deserializing a <xref:System.Web.Mail.MailMessage> object.</span></span>

| <span data-ttu-id="aa25d-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="aa25d-108">Name</span></span>    | <span data-ttu-id="aa25d-109">Valor</span><span class="sxs-lookup"><span data-stu-id="aa25d-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="aa25d-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="aa25d-110">Scope</span></span>   |<span data-ttu-id="aa25d-111">Secundaria</span><span class="sxs-lookup"><span data-stu-id="aa25d-111">Minor</span></span>|
|<span data-ttu-id="aa25d-112">Versión</span><span class="sxs-lookup"><span data-stu-id="aa25d-112">Version</span></span>|<span data-ttu-id="aa25d-113">4.5</span><span class="sxs-lookup"><span data-stu-id="aa25d-113">4.5</span></span>|
|<span data-ttu-id="aa25d-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="aa25d-114">Type</span></span>|<span data-ttu-id="aa25d-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="aa25d-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="aa25d-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="aa25d-116">Affected APIs</span></span>

- <xref:System.Web.Mail.MailMessage?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Web.Mail.MailMessage`

-->

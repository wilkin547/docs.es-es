---
ms.openlocfilehash: a6f93bbdf39a1b525e2daeb12afc3a6392a66e30
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235955"
---
### <a name="deserialization-of-mailmessage-objects-serialized-under-the-net-framework-45-may-fail"></a><span data-ttu-id="8d77a-101">Se puede producir un error en las deserialización de los objetos MailMessage serializados en .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="8d77a-101">Deserialization of MailMessage objects serialized under the .NET Framework 4.5 may fail</span></span>

|   |   |
|---|---|
|<span data-ttu-id="8d77a-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="8d77a-102">Details</span></span>|<span data-ttu-id="8d77a-103">A partir de .NET Framework 4.5, los objetos <xref:System.Web.Mail.MailMessage> pueden incluir caracteres que no sean ASCII.</span><span class="sxs-lookup"><span data-stu-id="8d77a-103">Starting with the .NET Framework 4.5, <xref:System.Web.Mail.MailMessage> objects can include non-ASCII characters.</span></span> <span data-ttu-id="8d77a-104">En .NET Framework 4, solo se admiten caracteres ASCII.</span><span class="sxs-lookup"><span data-stu-id="8d77a-104">In the .NET Framework 4, only ASCII characters are supported.</span></span> <span data-ttu-id="8d77a-105">Los objetos <xref:System.Web.Mail.MailMessage> que contienen caracteres que no son ASCII y que están serializados en .NET Framework 4.5 o una versión posterior no se pueden deserializar en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="8d77a-105"><xref:System.Web.Mail.MailMessage> objects that contain non-ASCII characters and that are serialized under the .NET Framework 4.5 or later cannot be deserialized under the .NET Framework 4.</span></span>|
|<span data-ttu-id="8d77a-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="8d77a-106">Suggestion</span></span>|<span data-ttu-id="8d77a-107">Asegúrese de que el código proporciona control de excepciones al deserializar un objeto <xref:System.Web.Mail.MailMessage>.</span><span class="sxs-lookup"><span data-stu-id="8d77a-107">Ensure that your code provides exception handling when deserializing a <xref:System.Web.Mail.MailMessage> object.</span></span>|
|<span data-ttu-id="8d77a-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="8d77a-108">Scope</span></span>|<span data-ttu-id="8d77a-109">Secundaria</span><span class="sxs-lookup"><span data-stu-id="8d77a-109">Minor</span></span>|
|<span data-ttu-id="8d77a-110">Versión</span><span class="sxs-lookup"><span data-stu-id="8d77a-110">Version</span></span>|<span data-ttu-id="8d77a-111">4.5</span><span class="sxs-lookup"><span data-stu-id="8d77a-111">4.5</span></span>|
|<span data-ttu-id="8d77a-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="8d77a-112">Type</span></span>|<span data-ttu-id="8d77a-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="8d77a-113">Runtime</span></span>|
|<span data-ttu-id="8d77a-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="8d77a-114">Affected APIs</span></span>|<ul><li><xref:System.Web.Mail.MailMessage?displayProperty=nameWithType></li></ul>|

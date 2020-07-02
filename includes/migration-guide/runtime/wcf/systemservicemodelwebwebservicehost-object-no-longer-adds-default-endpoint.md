---
ms.openlocfilehash: 57f68c10d5d1edc9b8deaca2f4fe7edda2dd69b0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620668"
---
### <a name="systemservicemodelwebwebservicehost-object-no-longer-adds-a-default-endpoint"></a><span data-ttu-id="58945-101">El objeto System.ServiceModel.Web.WebServiceHost ya no agrega un punto de conexión predeterminado</span><span class="sxs-lookup"><span data-stu-id="58945-101">System.ServiceModel.Web.WebServiceHost object no longer adds a default endpoint</span></span>

#### <a name="details"></a><span data-ttu-id="58945-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="58945-102">Details</span></span>

<span data-ttu-id="58945-103">El objeto <xref:System.ServiceModel.Web.WebServiceHost> ya no agrega un punto de conexión predeterminado si el código de la aplicación ha agregado un punto de conexión explícito.</span><span class="sxs-lookup"><span data-stu-id="58945-103">The <xref:System.ServiceModel.Web.WebServiceHost> object no longer adds a default endpoint if an explicit endpoint has been added by application code.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="58945-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="58945-104">Suggestion</span></span>

<span data-ttu-id="58945-105">Si los usuarios esperan poder conectarse a un punto de conexión predeterminado y ya se han agregados otros puntos de conexión explícitos a <xref:System.ServiceModel.Web.WebServiceHost?displayProperty=fullName>, los puntos de conexión predeterminados también se deben agregar de forma explícita (mediante <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints?displayProperty=fullName>).</span><span class="sxs-lookup"><span data-stu-id="58945-105">If users will expect to be able to connect to a default endpoint and other explicit endpoints have been added to the <xref:System.ServiceModel.Web.WebServiceHost?displayProperty=fullName>, default endpoints should also be added explicitly (using <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints?displayProperty=fullName>).</span></span>

| <span data-ttu-id="58945-106">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="58945-106">Name</span></span>    | <span data-ttu-id="58945-107">Valor</span><span class="sxs-lookup"><span data-stu-id="58945-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="58945-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="58945-108">Scope</span></span>   |<span data-ttu-id="58945-109">Secundaria</span><span class="sxs-lookup"><span data-stu-id="58945-109">Minor</span></span>|
|<span data-ttu-id="58945-110">Versión</span><span class="sxs-lookup"><span data-stu-id="58945-110">Version</span></span>|<span data-ttu-id="58945-111">4.5</span><span class="sxs-lookup"><span data-stu-id="58945-111">4.5</span></span>|
|<span data-ttu-id="58945-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="58945-112">Type</span></span>|<span data-ttu-id="58945-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="58945-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="58945-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="58945-114">Affected APIs</span></span>

-<xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.String)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.String,System.Uri)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.ServiceModel.Description.ServiceEndpoint)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.String)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.Uri)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.String,System.Uri)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)?displayProperty=nameWithType></li></ul>|

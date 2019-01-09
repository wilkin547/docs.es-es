---
title: '&lt;mexEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: 4e2fb4946ee68b3cbd5bd6bfbafe6bb5e9c9106f
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149155"
---
# <a name="ltmexendpointgt"></a><span data-ttu-id="e3cef-102">&lt;mexEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="e3cef-102">&lt;mexEndpoint&gt;</span></span>
<span data-ttu-id="e3cef-103">Este elemento de configuración define un punto de conexión estándar con un contrato IMetadataExchange fijo.</span><span class="sxs-lookup"><span data-stu-id="e3cef-103">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="e3cef-104">Puesto que todos los puntos de conexión del intercambio de metadatos especifican IMetadataExchange como su contrato, puede usar este punto estándar en lugar de definir uno para sí mismo.</span><span class="sxs-lookup"><span data-stu-id="e3cef-104">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
 <span data-ttu-id="e3cef-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e3cef-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="e3cef-106">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="e3cef-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3cef-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e3cef-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3cef-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e3cef-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e3cef-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e3cef-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e3cef-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="e3cef-110">Attributes</span></span>  
  
|<span data-ttu-id="e3cef-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="e3cef-111">Attribute</span></span>|<span data-ttu-id="e3cef-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3cef-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e3cef-113">name</span><span class="sxs-lookup"><span data-stu-id="e3cef-113">name</span></span>|<span data-ttu-id="e3cef-114">Cadena que especifica el nombre de la configuración del extremo estándar.</span><span class="sxs-lookup"><span data-stu-id="e3cef-114">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="e3cef-115">El nombre se utiliza en el atributo `endpointConfiguration` del punto de conexión del servicio para vincular un punto de conexión estándar a su configuración.</span><span class="sxs-lookup"><span data-stu-id="e3cef-115">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e3cef-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e3cef-116">Child Elements</span></span>  
 <span data-ttu-id="e3cef-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e3cef-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e3cef-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e3cef-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e3cef-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="e3cef-119">Element</span></span>|<span data-ttu-id="e3cef-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3cef-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3cef-121">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="e3cef-121">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="e3cef-122">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="e3cef-122">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|

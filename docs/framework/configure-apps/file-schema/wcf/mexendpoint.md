---
title: '&lt;mexEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 713c1c260f36d6d980903cce1ebcc9c5648116c2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltmexendpointgt"></a><span data-ttu-id="55fcd-102">&lt;mexEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="55fcd-102">&lt;mexEndpoint&gt;</span></span>
<span data-ttu-id="55fcd-103">Este elemento de configuración define un punto de conexión estándar con un contrato IMetadataExchange fijo.</span><span class="sxs-lookup"><span data-stu-id="55fcd-103">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="55fcd-104">Puesto que todos los puntos de conexión del intercambio de metadatos especifican IMetadataExchange como su contrato, puede usar este punto estándar en lugar de definir uno para sí mismo.</span><span class="sxs-lookup"><span data-stu-id="55fcd-104">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
 <span data-ttu-id="55fcd-105">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="55fcd-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="55fcd-106">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="55fcd-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55fcd-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="55fcd-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="55fcd-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="55fcd-108">Attributes and Elements</span></span>  
 <span data-ttu-id="55fcd-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="55fcd-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="55fcd-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="55fcd-110">Attributes</span></span>  
  
|<span data-ttu-id="55fcd-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="55fcd-111">Attribute</span></span>|<span data-ttu-id="55fcd-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="55fcd-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="55fcd-113">name</span><span class="sxs-lookup"><span data-stu-id="55fcd-113">name</span></span>|<span data-ttu-id="55fcd-114">Cadena que especifica el nombre de la configuración del extremo estándar.</span><span class="sxs-lookup"><span data-stu-id="55fcd-114">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="55fcd-115">El nombre se utiliza en el atributo `endpointConfiguration` del extremo del servicio para vincular un extremo estándar a su configuración.</span><span class="sxs-lookup"><span data-stu-id="55fcd-115">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="55fcd-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="55fcd-116">Child Elements</span></span>  
 <span data-ttu-id="55fcd-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="55fcd-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="55fcd-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="55fcd-118">Parent Elements</span></span>  
  
|<span data-ttu-id="55fcd-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="55fcd-119">Element</span></span>|<span data-ttu-id="55fcd-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="55fcd-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="55fcd-121">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="55fcd-121">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="55fcd-122">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="55fcd-122">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|

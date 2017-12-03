---
title: '&lt;workflowControlEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 741968e160683ab38f79effdfa0bdf56053cfb93
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltworkflowcontrolendpointgt"></a><span data-ttu-id="99264-102">&lt;workflowControlEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="99264-102">&lt;workflowControlEndpoint&gt;</span></span>
<span data-ttu-id="99264-103">Este elemento de configuración define un punto de conexión estándar para controlar la ejecución de instancias de flujo de trabajo (crear, ejecutar, suspender, terminar, etc).</span><span class="sxs-lookup"><span data-stu-id="99264-103">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
<span data-ttu-id="99264-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="99264-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="99264-105">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="99264-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99264-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99264-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99264-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="99264-107">Attributes and Elements</span></span>  
 <span data-ttu-id="99264-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="99264-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99264-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="99264-109">Attributes</span></span>  
  
|<span data-ttu-id="99264-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="99264-110">Attribute</span></span>|<span data-ttu-id="99264-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="99264-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="99264-112">name</span><span class="sxs-lookup"><span data-stu-id="99264-112">name</span></span>|<span data-ttu-id="99264-113">Cadena que especifica el nombre de la configuración del extremo estándar.</span><span class="sxs-lookup"><span data-stu-id="99264-113">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="99264-114">El nombre se utiliza en el atributo `endpointConfiguration` del extremo del servicio para vincular un extremo estándar a su configuración.</span><span class="sxs-lookup"><span data-stu-id="99264-114">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99264-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="99264-115">Child Elements</span></span>  
 <span data-ttu-id="99264-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="99264-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99264-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="99264-117">Parent Elements</span></span>  
  
|<span data-ttu-id="99264-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="99264-118">Element</span></span>|<span data-ttu-id="99264-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="99264-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99264-120">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="99264-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="99264-121">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="99264-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="99264-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="99264-122">See Also</span></span>  
 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>

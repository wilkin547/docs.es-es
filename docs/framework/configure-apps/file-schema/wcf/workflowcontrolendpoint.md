---
title: <workflowControlEndpoint>
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: a9c16d1036a8177120cd152d4ac211ad084d588e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150389"
---
# <a name="workflowcontrolendpoint"></a><span data-ttu-id="5d237-101">\<workflowControlEndpoint></span><span class="sxs-lookup"><span data-stu-id="5d237-101">\<workflowControlEndpoint></span></span>
<span data-ttu-id="5d237-102">Este elemento de configuración define un punto de conexión estándar para controlar la ejecución de instancias de flujo de trabajo (crear, ejecutar, suspender, terminar, etc).</span><span class="sxs-lookup"><span data-stu-id="5d237-102">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
<span data-ttu-id="5d237-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5d237-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="5d237-104">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="5d237-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d237-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d237-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d237-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5d237-106">Attributes and Elements</span></span>  
 <span data-ttu-id="5d237-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5d237-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d237-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="5d237-108">Attributes</span></span>  
  
|<span data-ttu-id="5d237-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="5d237-109">Attribute</span></span>|<span data-ttu-id="5d237-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d237-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5d237-111">name</span><span class="sxs-lookup"><span data-stu-id="5d237-111">name</span></span>|<span data-ttu-id="5d237-112">Cadena que especifica el nombre de la configuración del punto de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="5d237-112">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="5d237-113">El nombre se utiliza en el atributo `endpointConfiguration` del punto de conexión del servicio para vincular un punto de conexión estándar a su configuración.</span><span class="sxs-lookup"><span data-stu-id="5d237-113">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5d237-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5d237-114">Child Elements</span></span>  
 <span data-ttu-id="5d237-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5d237-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5d237-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5d237-116">Parent Elements</span></span>  
  
|<span data-ttu-id="5d237-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="5d237-117">Element</span></span>|<span data-ttu-id="5d237-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d237-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d237-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="5d237-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="5d237-120">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="5d237-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5d237-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d237-121">See also</span></span>

- <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>

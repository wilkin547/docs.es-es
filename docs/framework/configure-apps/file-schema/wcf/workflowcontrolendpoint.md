---
title: <workflowControlEndpoint>
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: a9c16d1036a8177120cd152d4ac211ad084d588e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769647"
---
# <a name="workflowcontrolendpoint"></a><span data-ttu-id="42556-101">\<workflowControlEndpoint></span><span class="sxs-lookup"><span data-stu-id="42556-101">\<workflowControlEndpoint></span></span>
<span data-ttu-id="42556-102">Este elemento de configuración define un punto de conexión estándar para controlar la ejecución de instancias de flujo de trabajo (crear, ejecutar, suspender, terminar, etc).</span><span class="sxs-lookup"><span data-stu-id="42556-102">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
<span data-ttu-id="42556-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="42556-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="42556-104">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="42556-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42556-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42556-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42556-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="42556-106">Attributes and Elements</span></span>  
 <span data-ttu-id="42556-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="42556-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42556-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="42556-108">Attributes</span></span>  
  
|<span data-ttu-id="42556-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="42556-109">Attribute</span></span>|<span data-ttu-id="42556-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="42556-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="42556-111">name</span><span class="sxs-lookup"><span data-stu-id="42556-111">name</span></span>|<span data-ttu-id="42556-112">Cadena que especifica el nombre de la configuración del punto de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="42556-112">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="42556-113">El nombre se utiliza en el atributo `endpointConfiguration` del punto de conexión del servicio para vincular un punto de conexión estándar a su configuración.</span><span class="sxs-lookup"><span data-stu-id="42556-113">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="42556-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="42556-114">Child Elements</span></span>  
 <span data-ttu-id="42556-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="42556-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="42556-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="42556-116">Parent Elements</span></span>  
  
|<span data-ttu-id="42556-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="42556-117">Element</span></span>|<span data-ttu-id="42556-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="42556-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="42556-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="42556-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="42556-120">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="42556-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="42556-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="42556-121">See also</span></span>

- <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>

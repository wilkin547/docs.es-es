---
title: '&lt;workflowControlEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: 87c745cfb8f7cd98c25cd34fc1aa94a26a5ba507
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754790"
---
# <a name="ltworkflowcontrolendpointgt"></a><span data-ttu-id="efb40-102">&lt;workflowControlEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="efb40-102">&lt;workflowControlEndpoint&gt;</span></span>
<span data-ttu-id="efb40-103">Este elemento de configuración define un punto de conexión estándar para controlar la ejecución de instancias de flujo de trabajo (crear, ejecutar, suspender, terminar, etc).</span><span class="sxs-lookup"><span data-stu-id="efb40-103">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
<span data-ttu-id="efb40-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="efb40-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="efb40-105">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="efb40-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efb40-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="efb40-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="efb40-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="efb40-107">Attributes and Elements</span></span>  
 <span data-ttu-id="efb40-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="efb40-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="efb40-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="efb40-109">Attributes</span></span>  
  
|<span data-ttu-id="efb40-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="efb40-110">Attribute</span></span>|<span data-ttu-id="efb40-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="efb40-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="efb40-112">name</span><span class="sxs-lookup"><span data-stu-id="efb40-112">name</span></span>|<span data-ttu-id="efb40-113">Cadena que especifica el nombre de la configuración del extremo estándar.</span><span class="sxs-lookup"><span data-stu-id="efb40-113">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="efb40-114">El nombre se utiliza en el atributo `endpointConfiguration` del extremo del servicio para vincular un extremo estándar a su configuración.</span><span class="sxs-lookup"><span data-stu-id="efb40-114">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="efb40-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="efb40-115">Child Elements</span></span>  
 <span data-ttu-id="efb40-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="efb40-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="efb40-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="efb40-117">Parent Elements</span></span>  
  
|<span data-ttu-id="efb40-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="efb40-118">Element</span></span>|<span data-ttu-id="efb40-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="efb40-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="efb40-120">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="efb40-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="efb40-121">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="efb40-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="efb40-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="efb40-122">See Also</span></span>  
 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>

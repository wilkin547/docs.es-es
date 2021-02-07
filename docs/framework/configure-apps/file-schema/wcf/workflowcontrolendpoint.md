---
description: 'Más información acerca de: <workflowControlEndpoint>'
title: <workflowControlEndpoint>
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: 5205edf159bd947531231e69fd23f6cdf9c77d2d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682350"
---
# \<workflowControlEndpoint>

<span data-ttu-id="b2896-102">Este elemento de configuración define un punto de conexión estándar para controlar la ejecución de instancias de flujo de trabajo (crear, ejecutar, suspender, terminar, etc).</span><span class="sxs-lookup"><span data-stu-id="b2896-102">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowControlEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="b2896-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2896-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2896-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b2896-104">Attributes and Elements</span></span>  

 <span data-ttu-id="b2896-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b2896-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2896-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="b2896-106">Attributes</span></span>  
  
|<span data-ttu-id="b2896-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="b2896-107">Attribute</span></span>|<span data-ttu-id="b2896-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2896-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b2896-109">name</span><span class="sxs-lookup"><span data-stu-id="b2896-109">name</span></span>|<span data-ttu-id="b2896-110">Cadena que especifica el nombre de la configuración del punto de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="b2896-110">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="b2896-111">El nombre se utiliza en el atributo `endpointConfiguration` del punto de conexión del servicio para vincular un punto de conexión estándar a su configuración.</span><span class="sxs-lookup"><span data-stu-id="b2896-111">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b2896-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b2896-112">Child Elements</span></span>  

 <span data-ttu-id="b2896-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b2896-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b2896-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b2896-114">Parent Elements</span></span>  
  
|<span data-ttu-id="b2896-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="b2896-115">Element</span></span>|<span data-ttu-id="b2896-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2896-116">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="b2896-117">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="b2896-117">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b2896-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2896-118">See also</span></span>

- <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>

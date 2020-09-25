---
title: <workflowControlEndpoint>
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: 572ff7e119828897860944a430e5f51f5d1c3cad
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194848"
---
# \<workflowControlEndpoint>

<span data-ttu-id="547e7-101">Este elemento de configuración define un punto de conexión estándar para controlar la ejecución de instancias de flujo de trabajo (crear, ejecutar, suspender, terminar, etc).</span><span class="sxs-lookup"><span data-stu-id="547e7-101">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowControlEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="547e7-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="547e7-102">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="547e7-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="547e7-103">Attributes and Elements</span></span>  

 <span data-ttu-id="547e7-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="547e7-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="547e7-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="547e7-105">Attributes</span></span>  
  
|<span data-ttu-id="547e7-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="547e7-106">Attribute</span></span>|<span data-ttu-id="547e7-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="547e7-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="547e7-108">name</span><span class="sxs-lookup"><span data-stu-id="547e7-108">name</span></span>|<span data-ttu-id="547e7-109">Cadena que especifica el nombre de la configuración del punto de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="547e7-109">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="547e7-110">El nombre se utiliza en el atributo `endpointConfiguration` del punto de conexión del servicio para vincular un punto de conexión estándar a su configuración.</span><span class="sxs-lookup"><span data-stu-id="547e7-110">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="547e7-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="547e7-111">Child Elements</span></span>  

 <span data-ttu-id="547e7-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="547e7-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="547e7-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="547e7-113">Parent Elements</span></span>  
  
|<span data-ttu-id="547e7-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="547e7-114">Element</span></span>|<span data-ttu-id="547e7-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="547e7-115">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="547e7-116">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="547e7-116">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="547e7-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="547e7-117">See also</span></span>

- <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>

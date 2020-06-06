---
title: <workflowControlEndpoint>
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: 670c1573fe4378a18c19d0a58fe58241745725bd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854786"
---
# \<workflowControlEndpoint>
<span data-ttu-id="2069a-101">Este elemento de configuración define un punto de conexión estándar para controlar la ejecución de instancias de flujo de trabajo (crear, ejecutar, suspender, terminar, etc).</span><span class="sxs-lookup"><span data-stu-id="2069a-101">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowControlEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="2069a-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2069a-102">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2069a-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2069a-103">Attributes and Elements</span></span>  
 <span data-ttu-id="2069a-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2069a-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2069a-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="2069a-105">Attributes</span></span>  
  
|<span data-ttu-id="2069a-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="2069a-106">Attribute</span></span>|<span data-ttu-id="2069a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="2069a-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2069a-108">name</span><span class="sxs-lookup"><span data-stu-id="2069a-108">name</span></span>|<span data-ttu-id="2069a-109">Cadena que especifica el nombre de la configuración del punto de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="2069a-109">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="2069a-110">El nombre se utiliza en el atributo `endpointConfiguration` del punto de conexión del servicio para vincular un punto de conexión estándar a su configuración.</span><span class="sxs-lookup"><span data-stu-id="2069a-110">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2069a-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2069a-111">Child Elements</span></span>  
 <span data-ttu-id="2069a-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2069a-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2069a-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2069a-113">Parent Elements</span></span>  
  
|<span data-ttu-id="2069a-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="2069a-114">Element</span></span>|<span data-ttu-id="2069a-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="2069a-115">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="2069a-116">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="2069a-116">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2069a-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2069a-117">See also</span></span>

- <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>

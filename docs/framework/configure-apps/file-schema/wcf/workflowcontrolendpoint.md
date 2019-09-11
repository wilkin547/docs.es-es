---
title: <workflowControlEndpoint>
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: 670c1573fe4378a18c19d0a58fe58241745725bd
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854786"
---
# <a name="workflowcontrolendpoint"></a><span data-ttu-id="574b1-101">\<workflowControlEndpoint></span><span class="sxs-lookup"><span data-stu-id="574b1-101">\<workflowControlEndpoint></span></span>
<span data-ttu-id="574b1-102">Este elemento de configuración define un punto de conexión estándar para controlar la ejecución de instancias de flujo de trabajo (crear, ejecutar, suspender, terminar, etc).</span><span class="sxs-lookup"><span data-stu-id="574b1-102">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
<span data-ttu-id="574b1-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="574b1-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="574b1-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="574b1-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="574b1-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> standardEndpoints**](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="574b1-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="574b1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> workflowControlEndpoint**</span><span class="sxs-lookup"><span data-stu-id="574b1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowControlEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="574b1-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="574b1-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="574b1-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="574b1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="574b1-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="574b1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="574b1-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="574b1-110">Attributes</span></span>  
  
|<span data-ttu-id="574b1-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="574b1-111">Attribute</span></span>|<span data-ttu-id="574b1-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="574b1-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="574b1-113">Nombre</span><span class="sxs-lookup"><span data-stu-id="574b1-113">name</span></span>|<span data-ttu-id="574b1-114">Cadena que especifica el nombre de la configuración del punto de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="574b1-114">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="574b1-115">El nombre se utiliza en el atributo `endpointConfiguration` del punto de conexión del servicio para vincular un punto de conexión estándar a su configuración.</span><span class="sxs-lookup"><span data-stu-id="574b1-115">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="574b1-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="574b1-116">Child Elements</span></span>  
 <span data-ttu-id="574b1-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="574b1-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="574b1-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="574b1-118">Parent Elements</span></span>  
  
|<span data-ttu-id="574b1-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="574b1-119">Element</span></span>|<span data-ttu-id="574b1-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="574b1-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="574b1-121">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="574b1-121">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="574b1-122">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="574b1-122">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="574b1-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="574b1-123">See also</span></span>

- <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>

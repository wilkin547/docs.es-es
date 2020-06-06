---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: 02d1d530f37f5082153c9aa6b9993fc4009917f5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854981"
---
# \<services>
<span data-ttu-id="50600-101">Los servicios se definen en la sección de `services` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="50600-101">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="50600-102">Cada servicio tiene su propia sección de configuración de `service`.</span><span class="sxs-lookup"><span data-stu-id="50600-102">Each service has its own `service` configuration section.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<services>**  
  
## <a name="syntax"></a><span data-ttu-id="50600-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="50600-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="50600-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="50600-104">Attributes and Elements</span></span>  
 <span data-ttu-id="50600-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="50600-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="50600-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="50600-106">Attributes</span></span>  
 <span data-ttu-id="50600-107">None</span><span class="sxs-lookup"><span data-stu-id="50600-107">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="50600-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="50600-108">Child Elements</span></span>  
  
|<span data-ttu-id="50600-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="50600-109">Element</span></span>|<span data-ttu-id="50600-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="50600-110">Description</span></span>|  
|-------------|-----------------|  
|[\<service>](service.md)|<span data-ttu-id="50600-111">Defina el contrato de servicios, comportamiento y puntos de conexión del servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="50600-111">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="50600-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="50600-112">Parent Elements</span></span>  
  
|<span data-ttu-id="50600-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="50600-113">Element</span></span>|<span data-ttu-id="50600-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="50600-114">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="50600-115">El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="50600-115">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="50600-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="50600-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>

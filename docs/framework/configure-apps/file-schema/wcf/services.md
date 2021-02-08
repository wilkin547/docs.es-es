---
description: 'Más información acerca de: <services>'
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: 6e8c0c5ad5390c097db7bf1be1f0d489e1c0d624
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786712"
---
# \<services>

<span data-ttu-id="45027-102">Los servicios se definen en la sección de `services` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="45027-102">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="45027-103">Cada servicio tiene su propia sección de configuración de `service`.</span><span class="sxs-lookup"><span data-stu-id="45027-103">Each service has its own `service` configuration section.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<services>**  
  
## <a name="syntax"></a><span data-ttu-id="45027-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45027-104">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="45027-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="45027-105">Attributes and Elements</span></span>  

 <span data-ttu-id="45027-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="45027-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="45027-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="45027-107">Attributes</span></span>  

 <span data-ttu-id="45027-108">None</span><span class="sxs-lookup"><span data-stu-id="45027-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="45027-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="45027-109">Child Elements</span></span>  
  
|<span data-ttu-id="45027-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="45027-110">Element</span></span>|<span data-ttu-id="45027-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="45027-111">Description</span></span>|  
|-------------|-----------------|  
|[\<service>](service.md)|<span data-ttu-id="45027-112">Defina el contrato de servicios, comportamiento y puntos de conexión del servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="45027-112">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="45027-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="45027-113">Parent Elements</span></span>  
  
|<span data-ttu-id="45027-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="45027-114">Element</span></span>|<span data-ttu-id="45027-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="45027-115">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="45027-116">El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="45027-116">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="45027-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="45027-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>

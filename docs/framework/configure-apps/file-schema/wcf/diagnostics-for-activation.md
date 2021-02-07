---
description: 'Más información sobre: <diagnostics> para la activación'
title: <diagnostics> para la activación
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: aa1529a478ac367ea89c8926571c6c6f2f57cf74
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698367"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="06b9f-103">\<diagnostics> para la activación</span><span class="sxs-lookup"><span data-stu-id="06b9f-103">\<diagnostics> for Activation</span></span>

<span data-ttu-id="06b9f-104">Configura las funcionalidades de diagnóstico del agente de escucha de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="06b9f-104">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<diagnostics>**  
  
## <a name="syntax"></a><span data-ttu-id="06b9f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06b9f-105">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="06b9f-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="06b9f-106">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06b9f-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="06b9f-107">Attributes and Elements</span></span>  

 <span data-ttu-id="06b9f-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="06b9f-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06b9f-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="06b9f-109">Attributes</span></span>  
  
|<span data-ttu-id="06b9f-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="06b9f-110">Attribute</span></span>|<span data-ttu-id="06b9f-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="06b9f-111">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="06b9f-112">Un valor booleano que indica si los contadores de rendimiento están habilitados para el diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="06b9f-112">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="06b9f-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="06b9f-113">Child Elements</span></span>  

 <span data-ttu-id="06b9f-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="06b9f-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="06b9f-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="06b9f-115">Parent Elements</span></span>  
  
|<span data-ttu-id="06b9f-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="06b9f-116">Element</span></span>|<span data-ttu-id="06b9f-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="06b9f-117">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](system-servicemodel-activation.md)|<span data-ttu-id="06b9f-118">Contiene la configuración para el proceso de agente de escucha SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="06b9f-118">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="06b9f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="06b9f-119">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>

---
title: <diagnostics>para la activación
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 33b2cd4c5ae1b4076892a61aa7e2b927efa1ddc1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400412"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="acac7-102">\<diagnostics>para la activación</span><span class="sxs-lookup"><span data-stu-id="acac7-102">\<diagnostics> for Activation</span></span>
<span data-ttu-id="acac7-103">Configura las funcionalidades de diagnóstico del agente de escucha de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="acac7-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<diagnostics>**  
  
## <a name="syntax"></a><span data-ttu-id="acac7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="acac7-104">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="acac7-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="acac7-105">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="acac7-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="acac7-106">Attributes and Elements</span></span>  
 <span data-ttu-id="acac7-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="acac7-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="acac7-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="acac7-108">Attributes</span></span>  
  
|<span data-ttu-id="acac7-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="acac7-109">Attribute</span></span>|<span data-ttu-id="acac7-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="acac7-110">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="acac7-111">Un valor booleano que indica si los contadores de rendimiento están habilitados para el diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="acac7-111">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="acac7-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="acac7-112">Child Elements</span></span>  
 <span data-ttu-id="acac7-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="acac7-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="acac7-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="acac7-114">Parent Elements</span></span>  
  
|<span data-ttu-id="acac7-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="acac7-115">Element</span></span>|<span data-ttu-id="acac7-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="acac7-116">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](system-servicemodel-activation.md)|<span data-ttu-id="acac7-117">Contiene la configuración para el proceso de agente de escucha SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="acac7-117">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="acac7-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="acac7-118">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>

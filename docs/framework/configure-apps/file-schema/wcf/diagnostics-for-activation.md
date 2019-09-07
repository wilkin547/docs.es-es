---
title: <diagnostics>para la activación
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 33b2cd4c5ae1b4076892a61aa7e2b927efa1ddc1
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400412"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="69af1-102">\<diagnóstico > para la activación</span><span class="sxs-lookup"><span data-stu-id="69af1-102">\<diagnostics> for Activation</span></span>
<span data-ttu-id="69af1-103">Configura las funcionalidades de diagnóstico del agente de escucha de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="69af1-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
<span data-ttu-id="69af1-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="69af1-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="69af1-105">&nbsp;&nbsp;[ **\<System. serviceModel. Activation >** ](system-servicemodel-activation.md)</span><span class="sxs-lookup"><span data-stu-id="69af1-105">&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)</span></span>\
<span data-ttu-id="69af1-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<diagnóstico >**</span><span class="sxs-lookup"><span data-stu-id="69af1-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<diagnostics>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69af1-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69af1-107">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="69af1-108">Type</span><span class="sxs-lookup"><span data-stu-id="69af1-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69af1-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="69af1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="69af1-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="69af1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69af1-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="69af1-111">Attributes</span></span>  
  
|<span data-ttu-id="69af1-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="69af1-112">Attribute</span></span>|<span data-ttu-id="69af1-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="69af1-113">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="69af1-114">Un valor booleano que indica si los contadores de rendimiento están habilitados para el diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="69af1-114">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="69af1-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="69af1-115">Child Elements</span></span>  
 <span data-ttu-id="69af1-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="69af1-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="69af1-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="69af1-117">Parent Elements</span></span>  
  
|<span data-ttu-id="69af1-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="69af1-118">Element</span></span>|<span data-ttu-id="69af1-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="69af1-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="69af1-120">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="69af1-120">\<system.serviceModel.activation></span></span>](system-servicemodel-activation.md)|<span data-ttu-id="69af1-121">Contiene la configuración para el proceso de agente de escucha SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="69af1-121">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="69af1-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="69af1-122">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>

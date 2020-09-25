---
title: <diagnostics> para la activación
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: c16f32357d40b9b69d52c525ce8a395a3de8fdb1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192326"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="01db6-102">\<diagnostics> para la activación</span><span class="sxs-lookup"><span data-stu-id="01db6-102">\<diagnostics> for Activation</span></span>

<span data-ttu-id="01db6-103">Configura las funcionalidades de diagnóstico del agente de escucha de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="01db6-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<diagnostics>**  
  
## <a name="syntax"></a><span data-ttu-id="01db6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="01db6-104">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="01db6-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="01db6-105">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01db6-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="01db6-106">Attributes and Elements</span></span>  

 <span data-ttu-id="01db6-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="01db6-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01db6-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="01db6-108">Attributes</span></span>  
  
|<span data-ttu-id="01db6-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="01db6-109">Attribute</span></span>|<span data-ttu-id="01db6-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="01db6-110">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="01db6-111">Un valor booleano que indica si los contadores de rendimiento están habilitados para el diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="01db6-111">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="01db6-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="01db6-112">Child Elements</span></span>  

 <span data-ttu-id="01db6-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="01db6-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="01db6-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="01db6-114">Parent Elements</span></span>  
  
|<span data-ttu-id="01db6-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="01db6-115">Element</span></span>|<span data-ttu-id="01db6-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="01db6-116">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](system-servicemodel-activation.md)|<span data-ttu-id="01db6-117">Contiene la configuración para el proceso de agente de escucha SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="01db6-117">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="01db6-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="01db6-118">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>

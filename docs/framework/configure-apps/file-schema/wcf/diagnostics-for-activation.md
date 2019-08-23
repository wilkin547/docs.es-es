---
title: <diagnostics>para la activación
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 543c41936921eda39017e07f1c97294b268a9141
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919217"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="b839d-102">\<diagnóstico > para la activación</span><span class="sxs-lookup"><span data-stu-id="b839d-102">\<diagnostics> for Activation</span></span>
<span data-ttu-id="b839d-103">Configura las funcionalidades de diagnóstico del agente de escucha de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="b839d-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="b839d-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="b839d-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="b839d-105">\<diagnóstico ></span><span class="sxs-lookup"><span data-stu-id="b839d-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b839d-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b839d-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="b839d-107">Type</span><span class="sxs-lookup"><span data-stu-id="b839d-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b839d-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b839d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b839d-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b839d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b839d-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="b839d-110">Attributes</span></span>  
  
|<span data-ttu-id="b839d-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="b839d-111">Attribute</span></span>|<span data-ttu-id="b839d-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b839d-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="b839d-113">Un valor booleano que indica si los contadores de rendimiento están habilitados para el diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="b839d-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b839d-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b839d-114">Child Elements</span></span>  
 <span data-ttu-id="b839d-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b839d-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b839d-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b839d-116">Parent Elements</span></span>  
  
|<span data-ttu-id="b839d-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="b839d-117">Element</span></span>|<span data-ttu-id="b839d-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b839d-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b839d-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="b839d-119">\<system.serviceModel.activation></span></span>](system-servicemodel-activation.md)|<span data-ttu-id="b839d-120">Contiene la configuración para el proceso de agente de escucha SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="b839d-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b839d-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="b839d-121">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>

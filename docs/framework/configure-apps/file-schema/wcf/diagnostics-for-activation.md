---
title: <diagnostics> para la activación
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 30456963a7d74a93e39bb1fddc0910daae97f039
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59203813"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="1cc2f-102">\<diagnósticos > para la activación</span><span class="sxs-lookup"><span data-stu-id="1cc2f-102">\<diagnostics> for Activation</span></span>
<span data-ttu-id="1cc2f-103">Configura las funcionalidades del diagnóstico del agente de escucha de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="1cc2f-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="1cc2f-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="1cc2f-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="1cc2f-105">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="1cc2f-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cc2f-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1cc2f-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="1cc2f-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="1cc2f-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1cc2f-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1cc2f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1cc2f-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1cc2f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1cc2f-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="1cc2f-110">Attributes</span></span>  
  
|<span data-ttu-id="1cc2f-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="1cc2f-111">Attribute</span></span>|<span data-ttu-id="1cc2f-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="1cc2f-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="1cc2f-113">Un valor booleano que indica si los contadores de rendimiento están habilitados para el diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="1cc2f-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1cc2f-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1cc2f-114">Child Elements</span></span>  
 <span data-ttu-id="1cc2f-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1cc2f-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1cc2f-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1cc2f-116">Parent Elements</span></span>  
  
|<span data-ttu-id="1cc2f-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="1cc2f-117">Element</span></span>|<span data-ttu-id="1cc2f-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="1cc2f-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1cc2f-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="1cc2f-119">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="1cc2f-120">Contiene la configuración para el proceso de agente de escucha SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="1cc2f-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1cc2f-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="1cc2f-121">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>

---
title: '&lt;diagnostics&gt; para Activation'
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 28f051a7ab06dbc1b40f804c56071818eb37e88b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54144982"
---
# <a name="ltdiagnosticsgt-for-activation"></a><span data-ttu-id="054e5-102">&lt;diagnostics&gt; para Activation</span><span class="sxs-lookup"><span data-stu-id="054e5-102">&lt;diagnostics&gt; for Activation</span></span>
<span data-ttu-id="054e5-103">Configura las funcionalidades del diagnóstico del agente de escucha de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="054e5-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="054e5-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="054e5-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="054e5-105">\<diagnóstico ></span><span class="sxs-lookup"><span data-stu-id="054e5-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="054e5-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="054e5-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="054e5-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="054e5-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="054e5-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="054e5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="054e5-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="054e5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="054e5-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="054e5-110">Attributes</span></span>  
  
|<span data-ttu-id="054e5-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="054e5-111">Attribute</span></span>|<span data-ttu-id="054e5-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="054e5-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="054e5-113">Un valor booleano que indica si los contadores de rendimiento están habilitados para el diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="054e5-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="054e5-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="054e5-114">Child Elements</span></span>  
 <span data-ttu-id="054e5-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="054e5-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="054e5-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="054e5-116">Parent Elements</span></span>  
  
|<span data-ttu-id="054e5-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="054e5-117">Element</span></span>|<span data-ttu-id="054e5-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="054e5-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="054e5-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="054e5-119">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="054e5-120">Contiene la configuración para el proceso de agente de escucha SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="054e5-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="054e5-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="054e5-121">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>

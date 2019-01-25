---
title: '&lt;diagnostics&gt; para Activation'
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 5d8fcce28182dcac945655a52d829945a432a9b3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54723919"
---
# <a name="ltdiagnosticsgt-for-activation"></a><span data-ttu-id="fbbb9-102">&lt;diagnostics&gt; para Activation</span><span class="sxs-lookup"><span data-stu-id="fbbb9-102">&lt;diagnostics&gt; for Activation</span></span>
<span data-ttu-id="fbbb9-103">Configura las funcionalidades del diagnóstico del agente de escucha de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="fbbb9-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="fbbb9-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="fbbb9-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="fbbb9-105">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="fbbb9-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbbb9-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fbbb9-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="fbbb9-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="fbbb9-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fbbb9-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fbbb9-108">Attributes and Elements</span></span>  
 <span data-ttu-id="fbbb9-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fbbb9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fbbb9-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="fbbb9-110">Attributes</span></span>  
  
|<span data-ttu-id="fbbb9-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="fbbb9-111">Attribute</span></span>|<span data-ttu-id="fbbb9-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="fbbb9-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="fbbb9-113">Un valor booleano que indica si los contadores de rendimiento están habilitados para el diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="fbbb9-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fbbb9-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fbbb9-114">Child Elements</span></span>  
 <span data-ttu-id="fbbb9-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fbbb9-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fbbb9-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fbbb9-116">Parent Elements</span></span>  
  
|<span data-ttu-id="fbbb9-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="fbbb9-117">Element</span></span>|<span data-ttu-id="fbbb9-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="fbbb9-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fbbb9-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="fbbb9-119">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="fbbb9-120">Contiene la configuración para el proceso de agente de escucha SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="fbbb9-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fbbb9-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="fbbb9-121">See also</span></span>
- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>

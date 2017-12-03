---
title: '&lt;diagnostics&gt; para Activation'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1610c77125d2820e3adc06b3c37177058c85abdd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltdiagnosticsgt-for-activation"></a><span data-ttu-id="d818e-102">&lt;diagnostics&gt; para Activation</span><span class="sxs-lookup"><span data-stu-id="d818e-102">&lt;diagnostics&gt; for Activation</span></span>
<span data-ttu-id="d818e-103">Configura las funcionalidades del diagnóstico de agente de escucha [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d818e-103">Configures [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="d818e-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="d818e-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="d818e-105">\<diagnóstico ></span><span class="sxs-lookup"><span data-stu-id="d818e-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d818e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d818e-106">Syntax</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <diagnostics performanceCountersEnabled="Boolean" />  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## <a name="type"></a><span data-ttu-id="d818e-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="d818e-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d818e-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d818e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d818e-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d818e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d818e-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="d818e-110">Attributes</span></span>  
  
|<span data-ttu-id="d818e-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="d818e-111">Attribute</span></span>|<span data-ttu-id="d818e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d818e-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="d818e-113">Un valor booleano que indica si los contadores de rendimiento están habilitados para el diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="d818e-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d818e-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d818e-114">Child Elements</span></span>  
 <span data-ttu-id="d818e-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d818e-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d818e-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d818e-116">Parent Elements</span></span>  
  
|<span data-ttu-id="d818e-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="d818e-117">Element</span></span>|<span data-ttu-id="d818e-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="d818e-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d818e-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="d818e-119">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="d818e-120">Contiene la configuración para el proceso de agente de escucha SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="d818e-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d818e-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="d818e-121">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>

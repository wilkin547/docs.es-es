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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 29f2e56dd18da9dc3ce3206f5c3c80f4a47a7ff0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltdiagnosticsgt-for-activation"></a><span data-ttu-id="e1ac5-102">&lt;diagnostics&gt; para Activation</span><span class="sxs-lookup"><span data-stu-id="e1ac5-102">&lt;diagnostics&gt; for Activation</span></span>
<span data-ttu-id="e1ac5-103">Configura las funcionalidades del diagnóstico de agente de escucha [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1ac5-103">Configures [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="e1ac5-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="e1ac5-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="e1ac5-105">\<diagnóstico ></span><span class="sxs-lookup"><span data-stu-id="e1ac5-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1ac5-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e1ac5-106">Syntax</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <diagnostics performanceCountersEnabled="Boolean" />  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## <a name="type"></a><span data-ttu-id="e1ac5-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="e1ac5-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1ac5-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e1ac5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e1ac5-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e1ac5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1ac5-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="e1ac5-110">Attributes</span></span>  
  
|<span data-ttu-id="e1ac5-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="e1ac5-111">Attribute</span></span>|<span data-ttu-id="e1ac5-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1ac5-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="e1ac5-113">Un valor booleano que indica si los contadores de rendimiento están habilitados para el diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="e1ac5-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e1ac5-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e1ac5-114">Child Elements</span></span>  
 <span data-ttu-id="e1ac5-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e1ac5-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e1ac5-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e1ac5-116">Parent Elements</span></span>  
  
|<span data-ttu-id="e1ac5-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="e1ac5-117">Element</span></span>|<span data-ttu-id="e1ac5-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1ac5-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e1ac5-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="e1ac5-119">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="e1ac5-120">Contiene la configuración para el proceso de agente de escucha SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="e1ac5-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e1ac5-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1ac5-121">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>

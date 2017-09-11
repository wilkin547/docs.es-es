---
title: "Mitigación: Valor de configuración minFreeMemoryPercentageToActiveService"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a7875f26-0da8-4afe-9846-7a21778f757b
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f7f228890476d45517a21bc09806538139c5e389
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-minfreememorypercentagetoactiveservice-configuration-setting"></a><span data-ttu-id="a072d-102">Mitigación: Valor de configuración minFreeMemoryPercentageToActiveService</span><span class="sxs-lookup"><span data-stu-id="a072d-102">Mitigation: minFreeMemoryPercentageToActiveService Configuration Setting</span></span>
<span data-ttu-id="a072d-103">En [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], se produce una excepción si la memoria disponible en el servidor web es menor que el porcentaje especificado por la opción de configuración [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md).</span><span class="sxs-lookup"><span data-stu-id="a072d-103">In the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], an exception is thrown if the available memory on the web server is less than the percentage specified by the [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) configuration setting.</span></span> <span data-ttu-id="a072d-104">En [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], este valor se omite.</span><span class="sxs-lookup"><span data-stu-id="a072d-104">In the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], this setting was ignored.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="a072d-105">Impacto</span><span class="sxs-lookup"><span data-stu-id="a072d-105">Impact</span></span>  
 <span data-ttu-id="a072d-106">En la mayoría de los casos, el impacto de aplicar la opción [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) es deseable: mejora la estabilidad del sistema al evitar las excepciones <xref:System.OutOfMemoryException> que pueden aparecer cuando se inicia un servicio de Windows Communication Foundation (WCF) en un sistema que tiene memoria restringida.</span><span class="sxs-lookup"><span data-stu-id="a072d-106">In most cases, the impact of observing the [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) setting is desirable: It improves system stability by preventing the <xref:System.OutOfMemoryException> exceptions that can occur when a Windows Communication Foundation (WCF) service is started on a system that has constrained memory.</span></span>  
  
 <span data-ttu-id="a072d-107">Sin embargo, en algunos casos, es posible que un servicio iniciado correctamente con anterioridad no se pueda iniciar.</span><span class="sxs-lookup"><span data-stu-id="a072d-107">However, in some cases, a service that previously started successfully may be unable to start.</span></span> <span data-ttu-id="a072d-108">En ese caso, aparece un mensaje de error detallado:</span><span class="sxs-lookup"><span data-stu-id="a072d-108">In that case, a detailed error message appears:</span></span>  
  
```console
Memory gates checking failed because the free memory (nnnn bytes) is less than nn% of total memory. As a result, the service will not be available for incoming requests. To resolve this, either reduce the load on the machine or adjust the value of minFreeMemoryPercentageToActivateService on the serviceHostingEnvironment config element.
```
  
## <a name="mitigation"></a><span data-ttu-id="a072d-109">Mitigación</span><span class="sxs-lookup"><span data-stu-id="a072d-109">Mitigation</span></span>  
 <span data-ttu-id="a072d-110">Para revertir al comportamiento anterior, donde se omitía la configuración [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md), modifique el archivo web.config de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="a072d-110">To revert to the previous behavior where the [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) setting was ignored, modify the web.config file as follows:</span></span>  
  
```xml
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"   
                           minFreeMemoryPercentageToActivateService="0">  
   <serviceActivations>  
   ...  
   </serviceActivations>  
</serviceHostingEnvironment>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a072d-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="a072d-111">See Also</span></span>  
 [<span data-ttu-id="a072d-112">Cambios en el runtime</span><span class="sxs-lookup"><span data-stu-id="a072d-112">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)


---
title: "Mitigaci&#243;n: Valor de configuraci&#243;n minFreeMemoryPercentageToActiveService | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a7875f26-0da8-4afe-9846-7a21778f757b
caps.latest.revision: 4
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 4
---
# Mitigaci&#243;n: Valor de configuraci&#243;n minFreeMemoryPercentageToActiveService
En [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], se produce una excepción si la memoria disponible en el servidor web es menor que el porcentaje especificado por la opción de configuración [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md).  En [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], este valor se omite.  
  
## Impacto  
 En la mayoría de los casos, el impacto de aplicar la opción [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) es deseable: mejora la estabilidad del sistema evitando las excepciones <xref:System.OutOfMemoryException> que pueden aparecer cuando se inicia un servicio de Windows Communication Foundation \(WCF\) en un sistema que tiene memoria restringida.  
  
 Sin embargo, en algunos casos, es posible que un servicio iniciado correctamente con anterioridad no se pueda iniciar.  En ese caso, aparece un mensaje de error detallado:  
  
```Output  
  
Error en la comprobación de las puertas de memoria, la memoria libre (nnnn bytes) es menor que el nn% de la memoria total.  Como resultado, el servicio no estará disponible para las solicitudes entrantes.  Para solucionarlo, reduzca la carga del equipo o ajuste el valor de minFreeMemoryPercentageToActivateService en el elemento de configuración serviceHostingEnvironment.    
```  
  
## Mitigación  
 Para revertir al comportamiento anterior, donde se omitía la opción [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md), modifique el archivo web.config de la manera siguiente:  
  
```  
  
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"   
                           minFreeMemoryPercentageToActivateService="0">  
   <serviceActivations>  
   ...  
   </serviceActivations>  
</serviceHostingEnvironment>  
  
```  
  
## Vea también  
 [Cambios en tiempo de ejecución](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)
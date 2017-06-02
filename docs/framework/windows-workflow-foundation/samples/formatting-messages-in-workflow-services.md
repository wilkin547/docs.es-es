---
title: "Dar formato a mensajes en servicios de flujo de trabajo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6d15d44b-20f8-4cb7-bd4f-598c32781ebc
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Dar formato a mensajes en servicios de flujo de trabajo
En este ejemplo se muestra cómo se pueden utilizar diferentes tipos de usuario en actividades de mensajería \(servicios de WF\).El servicio del ejemplo es un servicio de aprobación de gastos simple y expone tres operaciones.`ApproveExpense` toma un tipo de contrato de datos y muestra cómo usar tipos conocidos.La operación devuelve `true` o `false` según la cantidad de gastos.`ApprovePO` toma un tipo XmlSerializer y devuelve `true` o `false` en función del importe del gasto. `ApprovedVendor` toma un tipo de contrato de mensaje y devuelve `true` o `false` si el proveedor está en la lista de proveedores autorizados o si la solicitud procede del departamento de finanzas \(el departamento de la finanzas puede usar cualquier proveedor\).  
  
#### Para utilizar este ejemplo  
  
1.  Cargue la solución de proyecto en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] y compile el proyecto.  
  
2.  En primer lugar, ejecute el servicio generado en \[directorio base de la solución\] \\FormatterService\\bin\\debug\\  
  
3.  En segundo lugar, ejecute la aplicación Client generada en \[directorio base de la solución\] \\FormatterClient\\bin\\debug.  
  
4.  El cliente llama a tres operaciones del servicio e imprime los resultados.Cuando se haya completado, presione Entrar para salir del cliente y a continuación del servicio.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\Services\Formatter`  
  
## Vea también
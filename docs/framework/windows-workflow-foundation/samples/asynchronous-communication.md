---
title: "Comunicaci&#243;n asincr&#243;nica | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Comunicaci&#243;n asincr&#243;nica
En este ejemplo se muestra cómo se realiza asincrónicamente de forma predeterminada la comunicación entre dos servicios de [!INCLUDE[wf](../../../../includes/wf-md.md)] diferentes.  
  
## Demostraciones  
 Comunicación asincrónica entre servicios de [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  
  
## Análisis  
 En este ejemplo se muestra cómo la comunicación entre aplicaciones de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] se realiza de forma asincrónica utilizando las actividades de mensajería proporcionadas por .NET Framework.  
  
 Este ejemplo consta de los tres proyectos siguientes.  
  
 CreditCheckService  
 Este servicio recibe la puntuación crediticia de una persona determinada o el valor del elemento que se va a adquirir y a continuación, decide si la persona recibe el crédito.  
  
 RentalApprovalService  
 Este servicio recibe una solicitud de una persona que necesita crédito.Este servicio se comunica de forma asincrónica con `CreditCheckService` para decidir si la solicitud de crédito es válida.  
  
 Client  
 El cliente se comunica sincrónicamente con `RentalApprovalService` para saber si se aprueba el crédito.  
  
#### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Haga clic con el botón secundario en la solución **AsynchronousCommunication** y seleccione **Propiedades**.  
  
2.  En **Propiedades comunes**, seleccione **Proyecto de inicio** y, a continuación, seleccione **Varios proyectos de inicio**.  
  
3.  Mueva **RentalApprovalService** a la primera posición de la lista, seguido de **CreditCheckService** y seguido de **Client**.Establezca la acción **Iniciar** en los tres proyectos.  
  
4.  Haga clic en **Aceptar** y presione F5 para ejecutar el ejemplo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`
---
title: Comunicación asincrónica
ms.date: 03/30/2017
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
ms.openlocfilehash: 9eafeab89aefb181ae016dc0219f9155d9bd2a25
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="asynchronous-communication"></a>Comunicación asincrónica
Este ejemplo muestra cómo la comunicación entre dos servicios diferentes de Windows Workflow Foundation (WF) se realiza asincrónicamente de forma predeterminada.  
  
## <a name="demonstrates"></a>Demostraciones  
 Comunicación asincrónica entre servicios de [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  
  
## <a name="discussion"></a>Explicación  
 En este ejemplo se muestra cómo la comunicación entre aplicaciones de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] se realiza de forma asincrónica utilizando las actividades de mensajería proporcionadas por .NET Framework.  
  
 Este ejemplo consta de los tres proyectos siguientes.  
  
 CreditCheckService  
 Este servicio recibe la puntuación crediticia de una persona determinada o el valor del elemento que se va a adquirir y a continuación, decide si la persona recibe el crédito.  
  
 RentalApprovalService  
 Este servicio recibe una solicitud de una persona que necesita crédito. Este servicio se comunica de forma asincrónica con `CreditCheckService` para decidir si la solicitud de crédito es válida.  
  
 Cliente  
 El cliente se comunica sincrónicamente con `RentalApprovalService` para saber si se aprueba el crédito.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Haga clic en el **AsynchronousCommunication** solución y seleccione **propiedades**.  
  
2.  En **propiedades comunes**, seleccione **proyecto de inicio**y seleccione **proyectos de inicio múltiples**.  
  
3.  Mover **RentalApprovalService** a la primera posición en la lista, seguido por **CreditCheckService**, seguido de **cliente**. Establecer el **iniciar** acción en los tres proyectos.  
  
4.  Haga clic en **Aceptar**, y presione F5 para ejecutar el ejemplo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`

---
title: "Uso de TransactedReceiveScope | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d455f1dc-bfc5-43d6-8ae9-bc3b3a3ea08a
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Uso de TransactedReceiveScope
En este ejemplo se muestra cómo pasar una transacción de un cliente a un servidor utilizando <xref:System.Activities.Statements.TransactionScope> para crear una transacción en el cliente y <xref:System.ServiceModel.Activities.TransactedReceiveScope> para recibir un mensaje con una transacción de flujo y determinar la duración de la transacción en el servidor.El ejemplo consta de dos proyectos que representan los roles de cliente y servidor.  
  
## Aplicación de cliente  
 La aplicación cliente ejecuta un flujo de trabajo que imprime el Id. de la transacción distribuida, envía un mensaje al servidor, pasa la transacción, recibe la respuesta, imprime de nuevo el Id. de la transacción distribuida y finaliza.Cuando el Id. de la transacción distribuida se imprime inicialmente, es un GUID vacío, puesto que la transacción es todavía solo local.  
  
## Servidor de aplicaciones  
 El proyecto de servidor es similar; sin embargo, el flujo de trabajo se hospeda en <xref:System.ServiceModel.Activities.WorkflowServiceHost> porque debe realizar escuchas en un extremo del mensaje procedente del cliente.El flujo de trabajo se centra en el objeto <xref:System.ServiceModel.Activities.TransactedReceiveScope>, que recibe la transacción de flujo del cliente, imprime el mensaje que se envió, imprime el Id. de la transacción distribuida y envía la respuesta al cliente.El Id. de la transacción distribuida es ahora un GUID que no está vacío y si se agregara una actividad que tenga en cuenta las transacciones al cuerpo de <xref:System.ServiceModel.Activities.TransactedReceiveScope>, se ejecutaría bajo la transacción de flujo.  
  
#### Para ejecutar el ejemplo  
  
1.  Abra la solución TransactedReceiveScope.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Para compilar la solución, presione CTRL\+MAYÚS\+B o seleccione **Compilar solución** en el menú **Compilar**.  
  
3.  Cuando la compilación se complete correctamente, haga clic con el botón secundario en la solución y seleccione **Establecer proyectos de inicio**.En el cuadro de diálogo, seleccione **Proyectos de inicio múltiples** y asegúrese de que la acción para ambos proyectos es **Iniciar**.  
  
4.  Presione F5 o seleccione **Iniciar depuración** en el menú **Depurar**.También, puede presionar CTRL\+F5 o seleccionar **Iniciar sin depurar** en el menú **Depurar** para realizar la ejecución sin depuración.  
  
    > [!NOTE]
    >  El servidor debe estar en ejecución antes de iniciar el cliente.El resultado de la ventana de la consola que hospeda el servicio indica cuándo se ha iniciado.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\Transactions\TransactedReceiveScope`  
  
## Vea también
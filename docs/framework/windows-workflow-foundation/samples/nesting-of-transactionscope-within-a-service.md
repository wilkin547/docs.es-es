---
title: "Anidamiento de TransactionScope dentro de un servicio | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e7e1ba64-1384-4eba-add8-415636e2d6d0
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Anidamiento de TransactionScope dentro de un servicio
Este ejemplo consiste en la ejecución de dos escenarios para mostrar cómo administrar instancias de actividad <xref:System.Activities.Statements.TransactionScope> dentro de un servicio.En primer lugar, la transacción se inicia utilizando la actividad <xref:System.Activities.Statements.TransactionScope> para crear una transacción en el cliente y <xref:System.ServiceModel.Activities.TransactedReceiveScope> para recibir y determinar la duración de la transacción en el servidor.El primer escenario dentro del servicio ejecuta una actividad <xref:System.Activities.Statements.TransactionScope> secundaria para mostrar el anidamiento de las actividades <xref:System.Activities.Statements.TransactionScope> dentro del servicio.El segundo escenario muestra cómo se respetan los tiempos de espera dentro de las actividades <xref:System.Activities.Statements.TransactionScope> anidadas.  
  
## Aplicación de cliente  
 La aplicación cliente ejecuta un flujo de trabajo que inicia una actividad <xref:System.Activities.Statements.TransactionScope>, imprime el Id. de la transacción distribuida, envía un mensaje al servidor, pasa la transacción, recibe la respuesta, imprime de nuevo el Id. de la transacción distribuida y finaliza.Esto lo realiza una vez para cada escenario de servicio.  
  
## Servidor de aplicaciones  
 El proyecto de servidor se hospeda en <xref:System.ServiceModel.Activities.WorkflowServiceHost>, que crea el extremo para escuchar el mensaje del cliente.El flujo de trabajo se centra en <xref:System.ServiceModel.Activities.TransactedReceiveScope>, que recibe la transacción de flujo del cliente, imprime el Id. de la transacción distribuida y, a continuación, ejecuta una segunda actividad <xref:System.Activities.Statements.TransactionScope>.En el primer escenario, la transacción se completa correctamente.En el segundo escenario, el cuerpo de la actividad <xref:System.Activities.Statements.TransactionScope> es un retraso de cinco segundos y el tiempo de espera para la transacción se establece en dos segundos.Cuando la transacción supera el tiempo de espera, se anula.  
  
#### Para ejecutar el ejemplo  
  
1.  Abra la solución TransactionServiceExample.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Para compilar la solución, presione CTRL\+MAYÚS\+B o seleccione **Compilar solución** en el menú **Compilar**.  
  
3.  Cuando la compilación se complete correctamente, haga clic con el botón secundario en la solución y seleccione **Establecer proyectos de inicio**.En el cuadro de diálogo, seleccione **Proyectos de inicio múltiples** y asegúrese de que la acción para ambos proyectos es **Iniciar**.  
  
4.  Presione F5 o seleccione **Iniciar depuración** en el menú **Depurar**.También, puede presionar CTRL\+F5 o seleccionar **Iniciar sin depurar** en el menú **Depurar** para realizar la ejecución sin depuración.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\Transactions\TRSComposability`
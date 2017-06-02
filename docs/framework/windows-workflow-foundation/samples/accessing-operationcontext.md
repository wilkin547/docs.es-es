---
title: "Obtener acceso a OperationContext | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4e92efe8-7e79-41f3-b50e-bdc38b9f41f8
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Obtener acceso a OperationContext
En este ejemplo se muestra cómo se pueden utilizar las actividades de mensajería \(<xref:System.ServiceModel.Activities.Receive> y <xref:System.ServiceModel.Activities.Send>\) con una actividad de ámbito personalizada para tener acceso a <xref:System.ServiceModel.OperationContext.Current%2A> y adjuntar o recuperar un encabezado de mensaje personalizado dentro de un mensaje de salida o entrante.  
  
## Demostraciones  
 Actividades de mensajería, <xref:System.ServiceModel.Activities.ISendMessageCallback>, <xref:System.ServiceModel.Activities.IReceiveMessageCallback>.  
  
## Análisis  
 En este ejemplo se muestra cómo utilizar puntos de extensibilidad \(<xref:System.ServiceModel.Activities.ISendMessageCallback> y <xref:System.ServiceModel.Activities.IReceiveMessageCallback>\) en las actividades de mensajería para tener acceso a <xref:System.ServiceModel.OperationContext.Current%2A>.Las devoluciones de llamada se registran dentro del tiempo de ejecución del flujo de trabajo como una implementación de <xref:System.Activities.IExecutionProperty> que utilizan las actividades de mensajería en la ejecución.Se ven afectadas todas las actividades de mensajería incluidas en el mismo ámbito que la implementación de <xref:System.Activities.IExecutionProperty>.Concretamente, en este ejemplo se utiliza una actividad de ámbito personalizada para exigir el comportamiento de devolución de llamada.En el flujo de trabajo del cliente se utiliza la interfaz <xref:System.ServiceModel.Activities.ISendMessageCallback> para incluir la propiedad <xref:System.Activities.WorkflowApplication.Id%2A> del flujo de trabajo como una clase <xref:System.ServiceModel.Channels.MessageHeader> de salida.A continuación, este encabezado se utiliza en el servicio mediante la interfaz <xref:System.ServiceModel.Activities.IReceiveMessageCallback>, y su valor se imprime en la consola.  
  
#### Para configurar, compilar y ejecutar el ejemplo  
  
1.  En este ejemplo se expone un servicio del flujo de trabajo mediante extremos HTTP.Para realizar este ejemplo, se deben agregar listas de control de acceso de dirección URL adecuadas \(vea [Configuración de HTTP y HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) para obtener más información\) ejecutando Visual Studio como administrador o el siguiente comando en una ventana de símbolo del sistema elevado para agregar las listas de control de acceso adecuadas.Asegúrese de que su dominio y su nombre de usuario se sustituyen.  
  
    ```  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2.  Una vez agregadas las listas de control de acceso de dirección URL, siga estos pasos.  
  
    1.  Compile la solución.  
  
    2.  Establezca varios proyectos de inicio haciendo clic con el botón secundario en la solución y seleccionando **Establecer proyectos de inicio**.  
  
    3.  Agregue **Service** y **Client** \(en ese orden\) como proyectos de inicio múltiples.  
  
    4.  Ejecute la aplicación.La consola del cliente muestra un flujo de trabajo que se ejecuta dos veces y la ventana Service muestra el identificador de instancia de estos flujos de trabajo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Scenario\Services\Accessing Operation Context`
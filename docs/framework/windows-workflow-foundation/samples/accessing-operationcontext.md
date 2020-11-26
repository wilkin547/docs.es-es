---
title: Obtener acceso a OperationContext
ms.date: 03/30/2017
ms.assetid: 4e92efe8-7e79-41f3-b50e-bdc38b9f41f8
ms.openlocfilehash: 5cffae101c5d39fcc9500aa7ccafde7a836a5023
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245736"
---
# <a name="accessing-operationcontext"></a>Obtener acceso a OperationContext

Este ejemplo muestra cómo se pueden utilizar las actividades de mensajería ( <xref:System.ServiceModel.Activities.Receive> y <xref:System.ServiceModel.Activities.Send> ) con una actividad de ámbito personalizada para tener acceso <xref:System.ServiceModel.OperationContext.Current%2A> y adjuntar o recuperar un encabezado de mensaje personalizado dentro de un mensaje saliente o entrante.  
  
## <a name="demonstrates"></a>Muestra  

 Actividades de mensajería, <xref:System.ServiceModel.Activities.ISendMessageCallback>, <xref:System.ServiceModel.Activities.IReceiveMessageCallback>.  
  
## <a name="discussion"></a>Discusión  

 En este ejemplo se muestra cómo utilizar puntos de extensibilidad (<xref:System.ServiceModel.Activities.ISendMessageCallback> y <xref:System.ServiceModel.Activities.IReceiveMessageCallback>) en las actividades de mensajería para tener acceso a <xref:System.ServiceModel.OperationContext.Current%2A>. Las devoluciones de llamada se registran dentro del tiempo de ejecución del flujo de trabajo como una implementación de <xref:System.Activities.IExecutionProperty> que utilizan las actividades de mensajería en la ejecución. Se ven afectadas todas las actividades de mensajería incluidas en el mismo ámbito que la implementación de <xref:System.Activities.IExecutionProperty>. Concretamente, en este ejemplo se utiliza una actividad de ámbito personalizada para exigir el comportamiento de devolución de llamada. En el flujo de trabajo del cliente se utiliza la interfaz <xref:System.ServiceModel.Activities.ISendMessageCallback> para incluir la propiedad <xref:System.Activities.WorkflowApplication.Id%2A> del flujo de trabajo como una clase <xref:System.ServiceModel.Channels.MessageHeader> de salida. A continuación, este encabezado se utiliza en el servicio mediante la interfaz <xref:System.ServiceModel.Activities.IReceiveMessageCallback>, y su valor se imprime en la consola.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. En este ejemplo se expone un servicio del flujo de trabajo mediante puntos de conexión HTTP. Para ejecutar este ejemplo, se deben agregar las ACL de dirección URL adecuadas (consulte [configuración de http y https](../../wcf/feature-details/configuring-http-and-https.md) para obtener detalles), ya sea ejecutando Visual Studio como administrador o ejecutando el siguiente comando en un símbolo del sistema con privilegios elevados para agregar las ACL adecuadas. Asegúrese de que su dominio y su nombre de usuario se sustituyen.  
  
    ```console  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2. Una vez agregadas las listas de control de acceso de dirección URL, siga estos pasos.  
  
    1. Compile la solución.  
  
    2. Establezca varios proyectos de inicio haciendo clic con el botón derecho en la solución y seleccionando **establecer proyectos de inicio**.  
  
    3. Agregue el **servicio** y el **cliente** (en ese orden) como varios proyectos de inicio.  
  
    4. Ejecute la aplicación. La consola del cliente muestra un flujo de trabajo que se ejecuta dos veces y la ventana Service muestra el identificador de instancia de estos flujos de trabajo.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\Accessing Operation Context`

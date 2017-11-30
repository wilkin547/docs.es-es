---
title: Retraso duradero
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 220ec240-b958-430c-81ff-b734a6aa97ae
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a7023d7548db99d511ae18ad4d52b9a8168c4243
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="durable-delay"></a>Retraso duradero
En este ejemplo se muestra cómo utilizar un retraso duradero, que es un retraso que conserva el flujo de trabajo en un dispositivo duradero durante el tiempo que dura. El flujo de trabajo de muestra contiene dos mensajes a la consola, separados por un retraso. Cuando el retraso se activa, el flujo de trabajo se descarga y espera 5 segundos en el almacén de instancias de flujo de trabajo antes de recargarse en la memoria.  
  
## <a name="workflow-details"></a>Detalles del flujo de trabajo  
 El host de servicio de flujo de trabajo hospeda el flujo de trabajo y administra las instancias de flujo de trabajo cargándolas y descargándolas. Para iniciar una instancia de la definición de flujo de trabajo, el ejemplo establece un proxy que envía un mensaje a la actividad <xref:System.ServiceModel.Activities.Receive> del flujo de trabajo. La propiedad <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> se establece en `true`, lo que permite crear una nueva instancia del flujo de trabajo después de recibir un mensaje.  
  
 La siguiente lista detalla la configuración que realiza el host de servicio de flujo de trabajo durante la inicialización.  
  
1.  Crea un host del servicio con una dirección (http://localhost:8080/Client).  
  
2.  Crea un extremo en el host de servicio para habilitar la comunicación con la actividad <xref:System.ServiceModel.Activities.Receive> dentro del flujo de trabajo.  
  
3.  Configura un almacén de instancias de SQL.  
  
4.  Agrega un comportamiento de instancia de descarga que especifica las condiciones bajo las que el host de servicio de flujo de trabajo debe descargar una instancia de flujo de trabajo al almacén de persistencia de SQL. En este ejemplo, descarga la instancia de forma inmediata cuando el flujo de trabajo pasa a estado inactivo (cuando el retraso se activa).  
  
5.  Crea el proxy que envía un mensaje a la actividad <xref:System.ServiceModel.Activities.Receive> del flujo de trabajo.  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Configure la base de datos de persistencia.  
  
    1.  Abra un símbolo del sistema de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
    2.  Navegue hasta la [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] directorio (C:\Windows\Microsoft.NET\Framework\v4. X\\).  
  
    3.  Edite el archivo WorkflowManagementService.exe.config y agregue la siguiente cadena de conexión dentro del elemento <`database`>.  
  
        ```xml  
        <database connectionString="Data Source=localhost\SQLEXPRESS;Initial Catalog=DefaultSampleStore;Integrated Security=True;Asynchronous Processing=True" />  
        ```  
  
    4.  Desplácese hasta el directorio DurableDelay\CS.  
  
    5.  Ejecute Setup.cmd.  
  
2.  Ejecutar [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con permisos elevados haciendo clic en el [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icono y seleccione **ejecutar como administrador**.  
  
3.  Abra el archivo de solución Delay.sln.  
  
4.  Presione Ctrl+MAYÚS+B para compilar la solución.  
  
5.  Presione CTRL+F5 para ejecutar la solución.  
  
#### <a name="to-uninstall-this-sample"></a>Para desinstalar este ejemplo  
  
1.  Abra un símbolo del sistema de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Desplácese hasta el directorio DurableDelay\CS.  
  
3.  Ejecute Cleanup.cmd.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelay`  
  
## <a name="see-also"></a>Vea también

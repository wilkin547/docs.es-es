---
title: "Conservar una aplicación de flujo de trabajo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: abcff14c-f047-4195-ba26-d27f4a82c24e
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 16251bcf5ceb9660fc4854c8e46bc376de9f01ef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="persisting-a-workflow-application"></a>Conservar una aplicación de flujo de trabajo
En este ejemplo se muestra cómo ejecutar un objeto <xref:System.Activities.WorkflowApplication>, cómo descargarlo cuando pasa a estado inactivo, y cómo recargarlo después para continuar su ejecución.  
  
## <a name="sample-details"></a>Detalles del ejemplo  
 <xref:System.Activities.WorkflowApplication> es un host para una instancia de flujo de trabajo única que proporciona una interfaz simple y habilita varios de los escenarios de hospedaje más comunes. Uno de estos escenarios son los flujos de trabajo de ejecución prolongada facilitados por la persistencia. El control host de la persistencia se realiza llamando a una operación de persistencia en <xref:System.Activities.WorkflowApplication>o administrando un evento <xref:System.Activities.WorkflowApplication> e indicando que <xref:System.Activities.WorkflowApplication> debe conservarse.  
  
 El flujo de trabajo de ejemplo es una actividad <xref:System.Activities.Statements.WriteLine> que pregunta al usuario su nombre, una actividad `ReadLine` para recibir el nombre como entrada a través de la reanudación de un <xref:System.Activities.Bookmark> y otro objeto <xref:System.Activities.Statements.WriteLine> para devolver un saludo al usuario. Cuando un flujo de trabajo está esperando por la entrada, esto proporciona un punto natural para la persistencia. Esto se conoce a menudo como punto de <xref:System.Workflow.Runtime.Tracking.TrackingWorkflowEvent.Idle>. <xref:System.Activities.WorkflowApplication> genera el evento <xref:System.Workflow.Runtime.Tracking.TrackingWorkflowEvent.Idle> siempre que el programa de flujo de trabajo se pueda conservar, esté esperando una reanudación del marcador y no se realice ningún otro trabajo. En el flujo de trabajo de este ejemplo, ese punto viene inmediatamente después del comienzo de la ejecución de la actividad `ReadLine`.  
  
 A <xref:System.Activities.WorkflowApplication> está configurado para realizar la persistencia con un <!--zz <xref:System.Runtime.Persistence.InstanceStore> --> `System.Runtime.Persistence.InstanceStore`. Este ejemplo utiliza <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>. El <!--zz <xref:System.Runtime.Persistence.InstanceStore> --> `System.Runtime.Persistence.InstanceStore` deben asignarse a la <xref:System.Activities.WorkflowApplication.InstanceStore%2A> propiedad antes de la <xref:System.Activities.WorkflowApplication> se ejecuta.  
  
 En el ejemplo se agrega un controlador al evento <xref:System.Activities.WorkflowApplication.PersistableIdle%2A>. El controlador de este evento indica lo que <xref:System.Activities.WorkflowApplication> debe hacer devolviendo un objeto <xref:System.Activities.PersistableIdleAction>. Cuando se devuelve <xref:System.Activities.PersistableIdleAction.Unload>, se descarga el objeto <xref:System.Activities.WorkflowApplication>.  
  
 A continuación, el ejemplo acepta la entrada del usuario y carga el flujo de trabajo conservado en un nuevo <xref:System.Activities.WorkflowApplication>. Lo hace mediante la creación de un nuevo <xref:System.Activities.WorkflowApplication>, volviendo a crear la <!--zz <xref:System.Runtime.Persistence.InstanceStore> --> `System.Runtime.Persistence.InstanceStore`y asociar los eventos descargados y completados a la instancia y, a continuación, llamar a <xref:System.Activities.WorkflowApplication.Load%2A> con el identificador de la instancia de flujo de trabajo de destino. Una vez adquirida la instancia, el marcador de la actividad `ReadLine` se reanuda. El flujo de trabajo realiza la ejecución desde la actividad `ReadLine` y se ejecuta hasta su finalización. Cuando se completa el flujo de trabajo y se descarga, el <!--zz <xref:System.Runtime.Persistence.InstanceStore> --> `System.Runtime.Persistence.InstanceStore` se llama por última vez para eliminar el flujo de trabajo.  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Abra un símbolo del sistema de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
     En este ejemplo se requiere SQL Server Express, que se instala de forma predeterminada con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Navegue hasta el directorio de ejemplo (\WF\Basic\Persistence\InstancePersistence\CS) y ejecute CreateInstanceStore.cmd.  
  
    > [!CAUTION]
    >  El script CreateInstanceStore.cmd intenta crear la base de datos en la instancia predeterminada de SQL Server 2008 Express. Si desea instalar la base de datos en una instancia diferente, modifique el script.  
  
3.  Abra el archivo de solución Persistence.sln con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] y presione CTRL+SHIFT+B para compilarlo.  
  
    > [!CAUTION]
    >  Si instaló la base de datos en una instancia no predeterminada de SQL Server, actualice la cadena de conexión en el código antes de compilar la solución.  
  
4.  Ejecutar el ejemplo con privilegios de administrador, desplácese hasta el directorio de bin del proyecto (\WF\Basic\Persistence\InstancePersistence\bin\Debug) en [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], con el botón secundario Workflow.exe y seleccionando **ejecutar como administrador**.  
  
#### <a name="to-remove-the-instance-store-database"></a>Para quitar la base de datos del almacén de instancias  
  
1.  Abra un símbolo del sistema de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Navegue hasta el directorio de ejemplo y ejecute RemoveInstanceStore.cmd.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\InstancePersistence`  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de persistencia y el hospedaje de AppFabric](http://go.microsoft.com/fwlink/?LinkId=193961)

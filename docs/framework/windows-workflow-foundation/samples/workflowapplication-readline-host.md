---
title: Host RedLIne WorkflowApplication
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7b362be-cb42-40d7-b9ef-cfc4aed2455b
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a65ca3d3d4a787132246312e28213e71defc94ec
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="workflowapplication-readline-host"></a>Host RedLIne WorkflowApplication
Este ejemplo es un host ReadLine genérico. Puede cargar y ejecutar cualquier flujo de trabajo mediante la actividad `ReadLine` incluida (u otras actividades similares que reciban datos de marcadores reanudados con cadenas). El resultado de la actividad `WriteLine` o cualquier escritura que se realice en la extensión <xref:System.Activities.Statements.WriteLine.TextWriter%2A> se dirige a la ventana del host. Cuando una instancia está inactiva, los marcadores disponibles para esa instancia aparecen en un cuadro combinado. Seleccione un marcador, escriba algún texto o presione el botón de reanudación del marcador para continuar con la ejecución del flujo de trabajo. También puede cancelar, anular o finalizar un flujo de trabajo seleccionado. La persistencia está activada de forma predeterminada; puede cerrar el host y volver a iniciarlo, y la lista de instancias se rellena con las instancias almacenadas en la base de datos. El seguimiento se utiliza para generar eventos de nivel de <xref:System.Activities.WorkflowApplication> en el host con la opción de agregar seguimiento detallado en el nivel de actividad.  
  
## <a name="sample-details"></a>Detalles del ejemplo  
 Hay dos niveles en este host: la vista y el administrador de instancias. La vista consta de las clases `HostView` y `WorkflowApplicationInfo`. El patrón general para este host es que la clase `HostView` muestre al usuario las opciones disponibles en función de los objetos `WorkflowApplicationInfo` que se mantienen razonablemente en sincronización con las instancias que representan. El nivel de administrador de instancias se compone de la clase `WorkflowApplicationManager`, que es el núcleo de todas las comunicaciones del host, y la clase `WorkflowDefinitionExtension`, que conserva la relación entre una instancia y la definición del programa con el que se inició y algunas otras clases. `HostView` llama a las operaciones de control en `WorkflowApplicationManager`. Estas llamadas suelen ser asincrónicas para mantener una interfaz de usuario que siga respondiendo. Cuando las llamadas asincrónicas se completan, `WorkflowApplicationManager` realiza llamadas en el nivel de vista a través de una interfaz bien definida (`IHostView`). La clase `HostView` a menudo envía estas llamadas de la clase `WorkflowApplicationManager` al subproceso de la interfaz de usuario. La escritura de texto se realiza en los objetos <xref:System.Activities.Statements.WriteLine.TextWriter%2A> seguros para subprocesos proporcionados por la clase `HostView`. La interfaz de usuario no es la única que genera eventos. Los objetos <xref:System.Activities.WorkflowApplication> también señalan a `WorkflowApplicationManager` cuando pasan al estado `Idle`, `Complete` o `Aborted`, por ejemplo. La clase `WorkflowApplicationManager` sale del subproceso de evento enviando el trabajo de limpieza o actualización al host.  
  
 La clase <xref:System.Activities.WorkflowApplication> facilita la grabación del archivo utilizado para iniciar `WorkflowDefinitionExtension`. Implementa la interfaz <xref:System.Activities.Persistence.PersistenceIOParticipant> para participar en la persistencia y conservar la ruta de acceso a la definición de flujo de trabajo.  
  
 El método `WorkflowApplicationManager.Load` utiliza la ruta de acceso almacenada para crear instancias de los programas de flujo de trabajo requeridos para cargar los objetos <xref:System.Activities.WorkflowApplication> inacabados.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  En este ejemplo se requiere instalar SQL Express. SQL Express viene con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Abra un símbolo del sistema de Visual Studio 2010.  
  
3.  Navegue hasta el directorio de ejemplo (\WF\Basic\Execution\ControllingWorkflowApplications) y ejecute CreateInstanceStore.cmd.  
  
4.  El script CreateInstanceStore.cmd intenta crear la base de datos en la instancia predeterminada de SQL Server 2008 Express. Si desea instalar la base de datos en una instancia diferente, modifique el script.  
  
5.  Compile el proyecto WorkflowApplicationReadLineHost y ejecútelo desde la línea de comandos.  
  
6.  Cuando se esté ejecutando, puede optar por activar o desactivar la persistencia. Además, dispone de la opción de activar o desactivar el seguimiento de actividad detallado.  
  
7.  Presione el botón de puntos suspensivos junto a la **ejecutar** botón para examinar un flujo de trabajo definido en un archivo XAML  
  
     En la carpeta SampleWorkflows se pueden encontrar dos ejemplos. El ejemplo parallel1.xaml pasa a estado inactivo.  
  
8.  Una vez seleccionado un ejemplo, presione el **ejecutar** botón.  
  
9. Si o cuando el flujo de trabajo pasa a estado inactivo, el **marcadores** cuadro combinado se rellena con los marcadores disponibles.  
  
10. Las opciones en este punto son reanudar un marcador, cancelar, interrumpir o finalizar el flujo de trabajo. También puede cerrar el host y reiniciarlo. Si la persistencia permanece activada, las instancias se descargan cuando se apaga y se recargan cuando se inicia.  
  
     Para reanudar un marcador, seleccione el marcador deseado, escriba un valor en el cuadro de texto situado junto al cuadro combinado y presione **reanudar marcador**.  
  
#### <a name="to-remove-the-instance-store-database"></a>Para quitar la base de datos del almacén de instancias  
  
1.  Abra un símbolo del sistema de Visual Studio 2010.  
  
2.  Navegue hasta el directorio de ejemplo (\WF\Basic\Execution\ControllingWorkflowApplications) and run RemoveInstanceStore.cmd.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ControllingWorkflowApplications`  
  
## <a name="see-also"></a>Vea también

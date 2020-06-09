---
title: Información interna de extensiones del host de servicio de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: af44596f-bf6a-4149-9f04-08d8e8f45250
ms.openlocfilehash: 7b47293211ee8143b1ce713c64ff1d5b22161b45
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594886"
---
# <a name="workflow-service-host-internals"></a>Información interna de extensiones del host de servicio de flujo de trabajo
La clase <xref:System.ServiceModel.WorkflowServiceHost> proporciona un host para los servicios de flujo de trabajo. Es responsable de escuchar los mensajes entrantes y enrutarlos a la instancia del servicio de flujo de trabajo adecuada, controlar la descarga y persistencia de los flujos de trabajo inactivos, etc. En este tema se describe cómo procesa la clase WorkflowServiceHost los mensajes entrantes.  
  
## <a name="workflowservicehost-overview"></a>Información general de WorkflowServiceHost  

La clase <xref:System.ServiceModel.WorkflowServiceHost> se usa para hospedar los servicios de flujo de trabajo. Escucha los mensajes entrantes y los enruta a la instancia de servicio adecuada. De esta forma, se crean nuevas instancias o se cargan instancias existentes desde un almacenamiento duradero según convenga. En el siguiente diagrama se muestra un alto nivel de cómo <xref:System.ServiceModel.WorkflowServiceHost> funciona:
  
 ![Diagrama que muestra una visión general del host de servicio de flujo de trabajo.](./media/workflow-service-host-internals/workflow-service-host-high-level-overview.gif)  
  
 Este diagrama muestra que la clase <xref:System.ServiceModel.WorkflowServiceHost> carga definiciones de servicio de flujo de trabajo desde archivos .xamlx e información de configuración a partir de un archivo de configuración. También carga la configuración de seguimiento del perfil de seguimiento. <xref:System.ServiceModel.WorkflowServiceHost> expone un extremo de control de flujo de trabajo que le permite enviar operaciones de control a instancias de flujo de trabajo.  Para obtener más información, vea [ejemplo de punto de conexión de control de flujo de trabajo](workflow-control-endpoint.md).  
  
 La clase <xref:System.ServiceModel.WorkflowServiceHost> también expone los extremos de la aplicación que escuchan los mensajes de aplicación entrantes. Cuando un mensaje entrante llega, se envía a la instancia de servicio de flujo de trabajo adecuada, si está cargada actualmente. Si es necesario se crea una nueva instancia de flujo de trabajo. O bien, si se ha conservado una instancia existente, se carga desde el almacén de persistencia.  
  
## <a name="workflowservicehost-details"></a>Detalles de WorkflowServiceHost  
 En el diagrama siguiente se muestra cómo <xref:System.ServiceModel.WorkflowServiceHost> controla los mensajes en un poco más detalle:  
  
 ![Diagrama que muestra el flujo de mensajes del host de servicio de flujo de trabajo.](./media/workflow-service-host-internals/workflow-service-host-message-flow.gif)  
  
 Este diagrama muestra tres extremos distintos: un extremo de la aplicación, un extremo de control de flujo de trabajo y un extremo de hospedaje de flujo de trabajo. El punto de conexión de aplicación recibe los mensajes que se enlazan para una instancia de flujo de trabajo específica. El punto de conexión de control de instancia de flujo de trabajo escucha las operaciones de control. El extremo de hospedaje de flujo de control escucha mensajes que pueden provocar que la clase <xref:System.ServiceModel.WorkflowServiceHost> cargue y ejecute flujos de trabajo no pertenecientes al servicio. Como se muestra en el diagrama, se procesan todos los mensajes a través del tiempo de ejecución de WCF.  La limitación de instancia de servicio de flujo de trabajo se logra mediante el uso de la propiedad <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>. Esta propiedad limitará el número de instancias de servicio de flujo de trabajo simultáneas. Se pondrán en cola las solicitudes adicionales de nuevas instancias de servicio de flujo de trabajo o las solicitudes para activar instancias de flujo de trabajo persistentes cuando se supere este límite. Las solicitudes puestas en cola se procesan en el orden FIFO independientemente de si son para una nueva instancia o para un instancia persistente en ejecución. Se carga la información de directivas de host y se determina cómo se tratan las excepciones no controladas, cómo se descargan los servicios de flujo de trabajo inactivos y cómo se conservan. Para obtener más información acerca de estos temas, consulte [How to: configure Workflow Unhandled Exception Behavior with workflowservicehost](config-workflow-unhandled-exception-workflowservicehost.md) y [How to: configure inidle Behavior with workflowservicehost](how-to-configure-idle-behavior-with-workflowservicehost.md). Las instancias de flujo de trabajo se conservan de acuerdo con las directivas de host y se recargan según convenga. Para obtener más información sobre la persistencia del flujo de trabajo, vea: [Cómo: configurar la persistencia con WorkflowServiceHost](how-to-configure-persistence-with-workflowservicehost.md), [crear un servicio de flujo de trabajo de ejecución prolongada](creating-a-long-running-workflow-service.md)y [persistencia del flujo de trabajo](../../windows-workflow-foundation/workflow-persistence.md).  
  
 En la ilustración siguiente se muestra el flujo cuando se llama a WorkflowServiceHost. Open:  
  
 ![Diagrama que muestra el flujo cuando se llama a WorkflowServiceHost. Open.](./media/workflow-service-host-internals/workflow-service-host-open.gif)  
  
 Se carga el flujo de trabajo desde XAML y se crea el árbol de actividad. <xref:System.ServiceModel.WorkflowServiceHost> recorre el árbol de actividad y crea la descripción del servicio. La configuración se aplica al host. Finalmente, el host empieza a escuchar los mensajes entrantes.  
  
 En la ilustración siguiente se muestra lo que <xref:System.ServiceModel.WorkflowServiceHost> hace cuando recibe un mensaje enlazado para una actividad Receive que tiene CanCreateInstance establecido en `true` :  
  
 ![Árbol de decisión usado por el host de ft cuando recibe un mensaje y CanCreateInstance es true.](./media/workflow-service-host-internals/workflow-service-host-receive-message-cancreateinstance.gif)  
  
 El mensaje llega y lo procesa la pila del canal WCF. Se comprueban los límites y se ejecutan las consultas de correlación. Si el mensaje se enlaza para una instancia existente, el mensaje se entrega. Si se debe crear una nueva instancia, se comprueba la propiedad CanCreateInstance de la actividad Receive. Si su valor se establece en true, se crea una nueva instancia y se entrega el mensaje.  
  
 En la siguiente ilustración se muestra lo que hace la clase <xref:System.ServiceModel.WorkflowServiceHost> cuando recibe un mensaje enlazado para una actividad Receive con el valor de CanCreateInstance establecido en false.  
  
 ![Árbol de decisión usado por el host de ft cuando recibe un mensaje y CanCreateInstance es false.](./media/workflow-service-host-internals/workflow-service-host-receive-message.gif)  
  
 El mensaje llega y lo procesa la pila del canal WCF. Se comprueban los límites y se ejecutan las consultas de correlación. El mensaje se enlaza para una instancia existente, puesto que el valor de CanCreateInstance es false, con el fin de que la instancia se cargue desde el almacén de persistencia, se reanude el marcador y se ejecute el flujo de trabajo.  
  
> [!WARNING]
> Se producirá un error de apertura en el host de servicio de flujo de trabajo si se configura SQL Server para escuchar solo en el protocolo NamedPipe.  
  
## <a name="see-also"></a>Vea también

- [Servicios de flujo de trabajo](workflow-services.md)
- [Hospedar servicios de flujo de trabajo](hosting-workflow-services.md)
- [Extremo de control de flujo de trabajo](workflow-control-endpoint.md)
- [Procedimiento para configurar el comportamiento de excepción no controlada del flujo de trabajo con WorkflowServiceHost](config-workflow-unhandled-exception-workflowservicehost.md)
- [Crear un servicio de flujo de trabajo de larga ejecución](creating-a-long-running-workflow-service.md)
- [Persistencia del flujo de trabajo](../../windows-workflow-foundation/workflow-persistence.md)

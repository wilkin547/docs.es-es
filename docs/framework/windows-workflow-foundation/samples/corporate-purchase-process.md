---
title: Proceso de compra corporativa
ms.date: 03/30/2017
ms.assetid: a5e57336-4290-41ea-936d-435593d97055
ms.openlocfilehash: aa2ca2577eb68204ffcb755ce1b16b9354348ee3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293473"
---
# <a name="corporate-purchase-process"></a>Proceso de compra corporativa

En este ejemplo se muestra cómo crear solicitudes de propuesta (RFP) muy básicas en función del proceso de compra con selección automática de la mejor propuesta. Combina <xref:System.Activities.Statements.Parallel>, <xref:System.Activities.Statements.ParallelForEach%601> y una actividad personalizada <xref:System.Activities.Statements.ForEach%601> para crear un flujo de trabajo que representa el proceso.

 Este ejemplo contiene una aplicación cliente de ASP.NET que permite interactuar con el proceso como participantes diferentes (como el solicitante original o un proveedor determinado).

## <a name="requirements"></a>Requisitos

- Visual Studio 2012.

- [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].

## <a name="demonstrates"></a>Muestra

- Actividades personalizadas

- Composición de actividades.

- Marcadores

- Persistencia

- Persistencia esquematizada

- Traza

- Seguimiento

- Hospedaje [!INCLUDE[wf1](../../../../includes/wf1-md.md)] en diferentes clientes (aplicaciones Web ASP.net y aplicaciones de WinForms).

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Application\PurchaseProcess`  
  
## <a name="description-of-the-process"></a>Descripción del proceso  

 En este ejemplo se muestra una implementación de un programa de Windows Workflow Foundation (WF) para recopilar propuestas de proveedores para una empresa genérica.  
  
1. Un empleado de la compañía X crea una solicitud de propuestas (RFP).  
  
    1. El empleado escribe el título de la solicitud de propuestas y una descripción.  
  
    2. El empleado selecciona los proveedores a los que desea invitar a enviar propuestas.  
  
2. El empleado envía la propuesta.  
  
    1. Se crea una instancia del flujo de trabajo.  
  
    2. El flujo de trabajo espera a que todos los proveedores envíen sus propuestas.  
  
3. Una vez recibidas todas las propuestas, el flujo de trabajo recorre en iteración todas las propuestas recibidas y selecciona la mejor.  
  
    1. Cada proveedor tiene una reputación (en este ejemplo la lista de reputaciones se almacena en VendorRepository.cs).  
  
    2. El valor total de la propuesta se determina por (El valor escrito por el proveedor) * (La reputación grabada del proveedor) / 100.  
  
4. El solicitante original puede ver todas las propuestas enviadas. La mejor propuesta se presenta en una sección especial del informe.  
  
## <a name="process-definition"></a>Definición de proceso  

 La lógica básica del ejemplo utiliza una actividad <xref:System.Activities.Statements.ParallelForEach%601> que espera las ofertas de cada proveedor (utilizando una actividad personalizada que crea un marcador) y registra la propuesta del proveedor como una solicitud de propuesta (mediante una actividad <xref:System.Activities.Statements.InvokeMethod>).  
  
 A continuación, el ejemplo recorre en iteración todas las propuestas recibidas almacenadas en `RfpRepository`, calculando el valor ajustado (mediante una actividad <xref:System.Activities.Statements.Assign> y las actividades <xref:System.Activities.Expressions>), y si el valor ajustado es mejor que la mejor oferta anterior, asigna el nuevo valor como la mejor oferta (utilizando actividades <xref:System.Activities.Statements.If> y <xref:System.Activities.Statements.Assign>).  
  
## <a name="projects-in-this-sample"></a>Proyectos en este ejemplo  

 Este ejemplo contiene los siguientes proyectos.  
  
|Proyecto|Descripción|  
|-------------|-----------------|  
|Comunes|Los objetos entidad utilizados dentro del proceso (solicitud de propuesta, proveedor y propuesta del proveedor).|  
|WfDefinition|La definición del proceso (como un programa [!INCLUDE[wf1](../../../../includes/wf1-md.md)]) y el host (`PurchaseProcessHost`) utilizado por las aplicaciones cliente para crear y utilizar instancias del flujo de trabajo del proceso de compra.|  
|WebClient|Una aplicación cliente de ASP.NET que permite a los usuarios crear y participar en instancias del proceso de compra. Utiliza un host creado de forma personalizada para interactuar con el motor del flujo de trabajo.|  
|WinFormsClient|Una aplicación cliente de Windows Forms que permite a los usuarios crear y participar en instancias del proceso de compra. Utiliza un host creado de forma personalizada para interactuar con el motor del flujo de trabajo.|  
  
### <a name="wfdefinition"></a>WfDefinition  

 La siguiente tabla contiene una descripción de los archivos más importantes dentro del proyecto WfDefinition.  
  
|Archivo|Descripción|  
|----------|-----------------|  
|IPurchaseProcessHost.cs|Interfaz del host del flujo de trabajo.|  
|PurchaseProcessHost.cs|Implementación de un host para el flujo de trabajo. El host resume los detalles del tiempo de ejecución del flujo de trabajo y se utiliza en todas las aplicaciones cliente para cargar, ejecutar e interactuar con instancias de flujo de trabajo `PurchaseProcess`.|  
|PurchaseProcessWorkflow.cs|Una actividad que contiene la definición del flujo de trabajo del proceso de compra (se deriva de <xref:System.Activities.Activity>).<br /><br /> Las actividades que se derivan de <xref:System.Activities.Activity> crean la funcionalidad ensamblando actividades personalizadas existentes y actividades procedentes de la biblioteca de actividades de [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]. Ensamblar estas actividades es la manera más básica de crear la funcionalidad personalizada.|  
|WaitForVendorProposal.cs|Esta actividad personalizada se deriva de <xref:System.Activities.NativeActivity> y crea un marcador con nombre que debe reanudar posteriormente un proveedor al enviar la propuesta.<br /><br /> Las actividades que deriven de <xref:System.Activities.NativeActivity>, como aquéllas que derivan de <xref:System.Activities.CodeActivity>, crean la funcionalidad imperativa invalidando <xref:System.Activities.NativeActivity.Execute%2A>, pero también tienen acceso a toda la funcionalidad del tiempo de ejecución del flujo de trabajo a través de <xref:System.Activities.ActivityContext> que se transfiere al método `Execute`. Este contexto admite la programación y cancelación de actividades secundarias, configurando zonas sin persistencia (bloques de ejecución durante los cuales el tiempo de ejecución no conserva los datos del flujo de trabajo, como en el caso de transacciones atómicas) y <xref:System.Activities.Bookmark> objetos (identificadores para reanudar flujos de trabajo en pausa).|  
|TrackingParticipant.cs|<xref:System.Activities.Tracking.TrackingParticipant> que recibe todos los eventos de seguimiento y los guarda en un archivo de texto.<br /><br /> Los participantes de seguimiento se agregan a la instancia de flujo de trabajo como extensiones.|  
|XmlWorkflowInstanceStore.cs|Un objeto <xref:System.Runtime.DurableInstancing.InstanceStore> personalizado que guarda las aplicaciones de flujo de trabajo en archivos XML.|  
|XmlPersistenceParticipant.cs|Un objeto <xref:System.Activities.Persistence.PersistenceParticipant> personalizado que guarda una instancia de solicitud de propuesta en un archivo XML.|  
|AsyncResult.cs / CompletedAsyncResult.cs|Clases del asistente para implementar el patrón asincrónico en los componentes de persistencia.|  
  
### <a name="common"></a>Comunes  

 La siguiente tabla contiene una descripción de las clases más importantes dentro del proyecto Común.  
  
|Clase|Descripción|  
|-----------|-----------------|  
|Vendor|Un proveedor que envía propuestas en una solicitud de propuestas.|  
|RequestForProposal|Una solicitud de propuestas (RFP) es una invitación para que los proveedores envíen propuestas para un artículo o un servicio concretos.|  
|VendorProposal|Una propuesta enviada por un proveedor a una determinada solicitud de propuestas.|  
|VendorRepository|El repositorio de los proveedores. Esta implementación contiene una colección ubicada en memoria de instancias de proveedor y métodos para exponer esas instancias.|  
|RfpRepository|El repositorio de solicitudes de propuestas. Esta implementación contiene usos de Linq to XML para consultar el archivo XML de solicitudes de propuestas generado por la persistencia esquematizada. |  
|IOHelper|Esta clase administra todos los problemas relacionados con E/S (carpetas, rutas de acceso, etc.).|  
  
### <a name="web-client"></a>Cliente web  

 La siguiente tabla contiene una descripción de las páginas web más importantes dentro del proyecto Cliente web.  
  
|Archivo|Descripción|  
|-|-|  
|CreateRfp.aspx|Crea y envía nuevas solicitudes de propuestas.|  
|Default.aspx|Muestra todas las solicitudes de propuestas activas y completas.|  
|GetVendorProposal.aspx|Recibe una propuesta de un proveedor en una solicitud de propuestas concreta. Esta página la usan solo los proveedores.|  
|ShowRfp.aspx|Muestra toda la información sobre una solicitud de propuestas (propuestas recibidas, fechas, valores y otra información). Esta página solo la usa el creador de la solicitud de propuestas.|  
  
### <a name="winforms-client"></a>Cliente de WinForms  

 La siguiente tabla contiene una descripción de los formularios más importantes dentro del proyecto de WinForms.  
  
|Form|Descripción|  
|-|-|  
|NewRfp|Crea y envía nuevas solicitudes de propuestas.|  
|ShowProposals|Muestra todas las solicitudes de propuestas activas y finalizadas. **Nota:**  Es posible que tenga que hacer clic en el botón **Actualizar** en la interfaz de usuario para ver los cambios en la pantalla después de crear o modificar una solicitud de propuesta.|  
|SubmitProposal|Recibe una propuesta de un proveedor en una solicitud de propuestas concreta. Esta ventana solo la usan los proveedores.|  
|ViewRfp|Muestra toda la información sobre una solicitud de propuestas (propuestas recibidas, fechas, valores y otra información). Esta ventana solo la usa el creador de la solicitud de propuestas.|  
  
### <a name="persistence-files"></a>Archivos de persistencia  

 La siguiente tabla muestra los archivos generados por el proveedor de persistencia (`XmlPersistenceProvider`) que se encuentran en la ruta de acceso de la carpeta temporal del sistema actual (utilizando <xref:System.IO.Path.GetTempPath%2A>). El archivo de traza se crea en la ruta de acceso de ejecución actual.  
  
|Nombre de archivo|Descripción|Path|  
|-|-|-|  
|rfps.xml|El archivo XML con todas las solicitudes de propuestas activas y finalizadas.|<xref:System.IO.Path.GetTempPath%2A>|  
|[instanceid]|Este archivo contiene toda la información sobre una instancia de flujo de trabajo.<br /><br /> La implementación de la persistencia esquematizada (PersistenceParticipant en XmlPersistenceProvider) genera este archivo.|<xref:System.IO.Path.GetTempPath%2A>|  
|[instanceId] .tracking|Un archivo de texto con todos los eventos que se produjeron dentro de una instancia concreta.<br /><br /> TrackingParticipant genera este archivo.|<xref:System.IO.Path.GetTempPath%2A>|  
|PurchaseProcess.Tracing.TraceLog.txt|El archivo de traza generado por el flujo de trabajo en base a los parámetros de configuración de los archivos App.config o Web.config.|Ruta de acceso de ejecución actual|  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1. Con Visual Studio 2010, abra el archivo de solución PurchaseProcess. sln.  
  
2. Para ejecutar el proyecto de cliente web, Abra **Explorador de soluciones** y haga clic con el botón secundario en el proyecto de **cliente web** . Seleccione **establecer como proyecto de inicio**.  
  
3. Para ejecutar el proyecto de cliente de WinForms, Abra **Explorador de soluciones** y haga clic con el botón secundario en el proyecto de **cliente de WinForms** . Seleccione **establecer como proyecto de inicio**.  
  
4. Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
5. Para ejecutar la solución, presione CTRL+F5.  
  
### <a name="web-client-options"></a>Opciones del cliente web  
  
- **Crear un nuevo RFP**: crea una nueva solicitud de propuestas (RFP) e inicia un flujo de trabajo de proceso de compra.  
  
- **Actualizar**: actualiza la lista de propuestas activos y finalizados en la ventana principal.  
  
- **Ver**: muestra el contenido de una PDP existente. Los proveedores pueden enviar sus propuestas (si están invitados o la solicitud de propuestas no finaliza).  
  
- Ver como: el usuario puede tener acceso a la PDP mediante identidades diferentes seleccionando el participante deseado en el cuadro combinado **ver como** en la cuadrícula de propuestas activa.  
  
### <a name="winforms-client-options"></a>Opciones del cliente de WinForms  
  
- **Crear RFP**: crea una nueva solicitud de propuestas (RFP) e inicia un flujo de trabajo de proceso de compra.  
  
- **Actualizar**: actualiza la lista de propuestas activos y finalizados en la ventana principal.  
  
- **Ver PDP**: muestra el contenido de una PDP existente. Los proveedores pueden enviar sus propuestas (si están invitados o la solicitud de propuestas no finaliza).  
  
- **Conectar como**: el usuario puede tener acceso a la PDP mediante identidades diferentes seleccionando el participante deseado en el cuadro combinado **ver como** en la cuadrícula de propuestas activa.

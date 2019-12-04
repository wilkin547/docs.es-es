---
title: Proceso de contratación
ms.date: 03/30/2017
ms.assetid: d5fcacbb-c884-4b37-a5d6-02b1b8eec7b4
ms.openlocfilehash: 02968acfc762550c9010dd0ed29acbca845e08bb
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715976"
---
# <a name="hiring-process"></a>Proceso de contratación
Este ejemplo muestra cómo implementar un proceso de negocio mediante actividades de mensajería y dos flujos de trabajo hospedados como servicios de flujo de trabajo. Estos flujos de trabajo son parte de la infraestructura de TI de una compañía ficticia denominada Contoso, Inc.  
  
 El proceso de flujo de trabajo `HiringRequest` (implementado como <xref:System.Activities.Statements.Flowchart>) solicita autorización a varios administradores de la organización. Para lograr este objetivo, el flujo de trabajo usa otros servicios existentes en la organización (en nuestro caso, un servicio de bandeja de entrada y un servicio de datos de la organización implementados como servicios de Windows Communication Foundation sin formato (WCF)).  
  
 El flujo de trabajo `ResumeRequest` (implementado como <xref:System.Activities.Statements.Sequence>) publica un anuncio de vacante en el sitio web externo de ofertas de trabajo de Contoso y administra la adquisición de currículos. Un anuncio de vacante está disponible en el sitio web externo durante un período fijo de tiempo (hasta que expira un tiempo de espera) o hasta que un empleado en Contoso decide quitarlo.  
  
 Este ejemplo muestra las siguientes características de [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]:  
  
- Los flujos de trabajo <xref:System.Activities.Statements.Flowchart> y <xref:System.Activities.Statements.Sequence> para modelar los procesos de negocio.  
  
- Servicios de flujo de trabajo.  
  
- Actividades de mensajería.  
  
- Correlación basada en contenido.  
  
- Actividades personalizadas (declarativas y basadas en código).  
  
- Persistencia del servidor SQL proporcionada por el sistema.  
  
- <xref:System.Activities.Persistence.PersistenceParticipant> personalizado.  
  
- Seguimiento personalizado.  
  
- Seguimiento de eventos para Windows (ETW).  
  
- Composición de actividades.  
  
- Actividades <xref:System.Activities.Statements.Parallel>.  
  
- Actividad <xref:System.Activities.Statements.CancellationScope>.  
  
- Temporizadores duraderos (actividad<xref:System.Activities.Statements.Delay>).  
  
- Transacciones.  
  
- Más de un flujo de trabajo en la misma solución.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Este ejemplo se encuentra en el siguiente directorio.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Application\HiringProcess`  
  
## <a name="description-of-the-process"></a>Descripción del proceso  
 Contoso, Inc. desea llevar un control detallado del número de personas de cada uno de sus departamentos. Por consiguiente, siempre que un empleado desea iniciar un nuevo proceso de contratación, debe someterse a la aprobación del proceso de solicitud de contratación antes de que la contratación suceda realmente. Este proceso se llama solicitud de proceso de contratación (se define en el proyecto HiringRequestService) y consiste de los siguientes pasos:  
  
1. Un empleado (el solicitante) inicia la solicitud del proceso de contratación.  
  
2. El jefe del solicitante debe aprobar la solicitud:  
  
    1. El jefe puede rechazar la solicitud.  
  
    2. El jefe puede devolver la solicitud al solicitante para obtener información adicional:  
  
        1. El solicitante revisa y devuelve la solicitud al jefe.  
  
    3. El jefe puede dar su aprobación.  
  
3. Después de que el jefe del solicitante da su aprobación, el propietario del departamento debe aprobar la solicitud:  
  
    1. El propietario del departamento puede rechazarla.  
  
    2. El propietario del departamento puede aprobarla.  
  
4. Después de que el propietario del departamento da su aprobación, el proceso requiere la aprobación de dos responsables de Recursos Humanos o el CEO:  
  
    1. El proceso puede pasar al estado de aceptado o rechazado.  
  
    2. Si se acepta el proceso, se inicia una nueva instancia del flujo de trabajo `ResumeRequest` (`ResumeRequest` se vincula a HiringRequest.csproj a través de una referencia de servicio).  
  
 Cuando los responsables aprueban la contratación de un nuevo empleado, Recursos Humanos debe encontrar el candidato adecuado. El segundo flujo de trabajo (`ResumeRequest`, definido en ResumeRequestService.csproj) realiza este proceso. Este flujo de trabajo define el proceso para enviar una publicación de vacante con una oferta de trabajo al sitio web de ofertas de trabajo de Contoso, recibe currículos de los solicitantes y supervisa el estado de la publicación de vacante. Las vacantes están disponibles durante un período de tiempo fijo (hasta que expire) o hasta que un empleado en Contoso decida quitarla. El flujo de trabajo `ResumeRequest` se compone de los siguientes pasos:  
  
1. Un empleado de Contoso escribe la información sobre la vacante y una duración de tiempo de espera. Una vez que el empleado escribe esta información, la vacante se publica en el sitio web de ofertas de trabajo.  
  
2. Una vez publicada la información, las partes interesadas pueden enviar sus currículos. Cuando se envía un curriculum, se almacena en un registro vinculado al puesto vacante.  
  
3. Los solicitantes pueden enviar los currículos hasta que expire el tiempo de espera o alguien del departamento de Recursos Humanos de Contoso decida quitar la vacante deteniendo el proceso.  
  
## <a name="projects-in-the-sample"></a>Proyectos del ejemplo  
 En la siguiente tabla se muestran los proyectos de la solución de ejemplo.  
  
|Proyecto de|Descripción|  
|-------------|-----------------|  
|ContosoHR|Contiene contratos de datos, objetos de negocios y clases de repositorio.|  
|HiringRequestService|Contiene la definición del flujo de trabajo del proceso de solicitud de contratación.<br /><br /> Este proyecto se implementa como una aplicación de consola que autohospeda el flujo de trabajo (archivo xaml) como servicio.|  
|ResumeRequestService|Servicio de flujo de trabajo que recopila los currículos de los candidatos hasta que expira un tiempo de espera o alguien decide que el proceso tiene que detenerse.<br /><br /> Este proyecto se implementa como un servicio de flujo de trabajo declarativo (xamlx).|  
|OrgService|Servicio que expone la información de la organización (empleados, vacantes, tipos de vacantes y departamentos). Puede pensar en este servicio como el módulo de organización de la compañía de un plan de recursos empresariales (ERP).<br /><br /> Este proyecto se implementa como una aplicación de consola que expone un servicio Windows Communication Foundation (WCF).|  
|InboxService|Bandeja de entrada que contiene las tareas procesables para los empleados.<br /><br /> Este proyecto se implementa como una aplicación de consola que expone un servicio WCF.|  
|InternalClient|Aplicación web para interactuar con el proceso. Los usuarios pueden iniciar, participar y ver sus flujos de trabajo de HiringProcess. Con esta aplicación, también pueden iniciar y supervisar los procesos ResumeRequest.<br /><br /> Este sitio se implementa para ser interno a la intranet de Contoso. Este proyecto se implementa como un sitio web de ASP.NET.|  
|CareersWebSite|Sitio web externo que expone las vacantes en Contoso. Cualquier candidato potencial puede navegar a este sitio y enviar un curriculum.|  
  
## <a name="feature-summary"></a>Resumen de características  
 La siguiente tabla describe cómo se usa cada característica en este ejemplo.  
  
|Característica|Descripción|Proyecto de|  
|-------------|-----------------|-------------|  
|Diagrama de flujo|El proceso de negocio se representa como un diagrama de flujo. Esta descripción de diagrama de flujo representa el proceso de la misma manera en la que una empresa lo habría dibujado en una pizarra.|HiringRequestService|  
|Servicios de flujo de trabajo|El diagrama de flujo con la definición de proceso se hospeda en un servicio (en este ejemplo, el servicio se hospeda en una aplicación de consola).|HiringRequestService|  
|Actividades de mensajería|El diagrama de flujo utiliza actividades de mensajería de dos maneras:<br /><br /> -Para obtener información del usuario (para recibir las decisiones e información relacionada en cada paso de aprobación).<br />-Para interactuar con otros servicios existentes (InboxService y OrgDataService, que se usan a través de referencias de servicio).|HiringRequestService|  
|Correlación basada en contenido|Los mensajes de aprobación se correlacionan por la propiedad ID de la solicitud de contratación:<br /><br /> -Cuando se inicia un proceso, el identificador de correlación se inicializa con el identificador de la solicitud.<br />-Los mensajes de aprobación entrantes se correlacionan en su identificador (el primer parámetro de cada mensaje de aprobación es el identificador de la solicitud).|HiringRequestService / ResumeRequestService|  
|Actividades personalizadas (declarativas y basadas en código).|Hay varias actividades personalizadas en este ejemplo:<br /><br /> -   `SaveActionTracking`: esta actividad emite una <xref:System.Activities.Tracking.TrackingRecord> personalizada (mediante <xref:System.Activities.NativeActivityContext.Track%2A>). Esta actividad se ha creado utilizando código imperativo que extiende <xref:System.Activities.NativeActivity>.<br />-   `GetEmployeesByPositionTypes`: esta actividad recibe una lista de identificadores de tipo de posición y devuelve una lista de personas que tienen esa posición en contoso. Esta actividad se ha creado de forma declarativa (con el diseñador de actividades).<br />-   `SaveHiringRequestInfo`: esta actividad guarda la información de un `HiringRequest` (con `HiringRequestRepository.Save`). Esta actividad se ha creado utilizando código imperativo que extiende <xref:System.Activities.CodeActivity>.|HiringRequestService|  
|Persistencia de SQL Server proporcionada por el sistema.|La instancia de <xref:System.ServiceModel.Activities.WorkflowServiceHost> que hospeda la definición de proceso de Diagrama de flujo se configura para utilizar la persistencia de SQL Server proporcionada por el sistema.|HiringRequestService / ResumeRequestService|  
|Seguimiento personalizado|En el ejemplo se incluye un participante de seguimiento personalizado que guarda el historial de `HiringRequestProcess` (registra qué acción se ha realizado, quién la ha realizado y cuándo se ha realizado). El código fuente está en la carpeta Tracking de HiringRequestService.|HiringRequestService|  
|Seguimiento ETW|El seguimiento de ETW proporcionado por el sistema se configura en el archivo App.config en el servicio HiringRequestService.|HiringRequestService|  
|Composición de actividades|La definición del proceso utiliza la composición libre de <xref:System.Activities.Activity>. El Diagrama de flujo contiene varias actividades Sequence y Parallel que al mismo tiempo contienen otras actividades (y así sucesivamente).|HiringRequestService|  
|Actividades paralelas|-   <xref:System.Activities.Statements.ParallelForEach%601> se usa para registrarse en la bandeja de entrada del Director Ejecutivo y los administradores de recursos humanos en paralelo (en espera del paso de aprobación de dos administradores de recursos humanos).<br />-   <xref:System.Activities.Statements.Parallel> se usa para realizar algunas tareas de limpieza en los pasos completados y rechazados|HiringRequestService|  
|Cancelación de modelo|El Diagrama de flujo utiliza <xref:System.Activities.Statements.CancellationScope> para crear el comportamiento de cancelación (en este caso, se lleva a cabo alguna limpieza).|HiringRequestService|  
|Participante de persistencia del cliente|`HiringRequestPersistenceParticipant` guarda los datos de una variable de flujo de trabajo en una tabla almacenada en la base de datos de Recursos Humanos de Contoso.|HiringRequestService|  
|Servicios de flujo de trabajo|`ResumeRequestService` se implementa utilizando los servicios de flujo de trabajo. La definición del Flujo de trabajo y la información del servicio se encuentran en ResumeRequestService.xamlx. El servicio se configura para utilizar la persistencia y el seguimiento.|ResumeRequestService|  
|Temporizadores duraderos|`ResumeRequestService` utiliza temporizadores duraderos para definir la duración de la publicación de vacante (una vez que expira el tiempo de espera, se cierra la publicación de vacante).|ResumeRequestService|  
|Transacciones|<xref:System.Activities.Statements.TransactionScope> se utiliza para garantizar la coherencia de los datos dentro de la ejecución de varias actividades (cuando se recibe un nuevo curriculum vitae).|ResumeRequestService|  
|Transacciones|El participante de persistencia personalizado (`HiringRequestPersistenceParticipant`) y el participante de seguimiento personalizado (`HistoryFileTrackingParticipant`) usan la misma transacción.|HiringRequestService|  
|Usar [!INCLUDE[wf1](../../../../includes/wf1-md.md)] en aplicaciones ASP.NET.|Se tiene acceso a los flujos de trabajo desde dos aplicaciones ASP.NET.|InternalClient / CareersWebSite|  
  
## <a name="data-storage"></a>Almacenamiento de datos  
 Los datos están almacenados en una base de datos de SQL Server llamada `ContosoHR` (el script para crear esta base de datos se encuentra en la carpeta `DbSetup` ). Las instancias del flujo de trabajo se almacenan en una base de datos de SQL Server llamada `InstanceStore` (los scripts para crear el almacén de instancias forman parte de la distribución de [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)]).  
  
 Ambas bases de datos se crean ejecutando el script Setup. cmd desde un Símbolo del sistema para desarrolladores para Visual Studio.  
  
## <a name="running-the-sample"></a>Ejecutar el ejemplo  
  
#### <a name="to-create-the-databases"></a>Para crear las bases de datos  
  
1. Abra una Símbolo del sistema para desarrolladores para Visual Studio.  
  
2. Navegue hasta la carpeta del ejemplo.  
  
3. Ejecute Setup.cmd.  
  
4. Compruebe que las dos bases de datos, `ContosoHR` e `InstanceStore`, se crearon en SQL Express.  
  
#### <a name="to-set-up-the-solution-for-execution"></a>Para configurar la solución para su ejecución  
  
1. Ejecute Visual Studio como administrador. Abra HiringRequest.sln.  
  
2. Haga clic con el botón secundario en la solución en **Explorador de soluciones** y seleccione **propiedades**.  
  
3. Seleccione la opción **proyectos de inicio múltiples** y establezca **CareersWebSite**, **InternalClient**, **HiringRequestService**y **ResumeRequestService** en **iniciar**. Deje **ContosoHR**, **InboxService**y **OrgService** como ninguno.  
  
4. Compile la solución presionando CTRL+MAYÚS+B. Compruebe que la compilación se ha realizado correctamente.  
  
#### <a name="to-run-the-solution"></a>Para ejecutar la solución  
  
1. Cuando se compile la solución, presione CTRL+F5 para ejecutarla sin depuración. Compruebe que todos los servicios se han iniciado.  
  
2. Haga clic con el botón derecho en **InternalClient** en la solución y seleccione **ver en el explorador**. Se muestra la página predeterminada para `InternalClient`. Asegúrese de que los servicios se están ejecutando y haga clic en el vínculo.  
  
3. Se muestra el módulo **HiringRequest** . Puede seguir el escenario que aquí se detalla.  
  
4. Cuando `HiringRequest` se haya completado, puede iniciar `ResumeRequest`. Puede seguir el escenario que aquí se detalla.  
  
5. Cuando se expone `ResumeRequest`, está disponible en el sitio web público (sitio web de ofertas de trabajo de Contoso). Para ver la publicación de vacante (y solicitar el puesto), navegue hasta el sitio web de ofertas de trabajo (Careers).  
  
6. Haga clic con el botón secundario en **CareersWebSite** en la solución y seleccione **ver en el explorador**.  
  
7. Vuelva al `InternalClient` haciendo clic con el botón secundario en **InternalClient** en la solución y seleccionando **ver en el explorador**.  
  
8. Para ir a la sección **JobPostings** , haga clic en el vínculo **trabajos** puestos en el menú superior de la bandeja de entrada. Puede seguir el escenario que aquí se detalla.  
  
## <a name="scenarios"></a>Escenarios  
  
### <a name="hiring-request"></a>Solicitud de contratación  
  
1. Michael Alejandro (Ingeniero de software) desea solicitar una nueva vacante para contratar a un ingeniero de software en Pruebas (SDET), en el departamento de Ingeniería, que tenga 3 años de experiencia en C# por lo menos.  
  
2. Después de crearla, la solicitud aparece en la bandeja de entrada de Michael (haga clic en **Actualizar** si no ve la solicitud) a la espera de la aprobación de Peter Brehm, que es el administrador de Michael.  
  
3. Peter desea actuar sobre la solicitud de Michael. Piensa que el puesto exige 5 años de experiencia en C# en lugar de 3, de modo que devuelve sus comentarios para su revisión.  
  
4. Michael ve un mensaje en su bandeja de entrada de su administrador y desea actuar. Michael Ve el historial de la solicitud de puesto y está de acuerdo con Peter. Michael modifica la descripción para exigir 5 años de experiencia en C# y acepta la modificación.  
  
5. Peter actúa sobre la solicitud modificada de Michael y la acepta. Ahora, el director de Ingeniería, Tsvi Reiter, debe aprobar la solicitud.  
  
6. Tsvi Reiter desea agilizar la solicitud, de modo que incluye un comentario para decir que la solicitud es urgente y la acepta.  
  
7. Ahora, la solicitud tiene que ser aprobada por dos responsables de Recursos Humanos o el CEO. El CEO, Brian Richard Goldstein, ve la solicitud urgente de Tsvi. Actúa sobre la solicitud, aceptándola, evitando así la aprobación de los dos responsables de Recursos Humanos.  
  
8. La solicitud se quita de la bandeja de entrada de Michael y comienza ahora el proceso de contratación de un SDET.  
  
### <a name="start-resume-request"></a>Iniciar la solicitud de curriculum vitae  
  
1. Ahora, la posición del trabajo está a la espera de publicarse en un sitio web externo al que se puede aplicar la gente (puede verlo haciendo clic en el vínculo **trabajos publicados** ). Actualmente, el puesto de trabajo está en manos de un representante de Recursos Humanos, que es el responsable de terminarlo y publicarlo.  
  
2. HR quiere editar esta posición del trabajo (haciendo clic en el vínculo **Editar** ) estableciendo un tiempo de espera de 60 minutos (en la vida real, esto podría ser de días o semanas). El tiempo de espera permite retirar el puesto de trabajo del sitio web externo según el tiempo especificado.  
  
3. Después de guardar el puesto de trabajo editado, aparece en la pestaña de **currículos de recepción** (actualice la página web para ver la nueva posición del trabajo).  
  
### <a name="collecting-resumes"></a>Recopilar currículos  
  
1. El puesto de trabajo debería aparecer en el sitio web externo. Si una persona está interesada en solicitar el puesto, puede hacerlo y enviar su curriculum vitae.  
  
2. Si vuelve al servicio de lista de publicaciones de trabajos, puede "ver currículos" que se han recopilado hasta ahora.  
  
3. Recursos humanos también puede dejar de recopilar currículos (una vez que se ha identificado el candidato correcto).  
  
## <a name="troubleshooting"></a>Solucionar problemas  
  
1. Asegúrese de que está ejecutando Visual Studio con privilegios de administrador.  
  
2. Si la solución no se compila, compruebe lo siguiente:  
  
    - No falta la referencia a `ContosoHR` en los proyectos de `InternalClient` o `CareersWebSite`.  
  
3. Si la solución no se ejecuta, compruebe lo siguiente:  
  
    1. Todos los servicios se están ejecutando.  
  
    2. Las referencias del servicio están actualizadas.  
  
        1. Abra la carpeta App_WebReferences.  
  
        2. Haga clic con el botón secundario en **contoso** y seleccione **Actualizar referencias Web o de servicio**.  
  
        3. Vuelva a compilar la solución presionando CTRL + MAYÚS + B en Visual Studio.  
  
## <a name="uninstalling"></a>Desinstalar  
  
1. Para eliminar el almacén de instancias de SQL Server, ejecute el archivo Cleanup.bat, situado en la carpeta DbSetup.  
  
2. Elimine el código fuente de su disco duro.

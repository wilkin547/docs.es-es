---
title: "Configuraci&#243;n integrada | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 34e85c9b-088d-4347-816c-0f77cb73ef2f
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Configuraci&#243;n integrada
En este ejemplo se muestran el uso y la configuración del almacén de instancias de flujo de trabajo de SQL.El almacén de instancias de flujo de trabajo de SQL es una implementación basada en SQL de un almacén de instancias.Permite a una instancia guardar y cargar su estado en y desde una base de datos SQL Server o SQL Server Express.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a \(página de descarga\) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\Persistence\BuiltInConfiguration`  
  
## Detalles del ejemplo  
 Este ejemplo consta de un flujo de trabajo que implementa un servicio de contador.Una vez invocado el método de inicio del servicio, este cuenta de 0 a 59.El contador se incrementa una vez cada 2 segundos.Después de cada recuento, el flujo de trabajo se guarda.  
  
 Un host de servicio de flujo de trabajo autohospeda el flujo de trabajo de contador.El método `Main` del programa crea una instancia del host de servicio de flujo de trabajo que hospeda el flujo de trabajo de contador.Define los extremos bajo los que se puede alcanzar el flujo de trabajo de contador.Después, define el comportamiento del almacén de instancias de flujo de trabajo de SQL, que se utiliza para configurar el almacén de instancias de flujo de trabajo de SQL.A continuación, el programa crea un cliente que llama al método de inicio del flujo de trabajo de contador.  
  
 Una vez iniciado el programa, el contador inicia la cuenta automáticamente.Tenga en cuenta que la carga y configuración del almacén de instancias de flujo de trabajo de SQL puede tardar unos segundos.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] el almacén de instancias de flujo de trabajo, vea [Almacén de instancias de flujo de trabajo de SQL](../../../../docs/framework/windows-workflow-foundation//sql-workflow-instance-store.md).  
  
 El ejemplo consta de dos partes:  
  
1.  InstanceStore1 muestra cómo se configura <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> mediante código de C\# \(vea Program.cs\).  
  
2.  InstanceStore2 muestra cómo se configura <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> utilizando XML \(vea App.config\).  
  
 A continuación se indican los parámetros disponibles para configurar el comportamiento del almacén de instancias de flujo de trabajo de SQL:  
  
-   Establezca el valor de `HostLockRenewalPeriod`.Este tiempo define el intervalo con el que el host renueva el bloqueo de propiedad de las instancias que ejecuta.La información de bloqueo se guarda en el almacén de instancias.Si la propiedad no se renueva durante dos de los intervalos definidos en `HostLockRenewalPeriod`, la instancia se considera abandonada.Si otra clase <xref:System.ServiceModel.Activities.WorkflowServiceHost> está ejecutando el mismo flujo de trabajo y está conectada al mismo almacén de instancias \(en el mismo equipo o en un equipo diferente\), recupera esta instancia.\(La recuperación de instancias está fuera del ámbito de este ejemplo\).  
  
-   Establezca el valor de `RunnableInstancesDetectionPeriod`.Este período define el intervalo en el que el host sondea instancias que se han vuelto ejecutables.Las instancias se pueden volver ejecutables si se produce cualquiera de los eventos siguientes:  
  
    -   Expira un temporizador de larga duración \(<xref:System.Activities.Statements.Delay>\).  
  
    -   Otro host pierde su latido `HostLockRenewal` \(por ejemplo, debido a un bloqueo del equipo\) y se recupera la instancia.  
  
-   Establezca el valor de `InstanceCompletionAction`.Esta propiedad, si se establece en `DeleteNothing`, mantiene las instancias completadas en el almacén de instancias; si se establece en `DeleteAll`, las instancias se eliminan del almacén al completarse.Tenga en cuenta lo siguiente:  
  
    > [!NOTE]
    >  Si finaliza el host presionando Entrar antes de que el recuento se haya completado, la instancia de flujo de trabajo no se completa.  
  
-   Establezca el valor de `InstanceLockedExceptionAction`.Este valor define lo que debe hacer un host si desea cargar una instancia que está bloqueada por otro host.Existen las siguientes opciones:  
  
    -   Si está establecido en `NoRetry`: no reintenta la carga y devuelve `InstanceLockedException` al host.  
  
    -   Si está establecido en `BasicRetry`: sigue reintentando cargar la instancia.Los reintentos se programan según un algoritmo lineal simple \(por ejemplo, reintento cada 5 segundos\).  
  
    -   Si está establecido en `AggressiveRetry`: sigue reintentando cargar la instancia.Los reintentos se programan según un algoritmo de espera exponencial agresivo.  
  
-   Establezca la opción de codificación.Este valor define cómo se almacena el estado de la instancia en el almacén de instancias de flujo de trabajo de SQL.Existen las siguientes opciones:  
  
    -   El estado de la instancia se comprime mediante el algoritmo de compresión GZip.  
  
    -   El estado de la instancia no se comprime.  
  
#### Para utilizar este ejemplo  
  
1.  Abra un símbolo del sistema de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] como administrador si dispone de permisos.  
  
2.  Navegue hasta el directorio de ejemplo \(\\WF\\Basic\\Persistence\\BuiltInConfiguration\\CS\) y ejecute CreateInstanceStore.cmd.  
  
3.  Si no dispone de privilegios de administrador, cree un inicio de sesión de SQL Server.Vaya a `Security`, **Inicios de sesión**.Haga clic con el botón secundario en **Inicios de sesión** y cree un nuevo inicio de sesión.  
  
4.  Agregue su usuario ACL al rol SQL.Abra **Bases de datos**, **InstanceStore**, **Seguridad**.Haga clic con el botón secundario en **Usuarios** y seleccione **Nuevo usuario**.Establezca el **Nombre de inicio de sesión** en el usuario creado en el paso anterior.Agregue al usuario a la pertenencia al rol de la base de datos **System.Activities.DurableInstancing.InstanceStoreUsers** \(y otros\).Observe que el usuario ya podría existir \(por ejemplo, el usuario dbo\).  
  
5.  Abra el archivo InstanceStore.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] y compile la solución presionando CTRL\+MAYÚS\+B.  
  
6.  En el [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], navegue hasta el directorio \\bin\\debug adecuado del ejemplo \(\\WF\\Basic\\Persistence\\BuiltInConfiguration\\cs\\InstanceStore \(1 o 2\)\\bin\\debug\), haga clic con el botón secundario en InstanceStore.exe y seleccione **Ejecutar como administrador**.Este ejemplo se debe ejecutar con privilegios de administrador porque abre una escucha del canal.  
  
7.  Si creó el almacén de instancias en una base de datos distinta de una instalación local de SQL Server Express debe actualizar la cadena de conexión a la base de datos \(`const string ConnectionString` en el archivo Program.cs del proyecto InstanceStore1 y el atributo `connectionString` en el archivo App.config del proyecto InstanceStore2\) del ejemplo y recompilarlo.  
  
#### Para comprobar que el ejemplo se está ejecutando correctamente  
  
1.  Mientras se está ejecutando el ejemplo, inicie SQL Server Management Studio.  
  
2.  En el **Explorador de objetos**, seleccione **Bases de datos**, **InstanceStore**, **Tablas** y, a continuación **System.Activities.DurableInstancing.InstanceTable**.  
  
3.  Haga clic con el botón secundario en la tabla **Instances** y seleccione **Seleccionar las primeras 1000 filas**.  
  
4.  Observe que hay una nueva entrada y que la **Expiración de bloqueo** cambia cada 5 segundos \(haga clic en el botón **Ejecutar** de la barra de tareas para actualizar la consulta\).Esta es una consecuencia de establecer el valor de **Periodo de renovación del bloqueo de host** en 5.  
  
5.  Una vez que la cuenta se completa, observe que se quita la entrada de la tabla de instancias.Esta es una consecuencia de establecer la **Acción de finalización de instancias** en **DeleteAll**.  
  
6.  Presione Entrar para finalizar la aplicación host de flujo de trabajo; observe que se elimina **LockOwnersTable**.  
  
#### Para desinstalar el ejemplo  
  
1.  Ejecute RemoveInstanceStore.cmd en el directorio de ejemplo \(\\WF\\Basic\\Persistence\\BuiltInConfiguration\).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\Persistence\BuiltInConfiguration`  
  
## Vea también  
 [Ejemplos de hospedaje y persistencia de AppFabric](http://go.microsoft.com/fwlink/?LinkId=193961)
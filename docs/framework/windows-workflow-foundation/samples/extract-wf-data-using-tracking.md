---
title: "Extraer datos de WF mediante seguimiento | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e30c68f5-8c6a-495a-bd20-667a4364c68e
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Extraer datos de WF mediante seguimiento
En este ejemplo se muestra cómo utilizar el seguimiento del flujo de trabajo para extraer variables de flujo de trabajo y argumentos de las actividades.También muestra cómo agregar anotaciones a los registros de seguimiento y cómo extraer una carga de datos en los registros de seguimiento personalizados.En el ejemplo se utiliza el participante de seguimiento de Seguimiento de eventos para Windows \(ETW\) para extraer datos del flujo de trabajo.  
  
## Detalles del ejemplo  
 [!INCLUDE[wf](../../../../includes/wf-md.md)] proporciona seguimiento para ganar visibilidad en la ejecución de una instancia de flujo de trabajo.El tiempo de ejecución de seguimiento emite registros de seguimiento de flujo de trabajo durante la ejecución del flujo de trabajo.Los datos de la instancia de flujo de trabajo, junto con los registros de seguimiento del flujo de trabajo, se pueden extraer del flujo de trabajo.La siguiente lista detalla los tipos de datos que se pueden extraer de los registros de seguimiento:  
  
1.  Las variables de flujo de trabajo de una actividad y registros de seguimiento durante la ejecución de la actividad.  
  
     Para extraer las variables de flujo de trabajo, las variables que se van a extraer se especifican en un perfil.Las variables que se van a extraer solo se pueden especificar con `ActivityStateQueries`.El siguiente ejemplo de código muestra un perfil de seguimiento utilizado para extraer la variable de flujo de trabajo de una actividad.  
  
    ```xml  
    <activityStateQuery activityName="StockPriceService">  
         <states>  
              <state name="Closed"/>  
         </states>  
         <variables>  
              <variable name="symbol"/>  
         </variables>  
    </activityStateQuery>  
    ```  
  
2.  Argumentos de actividad y registros de seguimiento del estado de la actividad.  
  
     Los argumentos definen el flujo de datos hacia dentro o fuera de una actividad.Los argumentos que se van a extraer se especifican mediante <xref:System.Activities.Tracking.ActivityStateQuery>. El siguiente ejemplo de código representa un perfil de seguimiento que extrae el argumento `Value`.  
  
    ```xml  
    <activityStateQuery activityName="GetStockPrice">  
         <states>  
              <state name="Closed"/>  
         </states>  
         <arguments>  
              <argument name="Value"/>  
         </arguments>  
    </activityStateQuery>  
    ```  
  
3.  Las anotaciones son pares clave\-valor que se pueden agregar a cualquier registro de seguimiento que se emita.  
  
     Las anotaciones actúan como un mecanismo de etiquetado de registros de seguimiento.Las anotaciones se agregan a los registros de seguimiento a través de un perfil de seguimiento.Las anotaciones se pueden agregar a cualquier tipo de consulta de seguimiento de flujo de trabajo.El siguiente ejemplo de código representa un perfil de seguimiento que muestra cómo agregar una anotación a un registro de seguimiento.  
  
    ```xml  
    <workflowInstanceQuery>  
         <states>  
              <state name="Started"/>  
         </states>  
         <annotations>  
              <annotation name="StockPriceWorkflow" value="Begin"/>  
         </annotations>  
    </workflowInstanceQuery>  
    ```  
  
4.  Los registros de seguimiento personalizados se emiten por actividades definidas por el usuario.  
  
     Los registros de seguimiento personalizados pueden llevar datos de carga definidos dentro de esta actividad.La suscripción de registros de seguimiento personalizados en un perfil de seguimiento permite la extracción de la carga dentro del registro de seguimiento.Los registros de seguimiento personalizados se pueden extraer con un objeto <xref:System.Activities.Tracking.TrackingQuery> personalizado.El siguiente ejemplo de código representa un perfil de seguimiento que extrae un registro de seguimiento personalizado junto con su carga.  
  
    ```  
    <customTrackingQuery name="QuoteLookupEvent" activityName="GetStockPrice"/>  
    ```  
  
 En el ejemplo se muestra cómo extraer variables, argumentos, registros personalizados y agregar anotaciones utilizando un perfil especificado en el archivo Web.config.El seguimiento se habilita en el servicio de flujo de trabajo de ejemplo agregando un elemento de comportamiento `<etwTracking>`.El siguiente ejemplo de código habilita el seguimiento para el perfil de seguimiento `ExtractWorkflowVariables`.  
  
```  
<serviceBehaviors>  
     <behavior>  
               <etwTracking profileName="ExtractWorkflowVariables"/>  
     </behavior>  
</serviceBehaviors>  
```  
  
#### Para utilizar este ejemplo  
  
1.  Abra el archivo de solución de WFStockPriceApplication.sln con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Para compilar la solución, presione Ctrl\+MAYÚS\+B.  
  
3.  Presione F5 para ejecutar la solución.  
  
     La ventana del explorador se abre y muestra la lista de directorios de la aplicación.  
  
4.  En el explorador, haga clic en StockPriceService.xamlx.  
  
5.  El explorador muestra la página StockPriceService, que contiene la dirección WSDL de servicio local.Copie esta dirección.  
  
     En el siguiente ejemplo se muestra una dirección WSDL de servicio local.`http://localhost:53797/StockPriceService.xamlx?wsdl`  
  
6.  Antes de invocar el servicio, inicie el Visor de eventos y asegúrese de que el registro de eventos escucha los eventos de seguimiento emitidos por el flujo de trabajo.  
  
7.  En el menú **Inicio**, seleccione **Herramientas administrativas** y, a continuación, **Visor de eventos**.  
  
8.  En la vista de árbol del Visor de eventos, navegue hasta **Visor de eventos**, **Registros de aplicaciones y servicios** y **Microsoft**.Haga clic con el botón secundario en **Microsoft**, seleccione **Ver** y, a continuación, **Mostrar registros analíticos y de depuración**.  
  
     Asegúrese de que esté activada la opción **Mostrar registros analíticos y de depuración**.  
  
9. En la vista de árbol del Visor de eventos, navegue hasta **Visor de eventos**, **Registros de aplicaciones y servicios**, **Microsoft**, **Windows**, **Servidor de aplicaciones\-Aplicación**.Haga clic con el botón secundario en **Analítico** y seleccione **Habilitar registro**.  
  
10. Con el [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], abra el cliente de prueba WCF.  
  
     El cliente de pruebas de WCF \(WcfTestClient.exe\) se encuentra en la carpeta \<[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] carpeta de instalación\>\\Common7\\IDE\\.  
  
     La carpeta de instalación predeterminada de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] es C:\\Archivos de programa\\Microsoft Visual Studio 10.0.  
  
11. En el cliente de pruebas de WCF, seleccione **Agregar servicio** en el menú **Archivo**.  
  
     Agregue la dirección WSDL de servicio local que copió anteriormente en el cuadro de entrada.  
  
12. En el cliente de pruebas de WCF, haga doble clic en `GetStockPrice`.  
  
     De este modo, se abrirá el método `GetStockPrice`.La solicitud acepta un parámetro.Utilice el valor **Contoso**.  
  
13. Haga clic en **Invocar**.  
  
14. Cambie al Visor de eventos y navegue hasta **Visor de eventos**, **Registros de aplicaciones y servicios**, **Microsoft**, **Windows**, **Aplicaciones de servidor\-Aplicaciones**.Haga clic con el botón secundario en **Analítico** y seleccione **Actualizar**.Los eventos de flujo de trabajo se encuentran en el intervalo de identificadores de evento que va del 100 al 199.  
  
     Los eventos contienen las anotaciones, las variables, los argumentos y los registros de seguimiento personalizados que se pueden ver en el Visor de eventos.  
  
## Limpiar el Visor de eventos  
 Para limpiar el canal analítico del registro de eventos en el Visor de eventos realice lo siguiente.  
  
#### Para realizar la limpieza \(Opcional\)  
  
1.  Abra el Visor de eventos.  
  
2.  Navegue hasta **Visor de eventos**, **Registros de aplicaciones y servicios**, **Microsoft**, **Windows**, **Aplicaciones de servidor\-Aplicaciones**.Haga clic con el botón secundario en **Analítico** y seleccione **Deshabilitar registro**.  
  
3.  Navegue hasta **Visor de eventos**, **Registros de aplicaciones y servicios**, **Microsoft**, **Windows**, **Aplicaciones de servidor\-Aplicaciones**.Haga clic con el botón secundario en **Analítico** y seleccione **Borrar registro**.  
  
     Elija la opción **Borrar** para borrar los eventos.  
  
## Problema conocido  
  
> [!NOTE]
>  Existe un problema conocido en el Visor de eventos en virtud del cual el visor no puede descodificar eventos de ETW.Es posible que vea un mensaje de error similar el siguiente.  
>   
>  `No se encuentra la descripción del id. de evento <id> en el origen Microsoft-Windows-Servidor de aplicaciones-Aplicaciones.El componente que genera este evento no está instalado en el equipo local, o bien la instalación está dañada.Puede instalar o reparar el componente en el equipo local.`  
>   
>  Si encuentra este error, haga clic en **Actualizar** en el panel de acciones.El evento debería descodificarse ahora correctamente.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\Tracking\ExtractWfData`  
  
## Vea también  
 [Ejemplos de supervisión de AppFabric](http://go.microsoft.com/fwlink/?LinkId=193959)
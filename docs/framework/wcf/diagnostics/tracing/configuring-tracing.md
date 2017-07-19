---
title: "Configurar seguimiento | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "seguimiento [WCF]"
ms.assetid: 82922010-e8b3-40eb-98c4-10fc05c6d65d
caps.latest.revision: 53
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 53
---
# Configurar seguimiento
En este tema se describe cómo se puede habilitar el seguimiento, configurar los orígenes de seguimiento para emitir trazas y establecer niveles de seguimiento, establecer el seguimiento y la propagación de actividades para admitir la correlación de seguimiento de un extremo a otro, y establecer escuchas de seguimiento para tener acceso a las trazas.  
  
 Para obtener las recomendaciones de configuración del seguimiento en un entorno de producción o depuración, consulte [Configuración recomendada para el seguimiento y el registro de mensajes](../../../../../docs/framework/wcf/diagnostics/tracing/recommended-settings-for-tracing-and-message-logging.md).  
  
> [!IMPORTANT]
>  En Windows 8, debe ejecutar la aplicación con permisos elevados \(Ejecutar como administrador\) para que la aplicación genere registros de seguimiento.  
  
## Habilitar el seguimiento  
 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] genera los datos siguientes para el seguimiento de diagnóstico:  
  
-   Trazas para los hitos del proceso en todos los componentes de las aplicaciones, como llamadas de operación, excepciones de código, advertencias y otros eventos de procesamiento significativos.  
  
-   Eventos de error de Windows cuando la característica de seguimiento no funciona bien.Vea [Registro de eventos](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md).  
  
 El seguimiento [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] se basa en <xref:System.Diagnostics>.Para usar el seguimiento, debe definir los orígenes de seguimiento en el archivo de configuración o en el código.[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] define un origen de seguimiento para cada ensamblado de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].El origen de seguimiento `System.ServiceModel` es el origen de seguimiento [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] más general y graba los hitos del procesamiento en la pila de comunicación [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], desde el transporte de entrada\/salida al código de usuario de entrada\/salida.El origen de seguimiento `System.ServiceModel.MessageLogging` graba todos los mensajes que fluyen a través del sistema.  
  
 De forma predeterminada, el seguimiento no está habilitado.Para activar el seguimiento, debe crear una escucha de seguimiento y establecer un nivel de seguimiento diferente a "Off" para el origen de seguimiento seleccionado en configuración; de lo contrario, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] no genera ninguna traza.Si no especifica una escucha, el seguimiento se deshabilita automáticamente.Si se define una escucha pero no se especifica ningún nivel, el nivel se establece de forma predeterminada en "Off", lo que significa que no se emite ningún seguimiento.  
  
 Si utiliza puntos de extensibilidad de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], como invocadores de operación personalizados, debería emitir sus propios seguimientos.Esto se debe a que, si implementa un punto de extensibilidad, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] ya no puede emitir los seguimientos estándar en la ruta de acceso predeterminada.Si no implementa la compatibilidad con el seguimiento manual mediante la emisión de seguimientos, puede que no vea los seguimientos que espera.  
  
 Puede configurar el seguimiento editando el archivo de configuración de la aplicación: Web.config para las aplicaciones hospedadas en web o Appname.exe.config para las aplicaciones autohospedadas.A continuación se muestra un ejemplo de dicha modificación:Para obtener más información sobre esta configuración, vea la sección “Configurar las escuchas para consumir seguimientos”.  
  
```  
<configuration>  
   <system.diagnostics>  
      <sources>  
            <source name="System.ServiceModel"   
                    switchValue="Information, ActivityTracing"  
                    propagateActivity="true">  
            <listeners>  
               <add name="traceListener"   
                   type="System.Diagnostics.XmlWriterTraceListener"   
                   initializeData= "c:\log\Traces.svclog" />  
            </listeners>  
         </source>  
      </sources>  
   </system.diagnostics>  
</configuration>  
```  
  
> [!NOTE]
>  Para editar el archivo de configuración de un proyecto de servicio de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] en [!INCLUDE[vs_current_short](../../../../../includes/vs-current-short-md.md)], haga clic con el botón secundario en el archivo de configuración de la aplicación \(Web.config para las aplicaciones hospedadas en web o Appname.exe.config para las aplicaciones autohospedadas\) en el **Explorador de soluciones**.A continuación, elija el elemento de menú contextual **Editar configuración de WCF**.Esto inicia la [Herramienta del editor de configuración \(SvcConfigEditor.exe\)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md), que le permite modificar la configuración de los servicios de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] mediante una interfaz gráfica de usuario.  
  
## Configurar los orígenes de seguimiento para emitir trazas  
 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] define un origen de seguimiento para cada ensamblado.Las escuchas definidas para ese origen tienen acceso a las trazas generadas dentro de un ensamblado.Se definen los orígenes de seguimiento siguientes:  
  
-   System.ServiceModel: registra todas las fases de procesamiento de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], cada vez que se lee la configuración, cada vez que se procesa un mensaje en el transporte, en el procesamiento de la seguridad, cuando un mensaje se envía en el código de usuario, etc.  
  
-   System.ServiceModel.MessageLogging: Registra todos los mensajes que fluyen a través del sistema.  
  
-   System.IdentityModel.  
  
-   System.ServiceModel.Activation.  
  
-   System.IO.Log: Registro para la interfaz .NET Framework al Sistema de archivos de registro comunes \(CLFS\).  
  
-   System.Runtime.Serialization: Se registra cuando los objetos se leen o escriben.  
  
-   CardSpace.  
  
 Puede configurar cada origen de seguimiento de manera que se utilice la misma escucha \(compartida\), como se indica en el ejemplo de configuración siguiente.  
  
```  
<configuration>  
    <system.diagnostics>  
        <sources>  
            <source name="System.ServiceModel"   
                    switchValue="Information, ActivityTracing"  
                    propagateActivity="true">  
                <listeners>  
                    <add name="xml" />  
                </listeners>  
            </source>  
            <source name="CardSpace">  
                <listeners>  
                    <add name="xml" />  
                </listeners>  
            </source>  
            <source name="System.IO.Log">  
                <listeners>  
                    <add name="xml" />  
                </listeners>  
            </source>  
            <source name="System.Runtime.Serialization">  
                <listeners>  
                    <add name="xml" />  
                </listeners>  
            </source>  
            <source name="System.IdentityModel">  
                <listeners>  
                    <add name="xml" />  
                </listeners>  
            </source>  
        </sources>  
  
        <sharedListeners>  
            <add name="xml"  
                 type="System.Diagnostics.XmlWriterTraceListener"  
                 initializeData="c:\log\Traces.svclog" />  
        </sharedListeners>  
    </system.diagnostics>  
</configuration>  
```  
  
 Además, puede agregar orígenes de seguimiento definidos por el usuario, como se muestra en el ejemplo siguiente, para emitir trazas de código de usuario.  
  
```  
<system.diagnostics>  
   <sources>  
       <source name="UserTraceSource" switchValue="Warning, ActivityTracing" >  
          <listeners>  
              <add name="xml"  
                 type="System.Diagnostics.XmlWriterTraceListener"  
                 initializeData="C:\logs\UserTraces.svclog" />  
          </listeners>  
       </source>  
   </sources>  
   <trace autoflush="true" />   
</system.diagnostics>  
```  
  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)] la creación de orígenes de seguimiento definidos por el usuario, vea [Extensión del seguimiento](../../../../../docs/framework/wcf/samples/extending-tracing.md).  
  
## Configurar las escuchas para consumir trazas  
 En tiempo de ejecución, las fuentes de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] hacen un seguimiento de datos hasta los agentes de escucha que procesan los datos.[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] proporciona varios agentes de escucha predefinidos para <xref:System.Diagnostics>, que difieren en el formato que usan para el resultado.También puede agregar tipos de escucha personalizados.  
  
 Puede utilizar `add` para especificar el nombre y tipo de agente de escucha de seguimiento que desea utilizar.En nuestra configuración de ejemplo, hemos llamado `traceListener` al agente de escucha y hemos agregado el agente de escucha de seguimiento estándar de .NET Framework \(`System.Diagnostics.XmlWriterTraceListener`\) como el tipo que deseamos utilizar.Puede agregar cualquier número de escuchas de seguimiento para cada origen.Si la escucha de seguimiento emite el seguimiento a un archivo, debe especificar la ubicación del archivo de salida y el nombre en el archivo de configuración.Esto se hace estableciendo `initializeData` en el nombre del archivo para esa escucha.Si no especifica un nombre de archivo, se genera un nombre de archivo aleatorio basado en el tipo de escucha utilizado.Si se utiliza <xref:System.Diagnostics.XmlWriterTraceListener>, se genera un nombre de archivo sin extensión.Si implementa una escucha personalizada, también puede utilizar este atributo para recibir datos de inicialización distintos de un nombre de archivo.Por ejemplo, puede especificar un identificador de la base de datos para este atributo.  
  
 Puede configurar una escucha de seguimiento personalizada para enviar las trazas en la conexión, por ejemplo, a una base de datos remota.Como un implementador de la aplicación, debería exigir un control de acceso apropiado en los registros de seguimiento en el equipo remoto.  
  
 También puede configurar mediante programación una escucha de seguimiento.[!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)][How to: Create and Initialize Trace Listeners](http://go.microsoft.com/fwlink/?LinkId=94648) y [Creating a Custom TraceListener](http://go.microsoft.com/fwlink/?LinkId=96239).  
  
> [!CAUTION]
>  Puesto que `System.Diagnostics.XmlWriterTraceListener` no es seguro para subprocesos, el origen de seguimiento puede bloquear los recursos de forma exclusiva al generar trazas.Cuando muchos subprocesos generan trazas para un origen de seguimiento configurado para utilizar esta escucha, puede producirse una contención de recursos, que genera un problema de rendimiento importante.Para solucionar este problema, debería implementar una escucha personalizada que sea segura para subprocesos.  
  
## Nivel de seguimiento  
 El nivel de seguimiento está controlado por el valor `switchValue` del origen de seguimiento.En la siguiente tabla se describen los niveles de seguimiento disponibles.  
  
|Nivel de seguimiento|Naturaleza de los eventos seguidos|Contenido de los eventos seguidos|Eventos de los que se realiza un seguimiento|Destino del usuario|  
|--------------------------|----------------------------------------|---------------------------------------|--------------------------------------------------|-------------------------|  
|Off|N\/D|N\/D|No se emiten seguimientos.|N\/D|  
|Crítico|Eventos "negativos": eventos que indican un procesamiento inesperado o una condición de error.||Se registran las excepciones no controladas, incluidas las siguientes:<br /><br /> -   OutOfMemoryException<br />-   ThreadAbortException \(el CLR invoca a cualquier ThreadAbortExceptionHandler\)<br />-   StackOverflowException \(no se puede detectar\)<br />-   ConfigurationErrorsException<br />-   SEHException<br />-   Errores de inicio de aplicación<br />-   Eventos Failfast<br />-   Caídas del sistema<br />-   Mensajes dudosos: seguimientos de mensajes que hacen que se produzca un error en la aplicación.|Administradores<br /><br /> Desarrolladores de aplicaciones|  
|Error|Eventos "negativos": eventos que indican un procesamiento inesperado o una condición de error.|Se ha producido un procesamiento inesperado.La aplicación no pudo realizar una tarea como se esperaba.Sin embargo, la aplicación todavía está en funcionamiento y ejecutándose.|Se registran todas las excepciones.|Administradores<br /><br /> Desarrolladores de aplicaciones|  
|Advertencia|Eventos "negativos": eventos que indican un procesamiento inesperado o una condición de error.|Se ha producido o puede producirse un posible problema, pero la aplicación todavía funciona correctamente.Sin embargo, puede no continuar funcionando correctamente.|-   La aplicación está recibiendo más solicitudes que las que permiten sus valores de limitación de peticiones.<br />-   La cola receptora está cercana a su capacidad máxima configurada.<br />-   Tiempo de espera superado.<br />-   Se rechazan las credenciales.|Administradores<br /><br /> Desarrolladores de aplicaciones|  
|Información|Eventos "positivos": eventos que marcan hitos correctos|Hitos importantes y correctos de ejecución de la aplicación, independientemente de si la aplicación funciona correctamente o no.|En general, se generan mensajes útiles para supervisar y diagnosticar el estado del sistema, medir el rendimiento o el perfil.Puede usar esta información para la planeación de la capacidad y la administración del rendimiento:<br /><br /> -   Se crean los canales.<br />-   Se crean escuchas del extremo.<br />-   El mensaje entra\/abandona el transporte.<br />-   Se recupera el token de seguridad.<br />-   Se lee el valor de configuración.|Administradores<br /><br /> Desarrolladores de aplicaciones<br /><br /> Desarrolladores de productos.|  
|Detalles|Eventos "positivos": eventos que marcan hitos correctos.|Se emiten eventos de bajo nivel tanto para el código de usuario como para el servicio.|En general, puede utilizar este nivel para depuración u optimización de la aplicación.<br /><br /> -   Se entendió el encabezado del mensaje.|Administradores<br /><br /> Programadores de aplicaciones<br /><br /> Programadores del producto.|  
|ActivityTracing||Transmitir eventos entre actividades de procesamiento y componentes.|Este nivel permite a los administradores y programadores poner en correlación las aplicaciones que se encuentran en el mismo dominio de aplicación:<br /><br /> -   Seguimiento de los límites de actividad, como iniciar\/detener.<br />-   Seguimiento de las transferencias.|Todos|  
|Todos||La aplicación puede funcionar correctamente.Se emiten todos los eventos.|Todos los eventos anteriores.|Todos|  
  
 Los niveles de Detallado a Crítico se apilan unos encima de otros, es decir, cada nivel de seguimiento incluye todos los niveles anteriores él excepto el nivel Off.Por ejemplo, una escucha que realiza escuchas en el nivel de advertencia recibe trazas de Crítico, Error, y Advertencia.Todos los niveles incluye los eventos de Detallado a Crítico y eventos de seguimiento de actividad.  
  
> [!CAUTION]
>  Los niveles de Información, Detallado, y ActivityTracing generan muchas trazas, lo que puede afectar negativamente al rendimiento de los mensajes si ha agotado todos los recursos disponibles en el equipo.  
  
## Configurar el seguimiento de actividad y la propagación para la correlación  
 El valor `activityTracing` especificado para el atributo `switchValue` se utiliza para habilitar el seguimiento de actividad, que emite las trazas para los límites de actividad y las transferencias dentro de los extremos.  
  
> [!NOTE]
>  Cuando se utilizan ciertas características de extensibilidad en [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], puede obtenerse una <xref:System.NullReferenceException> si la traza de la actividad está habilitada.Para solucionar este problema, compruebe el archivo de configuración de la aplicación y asegúrese de que el atributo `switchValue` para el origen de seguimiento de traza no está establecido en `activityTracing`.  
  
 El atributo `propagateActivity` indica si la actividad se debería propagar a otros extremos que participan en el intercambio de mensajes.Estableciendo este valor en `true`, puede coger archivos de seguimiento generados por dos extremos cualesquiera y observar cómo un conjunto de trazas en un extremo fluyó a un conjunto de rastros de otro extremo.  
  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)] la propagación y el seguimiento de actividades, consulte [Propagación](../../../../../docs/framework/wcf/diagnostics/tracing/propagation.md).  
  
 Los valores booleanos `propagateActivity`y `ActivityTracing`se aplican a System.ServiceModel TraceSource.El valor`ActivityTracing`también se aplica a cualquier origen de seguimiento, incluyendo los de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] o los definidos por el usuario.  
  
 No puede utilizar el atributo `propagateActivity` con orígenes de seguimiento definidos por el usuario.Para la propagación del identificador de actividad de código de usuario, asegúrese de no establecer ServiceModel `ActivityTracing`, mientras todavía tenga el atributo ServiceModel `propagateActivity` establecido en `true`.  
  
## Vea también  
 [Seguimiento](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)   
 [Cómo: Crear e inicializar agentes de escucha de seguimiento](http://go.microsoft.com/fwlink/?LinkId=94648)   
 [Crear un agente de escucha de seguimiento personalizado](http://go.microsoft.com/fwlink/?LinkId=96239)
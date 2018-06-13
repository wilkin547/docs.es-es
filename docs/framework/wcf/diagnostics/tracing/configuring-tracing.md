---
title: Configurar seguimiento
ms.date: 03/30/2017
helpviewer_keywords:
- tracing [WCF]
ms.assetid: 82922010-e8b3-40eb-98c4-10fc05c6d65d
ms.openlocfilehash: f9603f79992c31ad1af3b6c672b448ab031ba78d
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
ms.locfileid: "33807373"
---
# <a name="configuring-tracing"></a>Configurar seguimiento
En este tema se describe cómo se puede habilitar el seguimiento, configurar los orígenes de seguimiento para emitir trazas y establecer niveles de seguimiento, establecer el seguimiento y la propagación de actividades para admitir la correlación de seguimiento de un extremo a otro, y establecer escuchas de seguimiento para tener acceso a las trazas.  
  
 Para recomendaciones de configuración de seguimiento en el entorno de depuración o de producción, consulte [configuración recomendada para el seguimiento y registro de mensajes](../../../../../docs/framework/wcf/diagnostics/tracing/recommended-settings-for-tracing-and-message-logging.md).  
  
> [!IMPORTANT]
>  En Windows 8 debe ejecutar la aplicación elevada (ejecutar como administrador) para que la aplicación genere los registros de seguimiento.  
  
## <a name="enabling-tracing"></a>Habilitar el seguimiento  
 Windows Communication Foundation (WCF) genera los datos siguientes para el seguimiento de diagnóstico:  
  
-   Trazas para los hitos del proceso en todos los componentes de las aplicaciones, como llamadas de operación, excepciones de código, advertencias y otros eventos de procesamiento significativos.  
  
-   Eventos de error de Windows cuando la característica de seguimiento no funciona bien. Vea [el registro de eventos](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md).  
  
 Seguimiento de WCF se basa en <xref:System.Diagnostics>. Para usar el seguimiento, debe definir los orígenes de seguimiento en el archivo de configuración o en el código. WCF define un origen de seguimiento para cada ensamblado WCF. El `System.ServiceModel` origen de seguimiento es el origen de seguimiento WCF más general y graba los hitos del procesamiento a través de la pila de comunicación de WCF de transporte de entrada/salida salida código de usuario. El origen de seguimiento `System.ServiceModel.MessageLogging` graba todos los mensajes que fluyen a través del sistema.  
  
 De forma predeterminada, el seguimiento no está habilitado. Para activar el seguimiento, debe crear un agente de escucha de seguimiento y establecer un nivel de seguimiento diferente a "Off" para el origen de seguimiento seleccionado en configuración; en caso contrario, WCF no genera ninguna traza. Si no especifica una escucha, el seguimiento se deshabilita automáticamente. Si se define una escucha pero no se especifica ningún nivel, el nivel se establece de forma predeterminada en "Off", lo que significa que no se emite ningún seguimiento.  
  
 Si usa puntos de extensibilidad WCF, como Invocadores de operación personalizado, debe emitir sus propios seguimientos. Esto es porque si implementa un punto de extensibilidad, WCF ya no puede emitir los seguimientos estándar en la ruta de acceso predeterminada. Si no implementa la compatibilidad con el seguimiento manual mediante la emisión de seguimientos, puede que no vea los seguimientos que espera.  
  
 Puede configurar el seguimiento editando el archivo de configuración de la aplicación: Web.config para las aplicaciones hospedadas en web o Appname.exe.config para las aplicaciones autohospedadas. A continuación se muestra un ejemplo de dicha modificación: Para obtener más información sobre estas opciones, vea la sección "Configurar agentes de escucha de seguimiento para seguimientos consumir".  
  
```xml  
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
>  Para editar el archivo de configuración de un proyecto de servicio WCF en Visual Studio, haga clic en el archivo de configuración de la aplicación: Web.config para las aplicaciones hospedadas en Web o Appname.exe.config para las aplicaciones autohospedadas en **el Explorador de soluciones** . A continuación, elija la **Editar configuración de WCF** elemento de menú contextual. Esto inicia el [herramienta Editor de configuración (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md), lo que permite modificar la configuración para los servicios WCF mediante una interfaz gráfica de usuario.  
  
## <a name="configuring-trace-sources-to-emit-traces"></a>Configurar los orígenes de seguimiento para emitir trazas  
 WCF define un origen de seguimiento para cada ensamblado. Las escuchas definidas para ese origen tienen acceso a las trazas generadas dentro de un ensamblado. Se definen los orígenes de seguimiento siguientes:  
  
-   System.ServiceModel: Registra todas las fases de procesamiento de WCF, cada vez que se lee la configuración, se procesa un mensaje en el transporte, seguridad de procesamiento, un mensaje se envía en el código de usuario y así sucesivamente.  
  
-   System.ServiceModel.MessageLogging: Registra todos los mensajes que fluyen a través del sistema.  
  
-   System.IdentityModel.  
  
-   System.ServiceModel.Activation.  
  
-   System.IO.Log: Registro para la interfaz .NET Framework al Sistema de archivos de registro comunes (CLFS).  
  
-   System.Runtime.Serialization: Se registra cuando los objetos se leen o escriben.  
  
-   CardSpace.  
  
 Puede configurar cada origen de seguimiento de manera que se utilice la misma escucha (compartida), como se indica en el ejemplo de configuración siguiente.  
  
```xml  
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
  
```xml  
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
  
 Para obtener más información acerca de cómo crear orígenes de seguimiento definido por el usuario, consulte [extender seguimiento](../../../../../docs/framework/wcf/samples/extending-tracing.md).  
  
## <a name="configuring-trace-listeners-to-consume-traces"></a>Configurar las escuchas para consumir trazas  
 En tiempo de ejecución, WCF las fuentes de datos de seguimiento para los agentes de escucha que procesan los datos. WCF proporciona varios agentes de escucha predefinidos para <xref:System.Diagnostics>, que difieren en el formato que se usan para la salida. También puede agregar tipos de escucha personalizados.  
  
 Puede utilizar `add` para especificar el nombre y tipo de agente de escucha de seguimiento que desea utilizar. En nuestra configuración de ejemplo, hemos llamado `traceListener` al agente de escucha y hemos agregado el agente de escucha de seguimiento estándar de .NET Framework (`System.Diagnostics.XmlWriterTraceListener`) como el tipo que deseamos utilizar. Puede agregar cualquier número de escuchas de seguimiento para cada origen. Si la escucha de seguimiento emite el seguimiento a un archivo, debe especificar la ubicación del archivo de salida y el nombre en el archivo de configuración. Esto se hace estableciendo `initializeData` en el nombre del archivo para esa escucha. Si no especifica un nombre de archivo, se genera un nombre de archivo aleatorio basado en el tipo de escucha utilizado. Si se utiliza <xref:System.Diagnostics.XmlWriterTraceListener>, se genera un nombre de archivo sin extensión. Si implementa una escucha personalizada, también puede utilizar este atributo para recibir datos de inicialización distintos de un nombre de archivo. Por ejemplo, puede especificar un identificador de la base de datos para este atributo.  
  
 Puede configurar una escucha de seguimiento personalizada para enviar las trazas en la conexión, por ejemplo, a una base de datos remota. Como un implementador de la aplicación, debería exigir un control de acceso apropiado en los registros de seguimiento en el equipo remoto.  
  
 También puede configurar mediante programación una escucha de seguimiento. Para obtener más información, consulte [Cómo: crear e inicializar agentes de escucha de seguimiento](http://go.microsoft.com/fwlink/?LinkId=94648) y [crear un TraceListener personalizado](http://go.microsoft.com/fwlink/?LinkId=96239).  
  
> [!CAUTION]
>  Puesto que `System.Diagnostics.XmlWriterTraceListener` no es seguro para subprocesos, el origen de seguimiento puede bloquear los recursos de forma exclusiva al generar trazas. Cuando muchos subprocesos generan trazas para un origen de seguimiento configurado para utilizar esta escucha, puede producirse una contención de recursos, que genera un problema de rendimiento importante. Para solucionar este problema, debería implementar una escucha personalizada que sea segura para subprocesos.  
  
## <a name="trace-level"></a>Nivel de seguimiento  
 El nivel de seguimiento está controlado por el valor `switchValue` del origen de seguimiento. En la siguiente tabla se describen los niveles de seguimiento disponibles.  
  
|Nivel de seguimiento|Naturaleza de los eventos seguidos|Contenido de los eventos seguidos|Eventos de los que se realiza un seguimiento|Destino del usuario|  
|-----------------|----------------------------------|-----------------------------------|--------------------|-----------------|  
|Desactivado|N/D|N/D|No se emiten seguimientos.|N/D|  
|Crítico|Eventos "negativos": eventos que indican un procesamiento inesperado o una condición de error.||Se registran las excepciones no controladas, incluidas las siguientes:<br /><br /> -OutOfMemoryException<br />-ThreadAbortException (el CLR invoca a cualquier ThreadAbortExceptionHandler)<br />-StackOverflowException (no se puede detectar)<br />-ConfigurationErrorsException<br />-SEHException<br />-Errores de inicio la aplicación<br />-Eventos Failfast<br />-El sistema se bloquea<br />-Mensajes dudosos: seguimientos que hacen que la aplicación genere un error de mensajes.|Administradores<br /><br /> Desarrolladores de aplicaciones|  
|Error|Eventos "negativos": eventos que indican un procesamiento inesperado o una condición de error.|Se ha producido un procesamiento inesperado. La aplicación no pudo realizar una tarea como se esperaba. Sin embargo, la aplicación todavía está en funcionamiento y ejecutándose.|Se registran todas las excepciones.|Administradores<br /><br /> Desarrolladores de aplicaciones|  
|Advertencia|Eventos "negativos": eventos que indican un procesamiento inesperado o una condición de error.|Se ha producido o puede producirse un posible problema, pero la aplicación todavía funciona correctamente. Sin embargo, puede no continuar funcionando correctamente.|-La aplicación está recibiendo más solicitudes que permite su configuración de limitación.<br />-La cola receptora está cerca de su capacidad máxima configurada.<br />-El tiempo de espera superado.<br />-Rechazo de las credenciales.|Administradores<br /><br /> Desarrolladores de aplicaciones|  
|Información|Eventos "Positivos": eventos que marcan hitos correctos|Hitos importantes y correctos de ejecución de la aplicación, independientemente de si la aplicación funciona correctamente o no.|En general, se generan mensajes útiles para supervisar y diagnosticar el estado del sistema, medir el rendimiento o el perfil. Puede usar esta información para la planeación de la capacidad y la administración del rendimiento:<br /><br /> -Se crean canales.<br />-Se crean escuchas del punto de conexión.<br />-Mensaje entra/abandona el transporte.<br />-Se recupera el token de seguridad.<br />-Se lee el valor de configuración.|Administradores<br /><br /> Desarrolladores de aplicaciones<br /><br /> Desarrolladores de productos.|  
|Detallado|Eventos "Positivos": eventos que marcan hitos correctos.|Se emiten eventos de bajo nivel tanto para el código de usuario como para el servicio.|En general, puede utilizar este nivel para depuración u optimización de la aplicación.<br /><br /> -Encabezado de mensaje también se entiende.|Administradores<br /><br /> Desarrolladores de aplicaciones<br /><br /> Desarrolladores de productos.|  
|ActivityTracing||Transmitir eventos entre actividades de procesamiento y componentes.|Este nivel permite a los administradores y programadores poner en correlación las aplicaciones que se encuentran en el mismo dominio de aplicación:<br /><br /> -Seguimiento de los límites de actividad, como iniciar o detener.<br />-Seguimiento de las transferencias.|Todas|  
|Todas||La aplicación puede funcionar correctamente. Se emiten todos los eventos.|Todos los eventos anteriores.|Todas|  
  
 Los niveles de Detallado a Crítico se apilan unos encima de otros, es decir, cada nivel de seguimiento incluye todos los niveles anteriores él excepto el nivel Off. Por ejemplo, una escucha que realiza escuchas en el nivel de advertencia recibe trazas de Crítico, Error, y Advertencia. Todos los niveles incluye los eventos de Detallado a Crítico y eventos de seguimiento de actividad.  
  
> [!CAUTION]
>  Los niveles de Información, Detallado, y ActivityTracing generan muchas trazas, lo que puede afectar negativamente al rendimiento de los mensajes si ha agotado todos los recursos disponibles en el equipo.  
  
## <a name="configuring-activity-tracing-and-propagation-for-correlation"></a>Configurar el seguimiento de actividad y la propagación para la correlación  
 El valor `activityTracing` especificado para el atributo `switchValue` se utiliza para habilitar el seguimiento de actividad, que emite las trazas para los límites de actividad y las transferencias dentro de los extremos.  
  
> [!NOTE]
>  Cuando se utilizan ciertas características de extensibilidad de WCF, podría obtener un <xref:System.NullReferenceException> cuando está habilitado el seguimiento de la actividad. Para solucionar este problema, compruebe el archivo de configuración de la aplicación y asegúrese de que el atributo `switchValue` para el origen de seguimiento de traza no está establecido en `activityTracing`.  
  
 El atributo `propagateActivity` indica si la actividad se debería propagar a otros extremos que participan en el intercambio de mensajes. Estableciendo este valor en `true`, puede coger archivos de seguimiento generados por dos extremos cualesquiera y observar cómo un conjunto de trazas en un extremo fluyó a un conjunto de rastros de otro extremo.  
  
 Para obtener más información acerca del seguimiento de actividad y propagación, vea [propagación](../../../../../docs/framework/wcf/diagnostics/tracing/propagation.md).  
  
 Ambos `propagateActivity` y `ActivityTracing` valores booleanos se aplican a la System.ServiceModel TraceSource. El `ActivityTracing` valor también se aplica a cualquier origen de seguimiento, incluido WCF o las definidas por el usuario.  
  
 No puede utilizar el atributo `propagateActivity` con orígenes de seguimiento definidos por el usuario. Para la propagación del identificador de actividad de código de usuario, asegúrese de no establecer ServiceModel `ActivityTracing`, mientras todavía tenga el atributo ServiceModel `propagateActivity` establecido en `true`.  
  
## <a name="see-also"></a>Vea también  
 [Traza](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [Creación e inicialización de agentes de escucha de seguimiento](http://go.microsoft.com/fwlink/?LinkId=94648)  
 [Crear un TraceListener personalizado](http://go.microsoft.com/fwlink/?LinkId=96239)

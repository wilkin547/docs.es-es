---
title: Configurar seguimiento
description: Obtenga información acerca de cómo habilitar el seguimiento, configurar orígenes de seguimiento, establecer la propagación y el seguimiento de la actividad, y establecer agentes de escucha de seguimiento para obtener acceso a los seguimientos en WCF.
ms.date: 03/30/2017
helpviewer_keywords:
- tracing [WCF]
ms.assetid: 82922010-e8b3-40eb-98c4-10fc05c6d65d
ms.openlocfilehash: 55d701ee6769099698d2fd869a1502d94237b5a8
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245354"
---
# <a name="configuring-tracing"></a>Configurar seguimiento
En este tema se describe cómo se puede habilitar el seguimiento, configurar los orígenes de seguimiento para emitir trazas y establecer niveles de seguimiento, establecer el seguimiento y la propagación de actividades para admitir la correlación de seguimiento de un extremo a otro, y establecer escuchas de seguimiento para tener acceso a las trazas.  
  
 Para ver las recomendaciones de configuración de seguimiento en el entorno de producción o depuración, consulte la [configuración recomendada para el seguimiento y el registro de mensajes](recommended-settings-for-tracing-and-message-logging.md).  
  
> [!IMPORTANT]
> En Windows 8 debe ejecutar la aplicación elevada (ejecutar como administrador) para que la aplicación genere los registros de seguimiento.  
  
## <a name="enabling-tracing"></a>La habilitación del seguimiento  
 Windows Communication Foundation (WCF) genera los datos siguientes para el seguimiento de diagnóstico:  
  
- Realiza un seguimiento de los hitos del proceso en todos los componentes de las aplicaciones, como llamadas de operación, excepciones de código, advertencias y otros eventos de procesamiento significativos.  
  
- Eventos de error de Windows cuando la característica de seguimiento no funciona bien. Consulte [registro de eventos](../event-logging/index.md).  
  
 El seguimiento de WCF se basa en <xref:System.Diagnostics> . Para usar el seguimiento, debe definir los orígenes de seguimiento en el archivo de configuración o en el código. WCF define un origen de seguimiento para cada ensamblado de WCF. El `System.ServiceModel` origen de seguimiento es el origen de seguimiento de WCF más general y registra los hitos de procesamiento a través de la pila de comunicación de WCF, desde la entrada/salida del transporte hasta la entrada/salida del código de usuario. El origen de seguimiento `System.ServiceModel.MessageLogging` graba todos los mensajes que fluyen a través del sistema.  
  
 De forma predeterminada, el seguimiento no está habilitado. Para activar el seguimiento, debe crear un agente de escucha de seguimiento y establecer un nivel de seguimiento distinto de "desactivado" para el origen de seguimiento seleccionado en la configuración; de lo contrario, WCF no genera ningún seguimiento. Si no especifica una escucha, el seguimiento se deshabilita automáticamente. Si se define una escucha pero no se especifica ningún nivel, el nivel se establece de forma predeterminada en "Off", lo que significa que no se emite ningún seguimiento.  
  
 Si usa puntos de extensibilidad de WCF como invocadores de operación personalizados, debe emitir sus propios seguimientos. Esto se debe a que, si implementa un punto de extensibilidad, WCF ya no puede emitir los seguimientos estándar en la ruta de acceso predeterminada. Si no implementa la compatibilidad con el seguimiento manual mediante la emisión de seguimientos, puede que no vea los seguimientos que espera.  
  
 Puede configurar el seguimiento editando el archivo de configuración de la aplicación, ya sea Web.config para aplicaciones hospedadas en web o Appname.exe.config para aplicaciones autohospedadas. A continuación se muestra un ejemplo de dicha modificación: Para obtener más información sobre esta configuración, vea la sección "configuración de agentes de escucha de seguimiento para consumir seguimientos".  
  
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
> Para editar el archivo de configuración de un proyecto de servicio de WCF en Visual Studio, haga clic con el botón derecho en el archivo de configuración de la aplicación, ya sea Web.config para aplicaciones hospedadas en web o Appname.exe.config para la aplicación autohospedada en **Explorador de soluciones**. A continuación, elija el elemento de menú contextual **Editar configuración de WCF** . Esto inicia la [herramienta editor de configuración (SvcConfigEditor.exe)](../../configuration-editor-tool-svcconfigeditor-exe.md), que le permite modificar la configuración de los servicios WCF mediante una interfaz gráfica de usuario.  
  
## <a name="configuring-trace-sources-to-emit-traces"></a>Configurar los orígenes de seguimiento para emitir trazas  
 WCF define un origen de seguimiento para cada ensamblado. Las escuchas definidas para ese origen tienen acceso a las trazas generadas dentro de un ensamblado. Se definen los orígenes de seguimiento siguientes:  
  
- System. ServiceModel: registra todas las fases del procesamiento de WCF, cada vez que se lee la configuración, se procesa un mensaje en el transporte, el procesamiento de seguridad, se envía un mensaje en el código de usuario, etc.  
  
- System.ServiceModel.MessageLogging: Registra todos los mensajes que fluyen a través del sistema.  
  
- System.IdentityModel.  
  
- System.ServiceModel.Activation.  
  
- System.IO.Log: Registro para la interfaz .NET Framework al Sistema de archivos de registro comunes (CLFS).  
  
- System.Runtime.Serialization: Se registra cuando los objetos se leen o escriben.  
  
- CardSpace.  
  
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
  
 Para obtener más información sobre cómo crear orígenes de seguimiento definidos por el usuario, vea [extender el seguimiento](../../samples/extending-tracing.md).  
  
## <a name="configuring-trace-listeners-to-consume-traces"></a>Configurar las escuchas para consumir trazas  
 En tiempo de ejecución, WCF suministra datos de seguimiento a los agentes de escucha, que procesan los datos. WCF proporciona varios agentes de escucha predefinidos para <xref:System.Diagnostics> , que difieren en el formato que usan para la salida. También puede agregar tipos de escucha personalizados.  
  
 Puede utilizar `add` para especificar el nombre y tipo de agente de escucha de seguimiento que desea utilizar. En nuestra configuración de ejemplo, hemos llamado `traceListener` al agente de escucha y hemos agregado el agente de escucha de seguimiento estándar de .NET Framework (`System.Diagnostics.XmlWriterTraceListener`) como el tipo que deseamos utilizar. Puede agregar cualquier número de escuchas de seguimiento para cada origen. Si la escucha de seguimiento emite el seguimiento a un archivo, debe especificar la ubicación del archivo de salida y el nombre en el archivo de configuración. Esto se hace estableciendo `initializeData` en el nombre del archivo para esa escucha. Si no especifica un nombre de archivo, se genera un nombre de archivo aleatorio basado en el tipo de escucha utilizado. Si se utiliza <xref:System.Diagnostics.XmlWriterTraceListener>, se genera un nombre de archivo sin extensión. Si implementa una escucha personalizada, también puede utilizar este atributo para recibir datos de inicialización distintos de un nombre de archivo. Por ejemplo, puede especificar un identificador de la base de datos para este atributo.  
  
 Puede configurar una escucha de seguimiento personalizada para enviar las trazas en la conexión, por ejemplo, a una base de datos remota. Como un implementador de la aplicación, debería exigir un control de acceso apropiado en los registros de seguimiento en el equipo remoto.  
  
 También puede configurar mediante programación una escucha de seguimiento. Para obtener más información, vea [Cómo: crear e inicializar agentes de escucha de seguimiento](../../../debug-trace-profile/how-to-create-and-initialize-trace-listeners.md) y [crear un TraceListener personalizado](https://docs.microsoft.com/archive/msdn-magazine/2006/april/clr-inside-out-extending-system-diagnostics).  
  
> [!CAUTION]
> Puesto que `System.Diagnostics.XmlWriterTraceListener` no es seguro para subprocesos, el origen de seguimiento puede bloquear los recursos de forma exclusiva al generar trazas. Cuando muchos subprocesos generan trazas para un origen de seguimiento configurado para utilizar esta escucha, puede producirse una contención de recursos, que genera un problema de rendimiento importante. Para solucionar este problema, debería implementar una escucha personalizada que sea segura para subprocesos.  
  
## <a name="trace-level"></a>Nivel de seguimiento  
 El nivel de seguimiento está controlado por el valor `switchValue` del origen de seguimiento. En la siguiente tabla se describen los niveles de seguimiento disponibles.  
  
|Nivel de seguimiento|Naturaleza de los eventos seguidos|Contenido de los eventos seguidos|Eventos de los que se realiza un seguimiento|Destino del usuario|  
|-----------------|----------------------------------|-----------------------------------|--------------------|-----------------|  
|Desactivado|N/D|N/D|No se emiten seguimientos.|N/D|  
|Crítica|Eventos "negativos": eventos que indican un procesamiento inesperado o una condición de error.||Se registran las excepciones no controladas, incluidas las siguientes:<br /><br /> -OutOfMemoryException<br />-ThreadAbortException (el CLR invoca cualquier ThreadAbortExceptionHandler)<br />-StackOverflowException (no se puede detectar)<br />-ConfigurationErrorsException<br />-SEHException<br />-Errores de inicio de la aplicación<br />-Eventos FailFast<br />-El sistema deja de responder<br />-Mensajes dudosos: seguimientos de mensajes que provocan un error en la aplicación.|Administradores<br /><br /> Desarrolladores de aplicaciones|  
|Error|Eventos "negativos": eventos que indican un procesamiento inesperado o una condición de error.|Se ha producido un procesamiento inesperado. La aplicación no pudo realizar una tarea como se esperaba. Sin embargo, la aplicación todavía está en funcionamiento y ejecutándose.|Se registran todas las excepciones.|Administradores<br /><br /> Desarrolladores de aplicaciones|  
|Advertencia|Eventos "negativos": eventos que indican un procesamiento inesperado o una condición de error.|Se ha producido o puede producirse un posible problema, pero la aplicación todavía funciona correctamente. Sin embargo, puede no continuar funcionando correctamente.|-La aplicación recibe más solicitudes de las que permite la configuración de limitación.<br />-La cola receptora está cerca de su capacidad máxima configurada.<br />-Se ha superado el tiempo de espera.<br />-Se rechazan las credenciales.|Administradores<br /><br /> Desarrolladores de aplicaciones|  
|Información|Eventos "positivos": eventos que marcan hitos correctos|Hitos importantes y correctos de ejecución de la aplicación, independientemente de si la aplicación funciona correctamente o no.|En general, se generan mensajes útiles para supervisar y diagnosticar el estado del sistema, medir el rendimiento o el perfil. Puede usar esta información para la planeación de la capacidad y la administración del rendimiento:<br /><br /> -Se crean canales.<br />-Se crean agentes de escucha del extremo.<br />-El mensaje entra o sale del transporte.<br />-Se recupera el token de seguridad.<br />-Se lee la configuración.|Administradores<br /><br /> Desarrolladores de aplicaciones<br /><br /> Desarrolladores de productos.|  
|Verbose|Eventos "positivos": eventos que marcan hitos correctos.|Se emiten eventos de bajo nivel para el código de usuario y el servicio.|En general, puede utilizar este nivel para depuración u optimización de la aplicación.<br /><br /> -Encabezado de mensaje entendido.|Administradores<br /><br /> Desarrolladores de aplicaciones<br /><br /> Desarrolladores de productos.|  
|ActivityTracing||Transmitir eventos entre actividades de procesamiento y componentes.|Este nivel permite a los administradores y programadores poner en correlación las aplicaciones que se encuentran en el mismo dominio de aplicación:<br /><br /> : Realiza un seguimiento de los límites de actividad, como iniciar o detener.<br />: Realiza un seguimiento de las transferencias.|All|  
|All||La aplicación puede funcionar correctamente. Se emiten todos los eventos.|Todos los eventos anteriores.|Todo|  
  
 Los niveles de Detallado a Crítico se apilan unos encima de otros, es decir, cada nivel de seguimiento incluye todos los niveles anteriores él excepto el nivel Off. Por ejemplo, una escucha que realiza escuchas en el nivel de advertencia recibe trazas de Crítico, Error, y Advertencia. Todos los niveles incluye los eventos de Detallado a Crítico y eventos de seguimiento de actividad.  
  
> [!CAUTION]
> Los niveles de Información, Detallado, y ActivityTracing generan muchas trazas, lo que puede afectar negativamente al rendimiento de los mensajes si ha agotado todos los recursos disponibles en el equipo.  
  
## <a name="configuring-activity-tracing-and-propagation-for-correlation"></a>Configurar el seguimiento de actividad y la propagación para la correlación  
 El valor `activityTracing` especificado para el atributo `switchValue` se utiliza para habilitar el seguimiento de actividad, que emite las trazas para los límites de actividad y las transferencias dentro de los puntos de conexión.  
  
> [!NOTE]
> Cuando se usan ciertas características de extensibilidad en WCF, es posible que obtenga una <xref:System.NullReferenceException> cuando esté habilitada la traza de la actividad. Para solucionar este problema, compruebe el archivo de configuración de la aplicación y asegúrese de que el atributo `switchValue` para el origen de seguimiento de traza no está establecido en `activityTracing`.  
  
 El atributo `propagateActivity` indica si la actividad se debería propagar a otros extremos que participan en el intercambio de mensajes. Estableciendo este valor en `true`, puede coger archivos de seguimiento generados por dos puntos de conexión cualesquiera y observar cómo un conjunto de trazas en un punto de conexión fluyó a un conjunto de rastros de otro punto de conexión.  
  
 Para obtener más información sobre la propagación y el seguimiento de la actividad, consulte [propagación](propagation.md).  
  
 Tanto `propagateActivity` como `ActivityTracing` los valores booleanos se aplican a System. ServiceModel TraceSource. El `ActivityTracing` valor también se aplica a cualquier origen de seguimiento, incluidos WCF o los definidos por el usuario.  
  
 No puede utilizar el atributo `propagateActivity` con orígenes de seguimiento definidos por el usuario. Para la propagación del identificador de actividad de código de usuario, asegúrese de no establecer ServiceModel `ActivityTracing`, mientras todavía tenga el atributo ServiceModel `propagateActivity` establecido en `true`.  
  
## <a name="see-also"></a>Vea también

- [Seguimiento](index.md)
- [Administración y diagnóstico](../index.md)
- [Procedimiento para crear e inicializar agentes de escucha de seguimiento](../../../debug-trace-profile/how-to-create-and-initialize-trace-listeners.md)
- [Crear un agente de escucha de seguimiento personalizado](https://docs.microsoft.com/archive/msdn-magazine/2006/april/clr-inside-out-extending-system-diagnostics)

---
title: Procedimiento para usar TraceSource y filtros con agentes de escucha de seguimiento
description: Utilice la clase TraceSource y filtros con agentes de escucha de seguimiento en .NET. TraceSource reemplaza los métodos estáticos de las clases anteriores de seguimiento y de depuración.
ms.date: 03/30/2017
helpviewer_keywords:
- initializing trace listeners
- configuration files [.NET Framework], trace listeners
- app.config files, trace listeners
- levels of writing trace messages
- trace listeners, TraceSource class
- application configuration files, trace listeners
- filters, trace listeners
- TraceSource class, trace listeners
- trace listeners, creating
- trace listeners, filters
- trace listeners, initializing
ms.assetid: 21dc2169-947d-453a-b0e2-3dac3ba0cc9f
ms.openlocfilehash: 432c866f7c3ca1fd59f8f3d36acd61740b6584c0
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051264"
---
# <a name="how-to-use-tracesource-and-filters-with-trace-listeners"></a>Procedimiento para usar TraceSource y filtros con agentes de escucha de seguimiento
Una de las nuevas características de la versión 2.0 de .NET Framework es un sistema de seguimiento mejorado. La idea básica no se ha modificado: se envían mensajes de seguimiento a través de conmutadores a agentes de escucha, que notifican los datos a un medio de salida asociado. Una diferencia principal de la versión 2.0 es que los seguimientos se pueden iniciar a través de instancias de la clase <xref:System.Diagnostics.TraceSource>. <xref:System.Diagnostics.TraceSource> está pensada para funcionar como un sistema de seguimiento mejorado y se puede usar en lugar de los métodos estáticos de las clases anteriores de seguimiento <xref:System.Diagnostics.Trace> y <xref:System.Diagnostics.Debug>. Las clases <xref:System.Diagnostics.Trace> y <xref:System.Diagnostics.Debug> conocidas siguen existiendo, pero la práctica recomendada es usar la clase <xref:System.Diagnostics.TraceSource> para realizar el seguimiento.  
  
 En este tema se describe el uso de <xref:System.Diagnostics.TraceSource> junto con un archivo de configuración de aplicación.  Es posible, aunque no aconsejable, realizar el seguimiento mediante <xref:System.Diagnostics.TraceSource> sin el uso de un archivo de configuración. Para obtener información sobre el seguimiento sin un archivo de configuración, vea [Cómo: Crear e inicializar orígenes de seguimiento](how-to-create-and-initialize-trace-sources.md).  
  
### <a name="to-create-and-initialize-your-trace-source"></a>Para crear e inicializar el origen de seguimiento  
  
1. El primer paso para instrumentar una aplicación con el seguimiento es crear un origen de seguimiento. En proyectos grandes con diversos componentes, puede crear un origen de seguimiento independiente para cada componente. La práctica recomendada es usar el nombre de la aplicación para el nombre del origen de seguimiento. Así resultará más fácil separar los distintos seguimientos. En el código siguiente se crea un nuevo origen de seguimiento (`mySource)`) y se llama a un método (`Activity1`) que realiza el seguimiento de eventos.  El agente de escucha de seguimiento predeterminado escribe los mensajes de seguimiento.  
  
    ```csharp
    using System;  
    using System.Diagnostics;  
    using System.Threading;  
  
    namespace TraceSourceApp  
    {  
        class Program  
        {  
            private static TraceSource mySource =
                new TraceSource("TraceSourceApp");  
            static void Main(string[] args)  
            {  
                Activity1();  
                mySource.Close();  
                return;  
            }  
            static void Activity1()  
            {  
                mySource.TraceEvent(TraceEventType.Error, 1,
                    "Error message.");  
                mySource.TraceEvent(TraceEventType.Warning, 2,
                    "Warning message.");  
            }  
        }  
    }  
    ```  
  
### <a name="to-create-and-initialize-trace-listeners-and-filters"></a>Para crear e inicializar agentes de escucha de seguimiento y filtros  
  
1. El código en el primer procedimiento no identifica mediante programación ningún agente de escucha de seguimiento ni ningún filtro. El resultado del código es que los mensajes de seguimiento se escriben en el agente de escucha de seguimiento predeterminado. Para configurar agentes de escucha de seguimiento específicos y sus filtros asociados, edite el archivo de configuración que se corresponde con el nombre de la aplicación. En este archivo, puede agregar o quitar un agente de escucha, establecer las propiedades y el filtro para un agente de escucha o quitar agentes de escucha. En el siguiente archivo de configuración de ejemplo se muestra cómo inicializar un agente de escucha de seguimiento de consola y un agente de escucha de seguimiento de escritor de texto para el origen de seguimiento creado en el procedimiento anterior. Además de configurar los agentes de escucha de seguimiento, el archivo de configuración crea filtros para ambos agentes de escucha y un modificador de origen para el origen de seguimiento. Para agregar agentes de escucha de traza se muestran dos técnicas: agregar directamente el agente de escucha al origen de traza y agregar un agente de escucha a la colección de agentes compartidos y después agregarlo por su nombre al origen de traza. Los filtros identificados para los dos agentes de escucha se inicializan con niveles de origen diferentes. Esto tiene como resultado que algunos mensajes se escriban mediante solo uno de los dos agentes de escucha.  
  
    ```xml  
    <configuration>  
      <system.diagnostics>  
        <sources>  
          <source name="TraceSourceApp"
            switchName="sourceSwitch"
            switchType="System.Diagnostics.SourceSwitch">  
            <listeners>  
              <add name="console"
                type="System.Diagnostics.ConsoleTraceListener">  
                <filter type="System.Diagnostics.EventTypeFilter"
                  initializeData="Warning"/>  
              </add>  
              <add name="myListener"/>  
              <remove name="Default"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="sourceSwitch" value="Warning"/>  
        </switches>  
        <sharedListeners>  
          <add name="myListener"
            type="System.Diagnostics.TextWriterTraceListener"
            initializeData="myListener.log">  
            <filter type="System.Diagnostics.EventTypeFilter"
              initializeData="Error"/>  
          </add>  
        </sharedListeners>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
### <a name="to-change-the-level-at-which-a-listener-writes-a-trace-message"></a>Para cambiar el nivel en el que un agente de escucha escribe un mensaje de seguimiento  
  
1. El archivo de configuración inicializa la configuración para el origen de traza en el momento en que se inicializa la aplicación. Para cambiar esa configuración, debe cambiar el archivo de configuración y reiniciar la aplicación, o actualizarla mediante programación usando el método <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=nameWithType>. La aplicación puede cambiar dinámicamente las propiedades establecidas por el archivo de configuración para reemplazar cualquier configuración especificada por el usuario.  Por ejemplo, es posible que quiera asegurarse de que los mensajes críticos siempre se envíen a un archivo de texto, independientemente de las opciones de configuración actuales.  
  
    ```csharp
    using System;  
    using System.Diagnostics;  
    using System.Threading;  
  
    namespace TraceSourceApp  
    {  
        class Program  
        {  
            private static TraceSource mySource =
                new TraceSource("TraceSourceApp");  
            static void Main(string[] args)  
            {  
                Activity1();  
  
                // Change the event type for which tracing occurs.  
                // The console trace listener must be specified
                // in the configuration file. First, save the original  
                // settings from the configuration file.  
                EventTypeFilter configFilter =
                    (EventTypeFilter)mySource.Listeners["console"].Filter;  
  
                // Then create a new event type filter that ensures
                // critical messages will be written.  
                mySource.Listeners["console"].Filter =  
                    new EventTypeFilter(SourceLevels.Critical);  
                Activity2();  
  
                // Allow the trace source to send messages to listeners
                // for all event types. This statement will override
                // any settings in the configuration file.  
                mySource.Switch.Level = SourceLevels.All;  
  
                // Restore the original filter settings.  
                mySource.Listeners["console"].Filter = configFilter;  
                Activity3();  
                mySource.Close();  
                return;  
            }  
            static void Activity1()  
            {  
                mySource.TraceEvent(TraceEventType.Error, 1,
                    "Error message.");  
                mySource.TraceEvent(TraceEventType.Warning, 2,
                    "Warning message.");  
            }  
            static void Activity2()  
            {  
                mySource.TraceEvent(TraceEventType.Critical, 3,
                    "Critical message.");  
                mySource.TraceInformation("Informational message.");  
            }  
            static void Activity3()  
            {  
                mySource.TraceEvent(TraceEventType.Error, 4,
                    "Error message.");  
                mySource.TraceInformation("Informational message.");  
            }  
        }  
    }  
    ```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventTypeFilter>
- [Procedimiento para crear e inicializar orígenes de seguimiento](how-to-create-and-initialize-trace-sources.md)
- [Agentes de escucha de seguimiento](trace-listeners.md)

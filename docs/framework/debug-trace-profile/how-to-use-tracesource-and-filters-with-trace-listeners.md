---
title: "How to: Use TraceSource and Filters with Trace Listeners | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "initializing trace listeners"
  - "configuration files [.NET Framework], trace listeners"
  - "app.config files, trace listeners"
  - "levels of writing trace messages"
  - "trace listeners, TraceSource class"
  - "application configuration files, trace listeners"
  - "filters, trace listeners"
  - "TraceSource class, trace listeners"
  - "trace listeners, creating"
  - "trace listeners, filters"
  - "trace listeners, initializing"
ms.assetid: 21dc2169-947d-453a-b0e2-3dac3ba0cc9f
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# How to: Use TraceSource and Filters with Trace Listeners
Una de las nuevas características incluidas en la versión 2.0 de .NET Framework es un sistema de traza mejorado.  La premisa básica no se ha modificado: se envían mensajes de traza a los agentes de escucha a través de los modificadores, que proporcionan los datos a un medio de salida asociado.  Una de las principales diferencias de la versión 2.0 es que las trazas se pueden iniciar a través de instancias de la clase <xref:System.Diagnostics.TraceSource>.  <xref:System.Diagnostics.TraceSource> está pensado para funcionar como un sistema de traza mejorado y se puede usar en lugar de los métodos estáticos de las anteriores clases de traza <xref:System.Diagnostics.Trace> y <xref:System.Diagnostics.Debug>.  Las conocidas clases <xref:System.Diagnostics.Trace> y <xref:System.Diagnostics.Debug> todavía existen, pero la práctica recomendada es utilizar la clase <xref:System.Diagnostics.TraceSource> para realizar la traza.  
  
 En este tema se describe el uso de un <xref:System.Diagnostics.TraceSource> acoplado con un archivo de configuración de la aplicación.  Es posible, aunque no se recomienda, realizar la traza utilizando un <xref:System.Diagnostics.TraceSource> sin usar un archivo de configuración.  Para obtener más información acerca de cómo realizar la traza sin un archivo de configuración, vea [Cómo: Crear e inicializar orígenes de seguimiento](../../../docs/framework/debug-trace-profile/how-to-create-and-initialize-trace-sources.md).  
  
### Para crear e inicializar su origen de traza  
  
1.  El primer paso para instrumentar una aplicación con traza consiste en crear un origen de traza.  En proyectos grandes con diversos componentes, puede crear un origen de traza independiente para cada componente.  La práctica recomendada es utilizar el nombre de aplicación para el nombre del origen de traza.  Así resultará más fácil mantener independientes los distintos seguimientos.  El código siguiente crea un nuevo origen de traza \(`mySource)`\) y llama a un método \(`Activity1`\) que efectúa la traza de los eventos.  El agente de escucha de traza predeterminado escribe los mensajes de traza.  
  
    ```  
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
  
### Crear e inicializar agentes de escucha de traza y filtros  
  
1.  El código del primer procedimiento no identifica mediante programación ningún agente de escucha de traza ni ningún filtro.  Por sí solo, el código produce la traza de los mensajes de traza que se escriben en el agente de escucha de traza predeterminado.  Para configurar agentes de escucha de traza específicos y sus filtros asociados, edite el archivo de configuración que corresponde al nombre de su aplicación.  En este archivo, puede agregar o quitar un agente de escucha, establecer las propiedades y filtrar por agente de escucha o quitar dichos agentes.  El siguiente ejemplo de archivo de configuración muestra cómo inicializar un agente de escucha de traza de la consola y un agente de escucha de traza de escritor de texto para el origen de traza que se crea en el procedimiento anterior.  Además de configurar los agentes de escucha de traza, el archivo de configuración filtra por ambos agentes de escucha y crea un modificador de origen para el origen de traza.  Para agregar agentes de escucha de traza se muestran dos técnicas: agregar directamente el agente de escucha al origen de traza y agregar un agente de escucha a la colección de agentes compartidos y después agregarlo por su nombre al origen de traza.  Los filtros identificados para los dos agentes de escucha se inicializan con niveles de origen diferentes.  Esto tiene como resultado que algunos mensajes se escriban mediante solo uno de los dos agentes de escucha.  
  
    ```  
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
  
### Para cambiar el nivel en el que un agente de escucha escribe un mensaje de traza  
  
1.  El archivo de configuración inicializa la configuración para el origen de traza en el momento en que se inicializa la aplicación.  Para cambiar esa configuración, debe cambiar el archivo de configuración y reiniciar la aplicación o actualizar mediante programación la aplicación a través del método <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=fullName>.  La aplicación puede cambiar dinámicamente las propiedades establecidas por el archivo de configuración para reemplazar cualquier configuración especificada por el usuario.  Por ejemplo, podría desear asegurar que siempre envían a los mensajes críticos a un archivo de texto, sin tener en cuenta las opciones de configuración actuales.  
  
    ```  
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
  
## Vea también  
 <xref:System.Diagnostics.TraceSource>   
 <xref:System.Diagnostics.TextWriterTraceListener>   
 <xref:System.Diagnostics.ConsoleTraceListener>   
 <xref:System.Diagnostics.EventTypeFilter>   
 [Cómo: Crear e inicializar orígenes de seguimiento](../../../docs/framework/debug-trace-profile/how-to-create-and-initialize-trace-sources.md)   
 [Trace Listeners](../../../docs/framework/debug-trace-profile/trace-listeners.md)
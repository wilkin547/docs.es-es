---
title: 'Cómo: Crear e inicializar orígenes de seguimiento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- trace sources
- initializing trace sources
- configuration files [.NET Framework], trace sources
ms.assetid: f88dda6f-5fda-45be-9b3c-745a9b708c4d
ms.openlocfilehash: cc2987499aa094960c08d220940fe1aed5440b2d
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449964"
---
# <a name="how-to-create-and-initialize-trace-sources"></a>Cómo: Crear e inicializar orígenes de seguimiento
Las aplicaciones utilizan la clase <xref:System.Diagnostics.TraceSource> para generar seguimientos que pueden asociarse con la aplicación. <xref:System.Diagnostics.TraceSource> proporciona métodos de traza que permiten rastrear fácilmente eventos y datos, así como emitir seguimientos de información. El resultado del seguimiento de <xref:System.Diagnostics.TraceSource> se puede crear e inicializar con o sin archivos de configuración. En este tema se proporcionan instrucciones para ambas opciones. Sin embargo, se recomienda usar archivos de configuración para facilitar la reconfiguración de las trazas generadas por los orígenes de traza en tiempo de ejecución.  
  
### <a name="to-create-and-initialize-a-trace-source-using-a-configuration-file"></a>Para crear e inicializar un origen de traza mediante un archivo de configuración  
  
1. Cree un proyecto de aplicación de consola de Visual Studio (.NET Framework) y reemplace el código proporcionado por el código siguiente. Este código registra errores y advertencias, y muestra algunos de ellos en la consola y otros en el archivo myListener creado por las entradas del archivo de configuración.  
  
     [!code-csharp[TraceSourceExample1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tracesourceexample1/cs/program.cs#1)]
     [!code-vb[TraceSourceExample1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tracesourceexample1/vb/program.vb#1)]  
  
2. Agregue al proyecto un archivo de configuración de la aplicación (si no hay uno) para inicializar el origen de seguimiento denominado `TraceSourceApp` en el ejemplo de código del paso 1.  
  
3. Reemplace el contenido del archivo de configuración predeterminado con la configuración siguiente para inicializar un agente de escucha de seguimiento de consola y un agente de escucha de seguimiento de escritor de texto para el origen de seguimiento creado en el paso 1.  
  
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
                  initializeData="Error"/>  
              </add>  
              <add name="myListener"/>  
              <remove name="Default"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="sourceSwitch" value="Error"/>  
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
  
     Además de configurar los agentes de escucha de traza, el archivo de configuración crea filtros para ambos agentes de escucha y crea un modificador de origen para el origen de traza. Para agregar agentes de escucha de traza se muestran dos técnicas: agregar directamente el agente de escucha al origen de traza y agregar un agente de escucha a la colección de agentes compartidos y después agregarlo por su nombre al origen de traza. Los filtros identificados para los dos agentes de escucha se inicializan con niveles de origen diferentes. Esto tiene como resultado que algunos mensajes se escriban mediante solo uno de los dos agentes de escucha.  
  
     El archivo de configuración inicializa la configuración para el origen de traza en el momento en que se inicializa la aplicación. La aplicación puede cambiar dinámicamente las propiedades establecidas por el archivo de configuración para reemplazar cualquier configuración especificada por el usuario. Por ejemplo, quizás desee asegurarse de que los mensajes críticos siempre se envíen a un archivo de texto, cualesquiera que sean las opciones de configuración actuales. En el ejemplo de código se muestra cómo reemplazar la configuración del archivo de configuración para garantizar que los mensajes críticos se envíen a los agentes de escucha de traza.  
  
     Cambiar los ajustes del archivo de configuración mientras la aplicación se está ejecutando no cambia la configuración inicial. Para cambiar la configuración, debe reiniciar la aplicación o actualizar la aplicación mediante programación usando el método <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=nameWithType>.  
  
### <a name="to-initialize-trace-sources-listeners-and-filters-without-a-configuration-file"></a>Para inicializar orígenes de traza, agentes de escucha y filtros sin archivo de configuración  
  
- Use el código de ejemplo siguiente para habilitar la traza a través de un origen de traza sin usar un archivo de configuración. No es un procedimiento recomendado, pero puede haber circunstancias en las que no desee depender de archivos de configuración para garantizar la traza.  
  
     [!code-csharp[TraceSourceExample2#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tracesourceexample2/cs/program.cs#1)]
     [!code-vb[TraceSourceExample2#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tracesourceexample2/vb/program.vb#1)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventTypeFilter>
- [Traza e instrumentación de aplicaciones](tracing-and-instrumenting-applications.md)

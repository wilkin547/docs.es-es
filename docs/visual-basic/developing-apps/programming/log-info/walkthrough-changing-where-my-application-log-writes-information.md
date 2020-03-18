---
title: Cambiar el lugar en el que My.Application.Log escribe la información
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application.Log object, walkthroughs
- event logs, changing output location
ms.assetid: ecc74f95-743c-450d-93f6-09a30db0fe4a
ms.openlocfilehash: bdee0a91360580b156c1734ef4c82139b18ce2b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74336730"
---
# <a name="walkthrough-changing-where-myapplicationlog-writes-information-visual-basic"></a>Tutorial: Cambiar el lugar en el que My.Application.Log escribe la información (Visual Basic)

Puede usar los objetos `My.Application.Log` y `My.Log` para registrar información sobre los eventos que se producen en su aplicación. Este tutorial muestra cómo reemplazar la configuración predeterminada y hacer que el objeto `Log` escriba en otros agentes de escucha de registro.

## <a name="prerequisites"></a>Requisitos previos

El objeto `Log` puede escribir información en varios agentes de escucha de registro. Debe determinar la configuración actual de los agentes de escucha de registro antes de cambiar las configuraciones. Para obtener más información, consulta [Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).

Es posible que quiera consultar [Cómo: Escribir información de eventos en un archivo de texto](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md) o [Cómo: Escribir el registro de eventos de una aplicación](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md).

### <a name="to-add-listeners"></a>Para agregar agentes de escucha

1. Haga clic con el botón derecho en app.config en el **Explorador de soluciones** y seleccione **Abrir**.

     \- o -

     Si no hay ningún archivo app.config:

    1. En el menú **Proyecto** , elija **Agregar nuevo elemento**.

    2. En el cuadro de diálogo **Agregar nuevo elemento** , seleccione **Archivo de configuración de aplicación**.

    3. Haga clic en **Agregar**.

2. Busque la sección `<listeners>` , bajo la sección `<source>` con el atributo `name` el "DefaultSource", en la sección `<sources>` . La sección `<sources>` está en la sección `<system.diagnostics>` , en la sección de nivel superior `<configuration>` .

3. Agregue estos elementos a la sección `<listeners>` .

    ```xml
    <!-- Uncomment to connect the application file log. -->
    <!-- <add name="FileLog" /> -->
    <!-- Uncomment to connect the event log. -->
    <!-- <add name="EventLog" /> -->
    <!-- Uncomment to connect the event log. -->
    <!-- <add name="Delimited" /> -->
    <!-- Uncomment to connect the XML log. -->
    <!-- <add name="XmlWriter" /> -->
    <!-- Uncomment to connect the console log. -->
    <!-- <add name="Console" /> -->
    ```

4. Quite la marca de comentario de los agentes de escucha de registro que desee que reciban mensajes de `Log` .

5. Busque la sección `<sharedListeners>` , en la sección `<system.diagnostics>` , en la sección de nivel superior `<configuration>` .

6. Agregue estos elementos a la sección `<sharedListeners>` .

    ```xml
    <add name="FileLog"
         type="Microsoft.VisualBasic.Logging.FileLogTraceListener,
               Microsoft.VisualBasic, Version=8.0.0.0,
               Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"
         initializeData="FileLogWriter" />
    <add name="EventLog"
         type="System.Diagnostics.EventLogTraceListener,
               System, Version=2.0.0.0,
               Culture=neutral, PublicKeyToken=b77a5c561934e089"
         initializeData="sample application"/>
    <add name="Delimited"
         type="System.Diagnostics.DelimitedListTraceListener,
               System, Version=2.0.0.0,
               Culture=neutral, PublicKeyToken=b77a5c561934e089"
         initializeData="c:\temp\sampleDelimitedFile.txt"
         traceOutputOptions="DateTime" />
    <add name="XmlWriter"
         type="System.Diagnostics.XmlWriterTraceListener,
               System, Version=2.0.0.0,
               Culture=neutral, PublicKeyToken=b77a5c561934e089"
         initializeData="c:\temp\sampleLogFile.xml" />
    <add name="Console"
         type="System.Diagnostics.ConsoleTraceListener,
               System, Version=2.0.0.0,
               Culture=neutral, PublicKeyToken=b77a5c561934e089"
         initializeData="true" />
    ```

7. El contenido del archivo app.config debe ser similar al código XML siguiente:

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <system.diagnostics>
        <sources>
          <!-- This section configures My.Application.Log -->
          <source name="DefaultSource" switchName="DefaultSwitch">
            <listeners>
              <add name="FileLog"/>
              <!-- Uncomment to connect the application file log. -->
              <!-- <add name="FileLog" /> -->
              <!-- Uncomment to connect the event log. -->
              <!-- <add name="EventLog" /> -->
              <!-- Uncomment to connect the event log. -->
              <!-- <add name="Delimited" /> -->
              <!-- Uncomment to connect the XML log. -->
              <!-- <add name="XmlWriter" /> -->
              <!-- Uncomment to connect the console log. -->
              <!-- <add name="Console" /> -->
            </listeners>
          </source>
        </sources>
        <switches>
          <add name="DefaultSwitch" value="Information" />
        </switches>
        <sharedListeners>
          <add name="FileLog"
               type="Microsoft.VisualBasic.Logging.FileLogTraceListener,
                     Microsoft.VisualBasic, Version=8.0.0.0,
                     Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"
               initializeData="FileLogWriter" />
          <add name="EventLog"
               type="System.Diagnostics.EventLogTraceListener,
                     System, Version=2.0.0.0,
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"
               initializeData="sample application"/>
          <add name="Delimited"
               type="System.Diagnostics.DelimitedListTraceListener,
                     System, Version=2.0.0.0,
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"
               initializeData="c:\temp\sampleDelimitedFile.txt"
               traceOutputOptions="DateTime" />
          <add name="XmlWriter"
               type="System.Diagnostics.XmlWriterTraceListener,
                     System, Version=2.0.0.0,
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"
               initializeData="c:\temp\sampleLogFile.xml" />
          <add name="Console"
               type="System.Diagnostics.ConsoleTraceListener,
                     System, Version=2.0.0.0,
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"
               initializeData="true" />
        </sharedListeners>
      </system.diagnostics>
    </configuration>
    ```

### <a name="to-reconfigure-a-listener"></a>Para volver a configurar un agente de escucha

1. Busque el elemento `<add>` del agente de escucha de la sección `<sharedListeners>` .

2. El atributo `type` proporciona el nombre del tipo de agente de escucha. Este tipo debe heredar de la clase <xref:System.Diagnostics.TraceListener> . Use el nombre de tipo con nombre seguro para asegurarse de que se use el tipo correcto. Para obtener más información, consulte la sección "Para hacer referencia a un tipo con nombre seguro" a continuación.

     Algunos tipos válidos que puede usar son:

    - Un agente de escucha <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType> , que escribe en un archivo de registro.

    - Un agente de escucha <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType> , que escribe información en el registro de eventos del equipo especificado por el parámetro `initializeData` .

    - Los agentes de escucha <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType> y <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> , que escriben en el archivo especificado en el parámetro `initializeData` .

    - Un agente de escucha <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType> , que escribe en la consola de línea de comandos.

     Para obtener información sobre dónde escriben información otros tipos de agentes de escucha de registro, consulte la documentación de ese tipo.

3. Cuando la aplicación crea el objeto de agente de escucha de registro, pasa el atributo `initializeData` como el parámetro de constructor. El significado del atributo `initializeData` depende del agente de escucha de seguimiento.

4. Después de crear el agente de escucha de registro, la aplicación establece las propiedades del agente de escucha. Estas propiedades se definen mediante los demás atributos del elemento `<add>` . Para obtener más información sobre las propiedades de un agente de escucha determinado, consulte la documentación de este tipo de agente de escucha.

### <a name="to-reference-a-strongly-named-type"></a>Para hacer referencia a un tipo con nombre seguro

1. Para asegurarse de que se usa el tipo correcto para el agente de escucha de registro, asegúrese de usar el nombre completo del tipo y el nombre de ensamblado con nombre seguro. La sintaxis de un tipo con nombre seguro es la siguiente:

     \<*nombre de tipo*>, \<*nombre de ensamblado*>, \<*número de versión*>, \<*referencia cultural*>, \<*nombre seguro*>

2. Este ejemplo de código muestra cómo determinar el nombre de tipo con nombre seguro para un tipo completo (en este caso, "System.Diagnostics.FileLogTraceListener").

     [!code-vb[VbVbalrMyApplicationLog#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#15)]

     Esta es la salida, que se puede usar para hacer referencia de manera exclusiva a un tipo con nombre seguro, como en el procedimiento "Para agregar agentes de escucha" anterior.

     `Microsoft.VisualBasic.Logging.FileLogTraceListener, Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a`

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceListener>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType>
- <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>
- [Escribir información de eventos en un archivo de texto](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md)
- [Cómo: Escribir el registro de eventos de una aplicación](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md)

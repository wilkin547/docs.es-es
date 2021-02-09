---
description: 'Más información acerca de: Tutorial: Filtrar el resultado de My.Application.Log (Visual Basic)'
title: Filtrar la salida de My.Application.Log
ms.date: 07/20/2015
helpviewer_keywords:
- My.Log object, filtering output
- My.Application.Log object, filtering output
- application event logs, output filtering
ms.assetid: 2c0a457a-38a4-49e1-934d-a51320b7b4ca
ms.openlocfilehash: 0fa64bde27be17b1809e45bfe294e70c7dd33563
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792263"
---
# <a name="walkthrough-filtering-myapplicationlog-output-visual-basic"></a>Tutorial: Filtrar el resultado de My.Application.Log (Visual Basic)

En este tutorial se muestra cómo cambiar el filtrado del registro predeterminado para el objeto `My.Application.Log`, para controlar qué información se pasa desde el objeto `Log` a los agentes de escucha y qué información escriben estos. Puede cambiar el comportamiento del registro incluso después de generar la aplicación, porque la información de configuración se almacena en el archivo de configuración de la aplicación.

## <a name="getting-started"></a>Introducción

Cada mensaje que `My.Application.Log` escribe tiene un nivel de gravedad asociado, que los mecanismos de filtrado usan para controlar el resultado del registro. En esta aplicación de ejemplo se usan métodos `My.Application.Log` para escribir varios mensajes de registro con distintos niveles de gravedad.

#### <a name="to-build-the-sample-application"></a>Para crear la aplicación de ejemplo

1. Abra un proyecto Aplicación Windows de Visual Basic nuevo.

2. Agregue un botón denominado Button1 a Form1.

3. En el controlador de eventos <xref:System.Windows.Forms.Control.Click> para Button1, agregue el código siguiente:

     [!code-vb[VbVbcnMyApplicationLogFiltering#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyApplicationLogFiltering/VB/Form1.vb#1)]

4. Ejecute la aplicación en el depurador.

5. Pulse **Button1**.

     La aplicación escribe la siguiente información en el archivo de registro y de salida de la depuración de la aplicación.

     `DefaultSource Information: 0 : In Button1_Click`

     `DefaultSource Error: 2 : Error in the application.`

6. Cierre la aplicación.

     Para obtener información sobre cómo ver la ventana de salida de la depuración de la aplicación, vea [Resultados (Ventana)](/visualstudio/ide/reference/output-window). Para obtener información sobre la ubicación del archivo de registro de la aplicación, vea [Tutorial: Determinar el lugar en el que My.Application.Log escribe la información (Visual Basic)](walkthrough-determining-where-my-application-log-writes-information.md).

    > [!NOTE]
    > De manera predeterminada, la aplicación vacía el resultado del archivo de registro cuando la aplicación se cierra.

     En el ejemplo anterior, la segunda llamada al método <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A> y la llamada al método <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A> producen una salida del registro, mientras que la primera y la última llamada al método `WriteEntry` no lo hacen. Esto se debe a que los niveles de gravedad de `WriteEntry` y `WriteException` son "Information" y "Error", que permite el filtrado de registro predeterminado del objeto `My.Application.Log`. En cambio, los eventos con niveles de gravedad "Start" y "Stop" no pueden generar el resultado del registro.

## <a name="filtering-for-all-myapplicationlog-listeners"></a>Filtrado para todos los agentes de escucha de My.Application.Log

El objeto `My.Application.Log` usa un objeto <xref:System.Diagnostics.SourceSwitch> denominado `DefaultSwitch` para controlar qué mensajes pasa de los métodos `WriteEntry` y `WriteException` a los agentes de escucha de registro. Puede configurar `DefaultSwitch` en el archivo de configuración de la aplicación estableciendo su valor en uno de los valores de enumeración <xref:System.Diagnostics.SourceLevels>. De manera predeterminada, su valor es "Information".

En esta tabla se muestra el nivel de gravedad necesario para que el registro escriba un mensaje a los agentes de escucha, con un valor `DefaultSwitch` determinado.

|Valor DefaultSwitch|Gravedad del mensaje que se necesita para el resultado|
|---|---|
|`Critical`|`Critical`|
|`Error`|`Critical` o `Error`|
|`Warning`|`Critical`, `Error`o `Warning`|
|`Information`|`Critical`, `Error`, `Warning` o `Information`|
|`Verbose`|`Critical`, `Error`, `Warning`, `Information` o `Verbose`|
|`ActivityTracing`|`Start`, `Stop`, `Suspend`, `Resume` o `Transfer`|
|`All`|Se permiten todos los mensajes.|
|`Off`|Se bloquean todos los mensajes.|

> [!NOTE]
> Los métodos `WriteEntry` y `WriteException` tienen una sobrecarga que no especifica un nivel de gravedad. El nivel de gravedad implícito para la sobrecarga `WriteEntry` es "Information" y el nivel de gravedad implícito para la sobrecarga `WriteException` es "Error".

En esta tabla se explica el resultado del registro que se muestra en el ejemplo anterior: con el valor `DefaultSwitch` predeterminado de "Information", solo la segunda llamada al método `WriteEntry` y la llamada al método `WriteException` generan un resultado del registro.

#### <a name="to-log-only-activity-tracing-events"></a>Para registrar solo los eventos de seguimiento de la actividad

1. Haga clic con el botón derecho en app.config en el **Explorador de soluciones** y seleccione **Abrir**.

     o bien

     Si no hay ningún archivo app.config:

    1. En el menú **Proyecto** , elija **Agregar nuevo elemento**.

    2. En el cuadro de diálogo **Agregar nuevo elemento** , seleccione **Archivo de configuración de aplicación**.

    3. Haga clic en **Agregar**.

2. Busque la sección `<switches>`, en la sección `<system.diagnostics>`, que se encuentra en la sección de nivel superior `<configuration>`.

3. Busque el elemento que agrega `DefaultSwitch` a la colección de modificadores. Este elemento debe ser similar a este:

     `<add name="DefaultSwitch" value="Information" />`

4. Cambie el valor del atributo `value` a "ActivityTracing".

5. El contenido del archivo app.config debe ser similar al código XML siguiente:

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <system.diagnostics>
        <sources>
          <!-- This section configures My.Application.Log -->
          <source name="DefaultSource" switchName="DefaultSwitch">
            <listeners>
              <add name="FileLog"/>
            </listeners>
          </source>
        </sources>
        <switches>
          <add name="DefaultSwitch" value="ActivityTracing" />
        </switches>
        <sharedListeners>
          <add name="FileLog"
               type="Microsoft.VisualBasic.Logging.FileLogTraceListener,
                     Microsoft.VisualBasic, Version=8.0.0.0,
                     Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a,
                     processorArchitecture=MSIL"
               initializeData="FileLogWriter"/>
        </sharedListeners>
      </system.diagnostics>
    </configuration>
    ```

6. Ejecute la aplicación en el depurador.

7. Pulse **Button1**.

     La aplicación escribe la siguiente información en el archivo de registro y de salida de la depuración de la aplicación:

     `DefaultSource Start: 4 : Entering Button1_Click`

     `DefaultSource Stop: 5 : Leaving Button1_Click`

8. Cierre la aplicación.

9. Cambie el valor del atributo `value` de nuevo a "Information".

    > [!NOTE]
    > La configuración del modificador `DefaultSwitch` solo controla `My.Application.Log`. No cambia el comportamiento de las clases <xref:System.Diagnostics.Trace?displayProperty=nameWithType> y <xref:System.Diagnostics.Debug?displayProperty=nameWithType> de .NET.

## <a name="individual-filtering-for-myapplicationlog-listeners"></a>Filtrado individual para los agentes de escucha de My.Application.Log

En el ejemplo anterior se muestra cómo cambiar el filtrado para todos los resultados de `My.Application.Log`. En este ejemplo se muestra cómo filtrar un agente de escucha de registro individual. De manera predeterminada, una aplicación tiene dos agentes de escucha que escriben en el archivo de registro y de salida de la depuración de la aplicación.

El archivo de configuración controla el comportamiento de los agentes de escucha de registro permitiendo que cada uno tenga un filtro, que es similar a un modificador para `My.Application.Log`. Un agente de escucha de registro generará un mensaje solo si la gravedad de este se permite por el filtro del agente de escucha de registro y del `DefaultSwitch` del registro.

En este ejemplo se muestra cómo configurar el filtrado para un nuevo agente de escucha de depuración y agregarlo al objeto `Log`. El agente de escucha de depuración predeterminado debe quitarse del objeto `Log`, por lo que es evidente que los mensajes de depuración provienen del nuevo agente de escucha de depuración.

#### <a name="to-log-only-activity-tracing-events"></a>Para registrar solo los eventos de seguimiento de la actividad

1. Haga clic con el botón derecho en app.config en el **Explorador de soluciones** y seleccione **Abrir**.

     O bien

     Si no hay ningún archivo app.config:

    1. En el menú **Proyecto** , elija **Agregar nuevo elemento**.

    2. En el cuadro de diálogo **Agregar nuevo elemento** , seleccione **Archivo de configuración de aplicación**.

    3. Haga clic en **Agregar**.

2. Haga clic con el botón derecho en app.config en el **Explorador de soluciones**. Pulse **Abrir**.

3. Busque la sección `<listeners>`, en la sección `<source>` con el atributo `name` "DefaultSource", que está en la sección `<sources>`. La sección `<sources>` está en la sección `<system.diagnostics>`, en la sección de nivel superior `<configuration>`.

4. Agregue este elemento a la sección `<listeners>`:

    ```xml
    <!-- Remove the default debug listener. -->
    <remove name="Default"/>
    <!-- Add a filterable debug listener. -->
    <add name="NewDefault"/>
    ```

5. Busque la sección `<sharedListeners>` , en la sección `<system.diagnostics>` , en la sección de nivel superior `<configuration>` .

6. Agregue este elemento a dicha sección `<sharedListeners>` :

    ```xml
    <add name="NewDefault"
         type="System.Diagnostics.DefaultTraceListener,
               System, Version=2.0.0.0, Culture=neutral,
               PublicKeyToken=b77a5c561934e089,
               processorArchitecture=MSIL">
        <filter type="System.Diagnostics.EventTypeFilter"
                initializeData="Error" />
    </add>
    ```

     El filtro <xref:System.Diagnostics.EventTypeFilter> toma uno de los valores de enumeración <xref:System.Diagnostics.SourceLevels> como su atributo `initializeData`.

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
              <!-- Remove the default debug listener. -->
              <remove name="Default"/>
              <!-- Add a filterable debug listener. -->
              <add name="NewDefault"/>
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
                     Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a,
                     processorArchitecture=MSIL"
               initializeData="FileLogWriter"/>
          <add name="NewDefault"
               type="System.Diagnostics.DefaultTraceListener,
                     System, Version=2.0.0.0, Culture=neutral,
                     PublicKeyToken=b77a5c561934e089,
                     processorArchitecture=MSIL">
            <filter type="System.Diagnostics.EventTypeFilter"
                    initializeData="Error" />
          </add>
        </sharedListeners>
      </system.diagnostics>
    </configuration>
    ```

8. Ejecute la aplicación en el depurador.

9. Pulse **Button1**.

     La aplicación escribe la siguiente información en el archivo de registro de la aplicación:

     `Default Information: 0 : In Button1_Click`

     `Default Error: 2 : Error in the application.`

     La aplicación escribe menos información en el resultado de depuración de la aplicación porque el filtrado es más restrictivo.

     `Default Error   2   Error`

10. Cierre la aplicación.

Para obtener más información sobre cómo cambiar la configuración del registro después de la implementación, vea [Trabajar con registros de aplicaciones en Visual Basic](working-with-application-logs.md).

## <a name="see-also"></a>Vea también

- [Tutorial: Determinar el lugar en el que My.Application.Log escribe la información](walkthrough-determining-where-my-application-log-writes-information.md)
- [Tutorial: Cambiar el lugar donde My.Application.Log escribe información](walkthrough-changing-where-my-application-log-writes-information.md)
- [Tutorial: Crear agentes de escucha de registro personalizados](walkthrough-creating-custom-log-listeners.md)
- [Escribir mensajes de registro](how-to-write-log-messages.md)
- [Modificadores de seguimiento](../../../../framework/debug-trace-profile/trace-switches.md)
- [Registrar información de la aplicación](index.md)

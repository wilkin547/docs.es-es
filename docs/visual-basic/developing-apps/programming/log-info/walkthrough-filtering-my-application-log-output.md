---
title: "Tutorial: Filtrar el resultado de My.Application.Log (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Log (objeto), filtrar el resultado"
  - "My.Application.Log (objeto), filtrar el resultado"
  - "registros de eventos de aplicación, el filtrado de salida"
ms.assetid: 2c0a457a-38a4-49e1-934d-a51320b7b4ca
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Tutorial: Filtrar el resultado de My.Application.Log (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Este tutorial muestra cómo cambiar el filtrado para el registro de forma predeterminada la `My.Application.Log` objeto, para controlar qué información se pasa desde el `Log` objeto para los agentes de escucha y qué información escriben los agentes de escucha. Puede cambiar el comportamiento del registro después de generar la aplicación, porque la información de configuración se almacena en el archivo de configuración de la aplicación.  
  
## <a name="getting-started"></a>Introducción  
 Cada mensaje que `My.Application.Log` escrituras tiene un nivel de gravedad asociado, los mecanismos de filtrado se utilizan para controlar el resultado del registro. Esta aplicación de ejemplo usa `My.Application.Log` métodos para escribir varios mensajes de registro con distintos niveles de gravedad.  
  
#### <a name="to-build-the-sample-application"></a>Para compilar la aplicación de ejemplo  
  
1.  Abra un nuevo [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] el proyecto de aplicación de Windows.  
  
2.  Agregue un botón denominado Button1 a Form1.  
  
3.  En la <xref:System.Windows.Forms.Control.Click> el controlador de eventos de Button1, agregue el código siguiente:  
  
     [!code-vb[VbVbcnMyApplicationLogFiltering#1](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/visualbasic/VbVbcnMyApplicationLogFiltering/Form1.vb#1)]  
  
4.  Ejecute la aplicación en el depurador.  
  
5.  Presione **Button1**.  
  
     La aplicación escribe la información siguiente al archivo de salida y de registro de depuración de la aplicación.  
  
     `DefaultSource Information: 0 : In Button1_Click`  
  
     `DefaultSource Error: 2 : Error in the application.`  
  
6.  Cierre la aplicación.  
  
     Para obtener información sobre cómo ver la ventana de salida de depuración de la aplicación, consulte [ventana Resultados](/visual-studio/ide/reference/output-window). Para obtener información sobre la ubicación del archivo de registro de la aplicación, consulte [Tutorial: determinar donde My.Application.Log escribe información](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).  
  
    > [!NOTE]
    >  De forma predeterminada, la aplicación vacía el archivo de registro generado cuando se cierra la aplicación.  
  
     En el ejemplo anterior, la segunda llamada a la <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A> método y la llamada a la <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A> método genera el resultado del registro, mientras que la primera y última llamadas a la `WriteEntry` no lo hace el método. Esto es porque los niveles de gravedad de `WriteEntry` y `WriteException` son "Información" y "Error", que permiten la `My.Application.Log` del objeto predeterminado de filtrado del registro. Sin embargo, los eventos con niveles de gravedad "Iniciar" y "Detener" no pueden producir la salida de registro.  
  
## <a name="filtering-for-all-myapplicationlog-listeners"></a>Filtrado de todos los agentes de escucha de My.Application.Log  
 El `My.Application.Log` de objeto usa un <xref:System.Diagnostics.SourceSwitch> denominado `DefaultSwitch` para controlar qué mensajes pasa de la `WriteEntry` y `WriteException` métodos a los agentes de escucha de registro. Puede configurar `DefaultSwitch` en el archivo de configuración de la aplicación estableciendo su valor en uno de los <xref:System.Diagnostics.SourceLevels> valores de enumeración. De forma predeterminada, su valor es "Información".  
  
 Esta tabla muestra el nivel de gravedad requerido para que registro que se va a escribir un mensaje en los agentes de escucha, dado un determinado `DefaultSwitch` configuración.  
  
|||  
|-|-|  
|Valor de DefaultSwitch|Gravedad del mensaje requerida para el resultado|  
|`Critical`|`Critical`|  
|`Error`|`Critical` o `Error`|  
|`Warning`|`Critical`, `Error` o `Warning`|  
|`Information`|`Critical`, `Error`, `Warning` o `Information`|  
|`Verbose`|`Critical`, `Error`, `Warning`, `Information` o `Verbose`|  
|`ActivityTracing`|`Start`, `Stop`, `Suspend`, `Resume` o `Transfer`|  
|`All`|Se permiten todos los mensajes.|  
|`Off`|Todos los mensajes están bloqueados.|  
  
> [!NOTE]
>  El `WriteEntry` y `WriteException` métodos tienen una sobrecarga que no especifica un nivel de gravedad. El nivel de gravedad implícito para la `WriteEntry` sobrecarga es "Información" y el nivel de gravedad implícito para la `WriteException` sobrecarga es "Error".  
  
 Esta tabla explica el resultado del registro se muestra en el ejemplo anterior: con el valor predeterminado `DefaultSwitch` establecer "Information", sólo la segunda llamada a la `WriteEntry` método y la llamada a la `WriteException` el resultado del método generan registros.  
  
#### <a name="to-log-only-activity-tracing-events"></a>Para registrar eventos de seguimiento de actividad única  
  
1.  Haga clic en app.config en el **el Explorador de soluciones** y seleccione **abiertos**.  
  
     O bien  
  
     Si no hay ningún archivo app.config:  
  
    1.  En el menú **Proyecto** , elija **Agregar nuevo elemento**.  
  
    2.  En el cuadro de diálogo **Agregar nuevo elemento** , seleccione **Archivo de configuración de aplicación**.  
  
    3.  Haga clic en **Agregar**.  
  
2.  Busque la `<switches>` sección, que se encuentra en la `<system.diagnostics>` sección, que se encuentra en el nivel superior `<configuration>` sección.  
  
3.  Busque el elemento que se agrega `DefaultSwitch` a la colección de modificadores. Debería ser similar a este elemento:  
  
     `<add name="DefaultSwitch" value="Information" />`  
  
4.  Cambie el valor de la `value` atributo a "ActivityTracing".  
  
5.  El contenido del archivo app.config debe ser similar al código XML siguiente:  
  
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
  
6.  Ejecute la aplicación en el depurador.  
  
7.  Presione **Button1**.  
  
     La aplicación escribe la información siguiente al archivo de salida y de registro de depuración de la aplicación:  
  
     `DefaultSource Start: 4 : Entering Button1_Click`  
  
     `DefaultSource Stop: 5 : Leaving Button1_Click`  
  
8.  Cierre la aplicación.  
  
9. Cambie el valor de la `value` atributo "Información".  
  
    > [!NOTE]
    >  El `DefaultSwitch` Cambiar configuración controla sólo `My.Application.Log`. No cambia la [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)] <xref:System.Diagnostics.Trace?displayProperty=fullName> y <xref:System.Diagnostics.Debug?displayProperty=fullName> se comportan las clases.  
  
## <a name="individual-filtering-for-myapplicationlog-listeners"></a>Filtrado para los agentes de escucha de My.Application.Log individual  
 El ejemplo anterior muestra cómo cambiar el filtrado para todos los `My.Application.Log` salida. En este ejemplo se muestra cómo filtrar un agente de escucha de registro individuales. De forma predeterminada, una aplicación tiene dos agentes de escucha que escriben en el resultado de la depuración de la aplicación y el archivo de registro.  
  
 El archivo de configuración controla el comportamiento de los agentes de escucha de registro permitiendo que cada uno tenga un filtro, que es similar a un conmutador para `My.Application.Log`. Un agente de escucha de registro generará un mensaje sólo si la gravedad del mensaje puede por tanto el registro `DefaultSwitch` y filtrar el registro del agente de escucha.  
  
 En este ejemplo se muestra cómo configurar el filtrado para un nuevo agente de escucha de depuración y agregarlo a la `Log` objeto. El agente de escucha de depuración predeterminado debe quitarse de la `Log` del objeto, por lo que resulta evidente que los mensajes de depuración proceden del nuevo agente de escucha de depuración.  
  
#### <a name="to-log-only-activity-tracing-events"></a>Para registrar sólo eventos de seguimiento de actividad  
  
1.  Haga clic en app.config en el **el Explorador de soluciones** y elija **abiertos**.  
  
     O bien  
  
     Si no hay ningún archivo app.config:  
  
    1.  En el menú **Proyecto** , elija **Agregar nuevo elemento**.  
  
    2.  En el cuadro de diálogo **Agregar nuevo elemento** , seleccione **Archivo de configuración de aplicación**.  
  
    3.  Haga clic en **Agregar**.  
  
2.  Haga clic en app.config en **el Explorador de soluciones**. Elija **abiertos**.  
  
3.  Busque la `<listeners>` sección, en la `<source>` sección con el `name` atributo "DefaultSource", que se encuentra en la `<sources>` sección. El `<sources>` sección está bajo la `<system.diagnostics>` sección, en el nivel superior `<configuration>` sección.  
  
4.  Agregue este elemento a la `<listeners>` sección:  
  
    ```xml  
    <!-- Remove the default debug listener. -->  
    <remove name="Default"/>  
    <!-- Add a filterable debug listener. -->  
    <add name="NewDefault"/>  
    ```  
  
5.  Busque la sección `<sharedListeners>` , en la sección `<system.diagnostics>` , en la sección de nivel superior `<configuration>` .  
  
6.  Agregue este elemento a dicha sección `<sharedListeners>` :  
  
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
  
     El <xref:System.Diagnostics.EventTypeFilter> filtro toma uno de los <xref:System.Diagnostics.SourceLevels> valores de enumeración como su `initializeData` atributo.  
  
7.  El contenido del archivo app.config debe ser similar al código XML siguiente:  
  
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
  
8.  Ejecute la aplicación en el depurador.  
  
9. Presione **Button1**.  
  
     La aplicación escribe la información siguiente al archivo de registro de la aplicación:  
  
     `Default Information: 0 : In Button1_Click`  
  
     `Default Error: 2 : Error in the application.`  
  
     La aplicación escribe menos información a los resultados de la depuración de la aplicación debido a que el filtrado más restrictivo.  
  
     `Default Error   2   Error`  
  
10. Cierre la aplicación.  
  
 Para obtener más información acerca de cómo cambiar la configuración del registro después de la implementación, consulte [trabajar con registros de aplicaciones](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Determinar el lugar donde My.Application.Log escribe información](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)   
 [Tutorial: Cambiar el lugar donde My.Application.Log escribe información](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)   
 [Tutorial: Crear agentes de escucha de registro personalizado](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-creating-custom-log-listeners.md)   
 [Cómo: escribir mensajes de registro](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)   
 [Modificadores de seguimiento](../Topic/Trace%20Switches.md)   
 [Información de registro de la aplicación](../../../../visual-basic/developing-apps/programming/log-info/logging-information-from-the-application.md)
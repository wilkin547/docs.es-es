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
# <a name="walkthrough-changing-where-myapplicationlog-writes-information-visual-basic"></a><span data-ttu-id="a3879-102">Tutorial: Cambiar el lugar en el que My.Application.Log escribe la información (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a3879-102">Walkthrough: Changing Where My.Application.Log Writes Information (Visual Basic)</span></span>

<span data-ttu-id="a3879-103">Puede usar los objetos `My.Application.Log` y `My.Log` para registrar información sobre los eventos que se producen en su aplicación.</span><span class="sxs-lookup"><span data-stu-id="a3879-103">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span> <span data-ttu-id="a3879-104">Este tutorial muestra cómo reemplazar la configuración predeterminada y hacer que el objeto `Log` escriba en otros agentes de escucha de registro.</span><span class="sxs-lookup"><span data-stu-id="a3879-104">This walkthrough shows how to override the default settings and cause the `Log` object to write to other log listeners.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a3879-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a3879-105">Prerequisites</span></span>

<span data-ttu-id="a3879-106">El objeto `Log` puede escribir información en varios agentes de escucha de registro.</span><span class="sxs-lookup"><span data-stu-id="a3879-106">The `Log` object can write information to several log listeners.</span></span> <span data-ttu-id="a3879-107">Debe determinar la configuración actual de los agentes de escucha de registro antes de cambiar las configuraciones.</span><span class="sxs-lookup"><span data-stu-id="a3879-107">You need to determine the current configuration of the log listeners before changing the configurations.</span></span> <span data-ttu-id="a3879-108">Para obtener más información, consulta [Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span><span class="sxs-lookup"><span data-stu-id="a3879-108">For more information, see [Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span></span>

<span data-ttu-id="a3879-109">Es posible que quiera consultar [Cómo: Escribir información de eventos en un archivo de texto](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md) o [Cómo: Escribir el registro de eventos de una aplicación](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md).</span><span class="sxs-lookup"><span data-stu-id="a3879-109">You may want to review [How to: Write Event Information to a Text File](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md) or [How to: Write to an Application Event Log](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md).</span></span>

### <a name="to-add-listeners"></a><span data-ttu-id="a3879-110">Para agregar agentes de escucha</span><span class="sxs-lookup"><span data-stu-id="a3879-110">To add listeners</span></span>

1. <span data-ttu-id="a3879-111">Haga clic con el botón derecho en app.config en el **Explorador de soluciones** y seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="a3879-111">Right-click app.config in **Solution Explorer** and choose **Open**.</span></span>

     <span data-ttu-id="a3879-112">\- o -</span><span class="sxs-lookup"><span data-stu-id="a3879-112">\- or -</span></span>

     <span data-ttu-id="a3879-113">Si no hay ningún archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="a3879-113">If there is no app.config file:</span></span>

    1. <span data-ttu-id="a3879-114">En el menú **Proyecto** , elija **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="a3879-114">On the **Project** menu, choose **Add New Item**.</span></span>

    2. <span data-ttu-id="a3879-115">En el cuadro de diálogo **Agregar nuevo elemento** , seleccione **Archivo de configuración de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="a3879-115">From the **Add New Item** dialog box, select **Application Configuration File**.</span></span>

    3. <span data-ttu-id="a3879-116">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a3879-116">Click **Add**.</span></span>

2. <span data-ttu-id="a3879-117">Busque la sección `<listeners>` , bajo la sección `<source>` con el atributo `name` el "DefaultSource", en la sección `<sources>` .</span><span class="sxs-lookup"><span data-stu-id="a3879-117">Locate the `<listeners>` section, under the `<source>` section with the `name` attribute "DefaultSource", in the `<sources>` section.</span></span> <span data-ttu-id="a3879-118">La sección `<sources>` está en la sección `<system.diagnostics>` , en la sección de nivel superior `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="a3879-118">The `<sources>` section is in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

3. <span data-ttu-id="a3879-119">Agregue estos elementos a la sección `<listeners>` .</span><span class="sxs-lookup"><span data-stu-id="a3879-119">Add these elements to that `<listeners>` section.</span></span>

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

4. <span data-ttu-id="a3879-120">Quite la marca de comentario de los agentes de escucha de registro que desee que reciban mensajes de `Log` .</span><span class="sxs-lookup"><span data-stu-id="a3879-120">Uncomment the log listeners that you want to receive `Log` messages.</span></span>

5. <span data-ttu-id="a3879-121">Busque la sección `<sharedListeners>` , en la sección `<system.diagnostics>` , en la sección de nivel superior `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="a3879-121">Locate the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

6. <span data-ttu-id="a3879-122">Agregue estos elementos a la sección `<sharedListeners>` .</span><span class="sxs-lookup"><span data-stu-id="a3879-122">Add these elements to that `<sharedListeners>` section.</span></span>

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

7. <span data-ttu-id="a3879-123">El contenido del archivo app.config debe ser similar al código XML siguiente:</span><span class="sxs-lookup"><span data-stu-id="a3879-123">The content of the app.config file should be similar to the following XML:</span></span>

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

### <a name="to-reconfigure-a-listener"></a><span data-ttu-id="a3879-124">Para volver a configurar un agente de escucha</span><span class="sxs-lookup"><span data-stu-id="a3879-124">To reconfigure a listener</span></span>

1. <span data-ttu-id="a3879-125">Busque el elemento `<add>` del agente de escucha de la sección `<sharedListeners>` .</span><span class="sxs-lookup"><span data-stu-id="a3879-125">Locate the listener's `<add>` element from the `<sharedListeners>` section.</span></span>

2. <span data-ttu-id="a3879-126">El atributo `type` proporciona el nombre del tipo de agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="a3879-126">The `type` attribute gives the name of the listener type.</span></span> <span data-ttu-id="a3879-127">Este tipo debe heredar de la clase <xref:System.Diagnostics.TraceListener> .</span><span class="sxs-lookup"><span data-stu-id="a3879-127">This type must inherit from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="a3879-128">Use el nombre de tipo con nombre seguro para asegurarse de que se use el tipo correcto.</span><span class="sxs-lookup"><span data-stu-id="a3879-128">Use the strongly named type name to ensure that the right type is used.</span></span> <span data-ttu-id="a3879-129">Para obtener más información, consulte la sección "Para hacer referencia a un tipo con nombre seguro" a continuación.</span><span class="sxs-lookup"><span data-stu-id="a3879-129">For more information, see the "To reference a strongly named type" section below.</span></span>

     <span data-ttu-id="a3879-130">Algunos tipos válidos que puede usar son:</span><span class="sxs-lookup"><span data-stu-id="a3879-130">Some types that you can use are:</span></span>

    - <span data-ttu-id="a3879-131">Un agente de escucha <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType> , que escribe en un archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="a3879-131">A <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType> listener, which writes to a file log.</span></span>

    - <span data-ttu-id="a3879-132">Un agente de escucha <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType> , que escribe información en el registro de eventos del equipo especificado por el parámetro `initializeData` .</span><span class="sxs-lookup"><span data-stu-id="a3879-132">A <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType> listener, which writes information to the computer event log specified by the `initializeData` parameter.</span></span>

    - <span data-ttu-id="a3879-133">Los agentes de escucha <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType> y <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> , que escriben en el archivo especificado en el parámetro `initializeData` .</span><span class="sxs-lookup"><span data-stu-id="a3879-133">The <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType> and <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> listeners, which write to the file specified in the `initializeData` parameter.</span></span>

    - <span data-ttu-id="a3879-134">Un agente de escucha <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType> , que escribe en la consola de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="a3879-134">A <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType> listener, which writes to the command-line console.</span></span>

     <span data-ttu-id="a3879-135">Para obtener información sobre dónde escriben información otros tipos de agentes de escucha de registro, consulte la documentación de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="a3879-135">For information about where other types of log listeners write information, consult that type's documentation.</span></span>

3. <span data-ttu-id="a3879-136">Cuando la aplicación crea el objeto de agente de escucha de registro, pasa el atributo `initializeData` como el parámetro de constructor.</span><span class="sxs-lookup"><span data-stu-id="a3879-136">When the application creates the log-listener object, it passes the `initializeData` attribute as the constructor parameter.</span></span> <span data-ttu-id="a3879-137">El significado del atributo `initializeData` depende del agente de escucha de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a3879-137">The meaning of the `initializeData` attribute depends on the trace listener.</span></span>

4. <span data-ttu-id="a3879-138">Después de crear el agente de escucha de registro, la aplicación establece las propiedades del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="a3879-138">After creating the log listener, the application sets the listener's properties.</span></span> <span data-ttu-id="a3879-139">Estas propiedades se definen mediante los demás atributos del elemento `<add>` .</span><span class="sxs-lookup"><span data-stu-id="a3879-139">These properties are defined by the other attributes in the `<add>` element.</span></span> <span data-ttu-id="a3879-140">Para obtener más información sobre las propiedades de un agente de escucha determinado, consulte la documentación de este tipo de agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="a3879-140">For more information on the properties for a particular listener, see the documentation for that listener's type.</span></span>

### <a name="to-reference-a-strongly-named-type"></a><span data-ttu-id="a3879-141">Para hacer referencia a un tipo con nombre seguro</span><span class="sxs-lookup"><span data-stu-id="a3879-141">To reference a strongly named type</span></span>

1. <span data-ttu-id="a3879-142">Para asegurarse de que se usa el tipo correcto para el agente de escucha de registro, asegúrese de usar el nombre completo del tipo y el nombre de ensamblado con nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="a3879-142">To ensure that the right type is used for your log listener, make sure to use the fully qualified type name and the strongly named assembly name.</span></span> <span data-ttu-id="a3879-143">La sintaxis de un tipo con nombre seguro es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="a3879-143">The syntax of a strongly named type is as follows:</span></span>

     <span data-ttu-id="a3879-144">\<*nombre de tipo*>, \<*nombre de ensamblado*>, \<*número de versión*>, \<*referencia cultural*>, \<*nombre seguro*></span><span class="sxs-lookup"><span data-stu-id="a3879-144">\<*type name*>, \<*assembly name*>, \<*version number*>, \<*culture*>, \<*strong name*></span></span>

2. <span data-ttu-id="a3879-145">Este ejemplo de código muestra cómo determinar el nombre de tipo con nombre seguro para un tipo completo (en este caso, "System.Diagnostics.FileLogTraceListener").</span><span class="sxs-lookup"><span data-stu-id="a3879-145">This code example shows how to determine the strongly named type name for a fully qualified type—"System.Diagnostics.FileLogTraceListener" in this case.</span></span>

     [!code-vb[VbVbalrMyApplicationLog#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#15)]

     <span data-ttu-id="a3879-146">Esta es la salida, que se puede usar para hacer referencia de manera exclusiva a un tipo con nombre seguro, como en el procedimiento "Para agregar agentes de escucha" anterior.</span><span class="sxs-lookup"><span data-stu-id="a3879-146">This is the output, and it can be used to uniquely reference a strongly named type, as in the "To add listeners" procedure above.</span></span>

     `Microsoft.VisualBasic.Logging.FileLogTraceListener, Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a`

## <a name="see-also"></a><span data-ttu-id="a3879-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3879-147">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceListener>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType>
- <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>
- [<span data-ttu-id="a3879-148">Escribir información de eventos en un archivo de texto</span><span class="sxs-lookup"><span data-stu-id="a3879-148">How to: Write Event Information to a Text File</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md)
- [<span data-ttu-id="a3879-149">Cómo: Escribir el registro de eventos de una aplicación</span><span class="sxs-lookup"><span data-stu-id="a3879-149">How to: Write to an Application Event Log</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md)

---
description: 'Más información acerca de: Tutorial: Cambiar el lugar en el que My.Application.Log escribe la información (Visual Basic)'
title: Cambiar el lugar en el que My.Application.Log escribe la información
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application.Log object, walkthroughs
- event logs, changing output location
ms.assetid: ecc74f95-743c-450d-93f6-09a30db0fe4a
ms.openlocfilehash: aa4e1b8ce33e2afd8dd51c68340feb3e85eb8966
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731427"
---
# <a name="walkthrough-changing-where-myapplicationlog-writes-information-visual-basic"></a><span data-ttu-id="3e7c3-103">Tutorial: Cambiar el lugar en el que My.Application.Log escribe la información (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3e7c3-103">Walkthrough: Changing Where My.Application.Log Writes Information (Visual Basic)</span></span>

<span data-ttu-id="3e7c3-104">Puede usar los objetos `My.Application.Log` y `My.Log` para registrar información sobre los eventos que se producen en su aplicación.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-104">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span> <span data-ttu-id="3e7c3-105">Este tutorial muestra cómo reemplazar la configuración predeterminada y hacer que el objeto `Log` escriba en otros agentes de escucha de registro.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-105">This walkthrough shows how to override the default settings and cause the `Log` object to write to other log listeners.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3e7c3-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3e7c3-106">Prerequisites</span></span>

<span data-ttu-id="3e7c3-107">El objeto `Log` puede escribir información en varios agentes de escucha de registro.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-107">The `Log` object can write information to several log listeners.</span></span> <span data-ttu-id="3e7c3-108">Debe determinar la configuración actual de los agentes de escucha de registro antes de cambiar las configuraciones.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-108">You need to determine the current configuration of the log listeners before changing the configurations.</span></span> <span data-ttu-id="3e7c3-109">Para obtener más información, vea [Tutorial: Determinar el lugar en el que My.Application.Log escribe la información](walkthrough-determining-where-my-application-log-writes-information.md).</span><span class="sxs-lookup"><span data-stu-id="3e7c3-109">For more information, see [Walkthrough: Determining Where My.Application.Log Writes Information](walkthrough-determining-where-my-application-log-writes-information.md).</span></span>

<span data-ttu-id="3e7c3-110">Es posible que quiera consultar [Cómo: Escribir información de eventos en un archivo de texto](how-to-write-event-information-to-a-text-file.md) o [Cómo: Escribir el registro de eventos de una aplicación](how-to-write-to-an-application-event-log.md).</span><span class="sxs-lookup"><span data-stu-id="3e7c3-110">You may want to review [How to: Write Event Information to a Text File](how-to-write-event-information-to-a-text-file.md) or [How to: Write to an Application Event Log](how-to-write-to-an-application-event-log.md).</span></span>

### <a name="to-add-listeners"></a><span data-ttu-id="3e7c3-111">Para agregar agentes de escucha</span><span class="sxs-lookup"><span data-stu-id="3e7c3-111">To add listeners</span></span>

1. <span data-ttu-id="3e7c3-112">Haga clic con el botón derecho en app.config en el **Explorador de soluciones** y seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-112">Right-click app.config in **Solution Explorer** and choose **Open**.</span></span>

     <span data-ttu-id="3e7c3-113">\- o -</span><span class="sxs-lookup"><span data-stu-id="3e7c3-113">\- or -</span></span>

     <span data-ttu-id="3e7c3-114">Si no hay ningún archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="3e7c3-114">If there is no app.config file:</span></span>

    1. <span data-ttu-id="3e7c3-115">En el menú **Proyecto** , elija **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-115">On the **Project** menu, choose **Add New Item**.</span></span>

    2. <span data-ttu-id="3e7c3-116">En el cuadro de diálogo **Agregar nuevo elemento** , seleccione **Archivo de configuración de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-116">From the **Add New Item** dialog box, select **Application Configuration File**.</span></span>

    3. <span data-ttu-id="3e7c3-117">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-117">Click **Add**.</span></span>

2. <span data-ttu-id="3e7c3-118">Busque la sección `<listeners>` , bajo la sección `<source>` con el atributo `name` el "DefaultSource", en la sección `<sources>` .</span><span class="sxs-lookup"><span data-stu-id="3e7c3-118">Locate the `<listeners>` section, under the `<source>` section with the `name` attribute "DefaultSource", in the `<sources>` section.</span></span> <span data-ttu-id="3e7c3-119">La sección `<sources>` está en la sección `<system.diagnostics>` , en la sección de nivel superior `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="3e7c3-119">The `<sources>` section is in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

3. <span data-ttu-id="3e7c3-120">Agregue estos elementos a la sección `<listeners>` .</span><span class="sxs-lookup"><span data-stu-id="3e7c3-120">Add these elements to that `<listeners>` section.</span></span>

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

4. <span data-ttu-id="3e7c3-121">Quite la marca de comentario de los agentes de escucha de registro que desee que reciban mensajes de `Log` .</span><span class="sxs-lookup"><span data-stu-id="3e7c3-121">Uncomment the log listeners that you want to receive `Log` messages.</span></span>

5. <span data-ttu-id="3e7c3-122">Busque la sección `<sharedListeners>` , en la sección `<system.diagnostics>` , en la sección de nivel superior `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="3e7c3-122">Locate the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

6. <span data-ttu-id="3e7c3-123">Agregue estos elementos a la sección `<sharedListeners>` .</span><span class="sxs-lookup"><span data-stu-id="3e7c3-123">Add these elements to that `<sharedListeners>` section.</span></span>

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

7. <span data-ttu-id="3e7c3-124">El contenido del archivo app.config debe ser similar al código XML siguiente:</span><span class="sxs-lookup"><span data-stu-id="3e7c3-124">The content of the app.config file should be similar to the following XML:</span></span>

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

### <a name="to-reconfigure-a-listener"></a><span data-ttu-id="3e7c3-125">Para volver a configurar un agente de escucha</span><span class="sxs-lookup"><span data-stu-id="3e7c3-125">To reconfigure a listener</span></span>

1. <span data-ttu-id="3e7c3-126">Busque el elemento `<add>` del agente de escucha de la sección `<sharedListeners>` .</span><span class="sxs-lookup"><span data-stu-id="3e7c3-126">Locate the listener's `<add>` element from the `<sharedListeners>` section.</span></span>

2. <span data-ttu-id="3e7c3-127">El atributo `type` proporciona el nombre del tipo de agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-127">The `type` attribute gives the name of the listener type.</span></span> <span data-ttu-id="3e7c3-128">Este tipo debe heredar de la clase <xref:System.Diagnostics.TraceListener> .</span><span class="sxs-lookup"><span data-stu-id="3e7c3-128">This type must inherit from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="3e7c3-129">Use el nombre de tipo con nombre seguro para asegurarse de que se use el tipo correcto.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-129">Use the strongly named type name to ensure that the right type is used.</span></span> <span data-ttu-id="3e7c3-130">Para obtener más información, consulte la sección "Para hacer referencia a un tipo con nombre seguro" a continuación.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-130">For more information, see the "To reference a strongly named type" section below.</span></span>

     <span data-ttu-id="3e7c3-131">Algunos tipos válidos que puede usar son:</span><span class="sxs-lookup"><span data-stu-id="3e7c3-131">Some types that you can use are:</span></span>

    - <span data-ttu-id="3e7c3-132">Un agente de escucha <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType> , que escribe en un archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-132">A <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType> listener, which writes to a file log.</span></span>

    - <span data-ttu-id="3e7c3-133">Un agente de escucha <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType> , que escribe información en el registro de eventos del equipo especificado por el parámetro `initializeData` .</span><span class="sxs-lookup"><span data-stu-id="3e7c3-133">A <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType> listener, which writes information to the computer event log specified by the `initializeData` parameter.</span></span>

    - <span data-ttu-id="3e7c3-134">Los agentes de escucha <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType> y <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> , que escriben en el archivo especificado en el parámetro `initializeData` .</span><span class="sxs-lookup"><span data-stu-id="3e7c3-134">The <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType> and <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> listeners, which write to the file specified in the `initializeData` parameter.</span></span>

    - <span data-ttu-id="3e7c3-135">Un agente de escucha <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType> , que escribe en la consola de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-135">A <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType> listener, which writes to the command-line console.</span></span>

     <span data-ttu-id="3e7c3-136">Para obtener información sobre dónde escriben información otros tipos de agentes de escucha de registro, consulte la documentación de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-136">For information about where other types of log listeners write information, consult that type's documentation.</span></span>

3. <span data-ttu-id="3e7c3-137">Cuando la aplicación crea el objeto de agente de escucha de registro, pasa el atributo `initializeData` como el parámetro de constructor.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-137">When the application creates the log-listener object, it passes the `initializeData` attribute as the constructor parameter.</span></span> <span data-ttu-id="3e7c3-138">El significado del atributo `initializeData` depende del agente de escucha de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-138">The meaning of the `initializeData` attribute depends on the trace listener.</span></span>

4. <span data-ttu-id="3e7c3-139">Después de crear el agente de escucha de registro, la aplicación establece las propiedades del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-139">After creating the log listener, the application sets the listener's properties.</span></span> <span data-ttu-id="3e7c3-140">Estas propiedades se definen mediante los demás atributos del elemento `<add>` .</span><span class="sxs-lookup"><span data-stu-id="3e7c3-140">These properties are defined by the other attributes in the `<add>` element.</span></span> <span data-ttu-id="3e7c3-141">Para obtener más información sobre las propiedades de un agente de escucha determinado, consulte la documentación de este tipo de agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-141">For more information on the properties for a particular listener, see the documentation for that listener's type.</span></span>

### <a name="to-reference-a-strongly-named-type"></a><span data-ttu-id="3e7c3-142">Para hacer referencia a un tipo con nombre seguro</span><span class="sxs-lookup"><span data-stu-id="3e7c3-142">To reference a strongly named type</span></span>

1. <span data-ttu-id="3e7c3-143">Para asegurarse de que se usa el tipo correcto para el agente de escucha de registro, asegúrese de usar el nombre completo del tipo y el nombre de ensamblado con nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-143">To ensure that the right type is used for your log listener, make sure to use the fully qualified type name and the strongly named assembly name.</span></span> <span data-ttu-id="3e7c3-144">La sintaxis de un tipo con nombre seguro es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="3e7c3-144">The syntax of a strongly named type is as follows:</span></span>

     <span data-ttu-id="3e7c3-145">\<*type name*>, \<*assembly name*>, \<*version number*>, \<*culture*>, \<*strong name*></span><span class="sxs-lookup"><span data-stu-id="3e7c3-145">\<*type name*>, \<*assembly name*>, \<*version number*>, \<*culture*>, \<*strong name*></span></span>

2. <span data-ttu-id="3e7c3-146">Este ejemplo de código muestra cómo determinar el nombre de tipo con nombre seguro para un tipo completo (en este caso, "System.Diagnostics.FileLogTraceListener").</span><span class="sxs-lookup"><span data-stu-id="3e7c3-146">This code example shows how to determine the strongly named type name for a fully qualified type—"System.Diagnostics.FileLogTraceListener" in this case.</span></span>

     [!code-vb[VbVbalrMyApplicationLog#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#15)]

     <span data-ttu-id="3e7c3-147">Esta es la salida, que se puede usar para hacer referencia de manera exclusiva a un tipo con nombre seguro, como en el procedimiento "Para agregar agentes de escucha" anterior.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-147">This is the output, and it can be used to uniquely reference a strongly named type, as in the "To add listeners" procedure above.</span></span>

     `Microsoft.VisualBasic.Logging.FileLogTraceListener, Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a`

## <a name="see-also"></a><span data-ttu-id="3e7c3-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e7c3-148">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceListener>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType>
- <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>
- [<span data-ttu-id="3e7c3-149">Cómo: Escribir información de eventos en un archivo de texto</span><span class="sxs-lookup"><span data-stu-id="3e7c3-149">How to: Write Event Information to a Text File</span></span>](how-to-write-event-information-to-a-text-file.md)
- [<span data-ttu-id="3e7c3-150">Cómo: Escribir el registro de eventos de una aplicación</span><span class="sxs-lookup"><span data-stu-id="3e7c3-150">How to: Write to an Application Event Log</span></span>](how-to-write-to-an-application-event-log.md)

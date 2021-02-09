---
description: 'Más información acerca de: Trabajar con registros de aplicaciones en Visual Basic'
title: Trabajar con registros de aplicaciones
ms.date: 07/20/2015
helpviewer_keywords:
- logs, application
- application event logs, Visual Basic
- application event logs
ms.assetid: 2581afd1-5791-4bc4-86b2-46244e9fe468
ms.openlocfilehash: 0c05bd63cfbae668c58a87aa39651b6c3ef166ad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792276"
---
# <a name="working-with-application-logs-in-visual-basic"></a><span data-ttu-id="c986c-103">Trabajar con registros de aplicaciones en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c986c-103">Working with Application Logs in Visual Basic</span></span>

<span data-ttu-id="c986c-104">Los objetos `My.Application.Log` y `My.Log` facilitan la escritura de información de registro y seguimiento en los registros.</span><span class="sxs-lookup"><span data-stu-id="c986c-104">The `My.Application.Log` and `My.Log` objects make it easy to write logging and tracing information to logs.</span></span>

## <a name="how-messages-are-logged"></a><span data-ttu-id="c986c-105">Cómo se registran los mensajes</span><span class="sxs-lookup"><span data-stu-id="c986c-105">How Messages are Logged</span></span>

<span data-ttu-id="c986c-106">En primer lugar, se comprueba la gravedad del mensaje con la propiedad <xref:System.Diagnostics.TraceSource.Switch%2A> de la propiedad <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A> del registro.</span><span class="sxs-lookup"><span data-stu-id="c986c-106">First, the severity of the message is checked with the <xref:System.Diagnostics.TraceSource.Switch%2A> property of the log's <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A> property.</span></span> <span data-ttu-id="c986c-107">De forma predeterminada, solo los mensajes de gravedad "Información" y superior se pasan a los agentes de escucha de seguimiento especificados en la colección `TraceListener` del registro.</span><span class="sxs-lookup"><span data-stu-id="c986c-107">By default, only messages of severity "Information" and higher are passed on to the trace listeners, specified in the log's `TraceListener` collection.</span></span> <span data-ttu-id="c986c-108">A continuación, cada agente de escucha compara la gravedad del mensaje con la propiedad <xref:System.Diagnostics.TraceSource.Switch%2A> del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="c986c-108">Then, each listener compares the severity of the message to the listener's <xref:System.Diagnostics.TraceSource.Switch%2A> property.</span></span> <span data-ttu-id="c986c-109">Si la gravedad del mensaje es bastante alta, el agente de escucha escribe el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c986c-109">If the message's severity is high enough, the listener writes out the message.</span></span>

<span data-ttu-id="c986c-110">En el siguiente diagrama se muestra cómo un mensaje escrito en el método `WriteEntry` se pasa a los métodos `WriteLine` de lo agentes de escucha de seguimiento del registro:</span><span class="sxs-lookup"><span data-stu-id="c986c-110">The following diagram shows how a message written to the `WriteEntry` method gets passed to the `WriteLine` methods of the log's trace listeners:</span></span>

![Diagrama que muestra la llamada My log.](./media/working-with-application-logs/my-log-call-messages.png)

<span data-ttu-id="c986c-112">Puede cambiar el archivo de configuración de la aplicación para modificar el comportamiento de los agentes de escucha de registro y de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c986c-112">You can change the behavior of the log and the trace listeners by changing the application's configuration file.</span></span> <span data-ttu-id="c986c-113">En el diagrama siguiente se muestra la correspondencia entre las partes del registro y el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="c986c-113">The following diagram shows the correspondence between the parts of the log and the configuration file.</span></span>

![Diagrama que muestra la configuración de My log.](./media/working-with-application-logs/my-log-configuration.png)

## <a name="where-messages-are-logged"></a><span data-ttu-id="c986c-115">Dónde se registran los mensajes</span><span class="sxs-lookup"><span data-stu-id="c986c-115">Where Messages are Logged</span></span>

<span data-ttu-id="c986c-116">Si el ensamblado no tiene ningún archivo de configuración, los objetos `My.Application.Log` y `My.Log` escriben en la salida de depuración de la aplicación (a través de la clase <xref:System.Diagnostics.DefaultTraceListener> ).</span><span class="sxs-lookup"><span data-stu-id="c986c-116">If the assembly has no configuration file, the `My.Application.Log` and `My.Log` objects write to the application's debug output (through the <xref:System.Diagnostics.DefaultTraceListener> class).</span></span> <span data-ttu-id="c986c-117">Además, el objeto `My.Application.Log` escribe en el archivo de registro del ensamblado (a través de la clase <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> ), mientras que el objeto `My.Log` escribe en la salida de la página web ASP.NET (a través de la clase <xref:System.Web.WebPageTraceListener> ).</span><span class="sxs-lookup"><span data-stu-id="c986c-117">In addition, the `My.Application.Log` object writes to the assembly's log file (through the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class), while the `My.Log` object writes to the ASP.NET Web page's output (through the <xref:System.Web.WebPageTraceListener> class).</span></span>

<span data-ttu-id="c986c-118">La salida de depuración se puede ver en la ventana **Salida** de Visual Studio al ejecutar la aplicación en modo de depuración.</span><span class="sxs-lookup"><span data-stu-id="c986c-118">The debug output can be viewed in the Visual Studio **Output** window when running your application in debug mode.</span></span> <span data-ttu-id="c986c-119">Para abrir la ventana **Salida** , haga clic en el elemento de menú **Depurar** , seleccione **Windows**, y, después, haga clic en **Salida**.</span><span class="sxs-lookup"><span data-stu-id="c986c-119">To open the **Output** window, click the **Debug** menu item, point to **Windows**, and then click **Output**.</span></span> <span data-ttu-id="c986c-120">En la ventana **Salida** , seleccione **Depurar** desde el cuadro **Mostrar resultados desde** .</span><span class="sxs-lookup"><span data-stu-id="c986c-120">In the **Output** window, select **Debug** from the **Show output from** box.</span></span>

<span data-ttu-id="c986c-121">De forma predeterminada, `My.Application.Log` escribe el archivo de registro en la ruta de acceso de los datos de aplicaciones del usuario.</span><span class="sxs-lookup"><span data-stu-id="c986c-121">By default, `My.Application.Log` writes the log file in the path for the user's application data.</span></span> <span data-ttu-id="c986c-122">Puede obtener la ruta de acceso de la propiedad <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.FullLogFileName%2A> del objeto <xref:Microsoft.VisualBasic.Logging.Log.DefaultFileLogWriter%2A> .</span><span class="sxs-lookup"><span data-stu-id="c986c-122">You can get the path from the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.FullLogFileName%2A> property of the <xref:Microsoft.VisualBasic.Logging.Log.DefaultFileLogWriter%2A> object.</span></span> <span data-ttu-id="c986c-123">El formato de la ruta de acceso es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="c986c-123">The format of that path is as follows:</span></span>

`BasePath`\\`CompanyName`\\`ProductName`\\`ProductVersion`

<span data-ttu-id="c986c-124">A continuación se indica un valor típico de `BasePath` .</span><span class="sxs-lookup"><span data-stu-id="c986c-124">A typical value for `BasePath` is as follows.</span></span>

<span data-ttu-id="c986c-125">C:\Documents and Settings\\`username`\Application Data</span><span class="sxs-lookup"><span data-stu-id="c986c-125">C:\Documents and Settings\\`username`\Application Data</span></span>

<span data-ttu-id="c986c-126">Los valores de `CompanyName`, `ProductName`y `ProductVersion` proceden de la información de ensamblado de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c986c-126">The values of `CompanyName`, `ProductName`, and `ProductVersion` come from the application's assembly information.</span></span> <span data-ttu-id="c986c-127">El formato del nombre de archivo de registro es *nombreDeEnsamblado*.log, donde *nombreDeEnsamblado* es el nombre de archivo del ensamblado sin la extensión.</span><span class="sxs-lookup"><span data-stu-id="c986c-127">The form of the log file name is *AssemblyName*.log, where *AssemblyName* is the file name of the assembly without the extension.</span></span> <span data-ttu-id="c986c-128">Si se necesita más de un archivo de registro, por ejemplo, si el registro original no está disponible cuando la aplicación intenta escribir en el registro, el formato del nombre de archivo de registro es *nombreDeEnsamblado*-*iteration*.log, donde `iteration` es un `Integer`.</span><span class="sxs-lookup"><span data-stu-id="c986c-128">If more than one log file is needed, such as when the original log is unavailable when the application attempts to write to the log, the form for the log file name is *AssemblyName*-*iteration*.log, where `iteration` is a positive `Integer`.</span></span>

<span data-ttu-id="c986c-129">Para invalidar el comportamiento predeterminado, puede agregar o cambiar los archivos de configuración del equipo y de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c986c-129">You can override the default behavior by adding or changing the computer's and the application's configuration files.</span></span> <span data-ttu-id="c986c-130">Para obtener más información, consulta [Tutorial: Cambiar el lugar donde My.Application.Log escribe información](walkthrough-changing-where-my-application-log-writes-information.md).</span><span class="sxs-lookup"><span data-stu-id="c986c-130">For more information, see [Walkthrough: Changing Where My.Application.Log Writes Information](walkthrough-changing-where-my-application-log-writes-information.md).</span></span>

## <a name="configuring-log-settings"></a><span data-ttu-id="c986c-131">Configurar el registro</span><span class="sxs-lookup"><span data-stu-id="c986c-131">Configuring Log Settings</span></span>

<span data-ttu-id="c986c-132">El objeto `Log` tiene una implementación predeterminada que funciona sin un archivo de configuración de la aplicación, app.config. Para cambiar los valores predeterminados, debe agregar un archivo de configuración con la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="c986c-132">The `Log` object has a default implementation that works without an application configuration file, app.config. To change the defaults, you must add a configuration file with the new settings.</span></span> <span data-ttu-id="c986c-133">Para obtener más información, consulta [Walkthrough: Filtering My.Application.Log Output](walkthrough-filtering-my-application-log-output.md).</span><span class="sxs-lookup"><span data-stu-id="c986c-133">For more information, see [Walkthrough: Filtering My.Application.Log Output](walkthrough-filtering-my-application-log-output.md).</span></span>

<span data-ttu-id="c986c-134">Las secciones de configuración de registro se encuentran en el nodo `<system.diagnostics>` del nodo principal `<configuration>` del archivo app.config.</span><span class="sxs-lookup"><span data-stu-id="c986c-134">The log configuration sections are located in the `<system.diagnostics>` node in the main `<configuration>` node of the app.config file.</span></span> <span data-ttu-id="c986c-135">La información de registro se define en varios nodos:</span><span class="sxs-lookup"><span data-stu-id="c986c-135">Log information is defined in several nodes:</span></span>

- <span data-ttu-id="c986c-136">Los agentes de escucha del objeto `Log` se definen en el nodo `<sources>` denominado DefaultSource.</span><span class="sxs-lookup"><span data-stu-id="c986c-136">The listeners for the `Log` object are defined in the `<sources>` node named DefaultSource.</span></span>

- <span data-ttu-id="c986c-137">El filtro de gravedad del objeto `Log` se definen en el nodo `<switches>` denominado DefaultSwitch.</span><span class="sxs-lookup"><span data-stu-id="c986c-137">The severity filter for the `Log` object is defined in the `<switches>` node named DefaultSwitch.</span></span>

- <span data-ttu-id="c986c-138">Los agentes de escucha de registro se definen en el nodo `<sharedListeners>` .</span><span class="sxs-lookup"><span data-stu-id="c986c-138">The log listeners are defined in the `<sharedListeners>` node.</span></span>

 <span data-ttu-id="c986c-139">En el código siguiente, se muestran ejemplos de los nodos `<sources>`, `<switches>`y `<sharedListeners>` :</span><span class="sxs-lookup"><span data-stu-id="c986c-139">Examples of `<sources>`, `<switches>`, and `<sharedListeners>` nodes are shown in the following code:</span></span>

```xml
<configuration>
  <system.diagnostics>
    <sources>
      <source name="DefaultSource" switchName="DefaultSwitch">
        <listeners>
          <add name="FileLog"/>
        </listeners>
      </source>
    </sources>
    <switches>
      <add name="DefaultSwitch" value="Information" />
    </switches>
    <sharedListeners>
      <add name="FileLog"
        type="Microsoft.VisualBasic.Logging.FileLogTraceListener,
          Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral,
          PublicKeyToken=b03f5f7f11d50a3a, processorArchitecture=MSIL"
        initializeData="FileLogWriter"
      />
    </sharedListeners>
  </system.diagnostics>
</configuration>
```

## <a name="changing-log-settings-after-deployment"></a><span data-ttu-id="c986c-140">Cambiar la configuración de registro después de la implementación</span><span class="sxs-lookup"><span data-stu-id="c986c-140">Changing Log Settings after Deployment</span></span>

<span data-ttu-id="c986c-141">Al desarrollar una aplicación, su configuración se almacena en el archivo app.config, tal como se muestra en los ejemplos anteriores.</span><span class="sxs-lookup"><span data-stu-id="c986c-141">When you develop an application, its configuration settings are stored in the app.config file, as shown in the examples above.</span></span> <span data-ttu-id="c986c-142">Después de implementar su aplicación, puede configurar el registro mediante la edición del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="c986c-142">After you deploy your application, you can still configure the log by editing the configuration file.</span></span> <span data-ttu-id="c986c-143">En una aplicación basada en Windows, el nombre de este archivo es *nombreDeAplicación*.exe.config y debe encontrarse en la misma carpeta que el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="c986c-143">In a Windows-based application, this file's name is *applicationName*.exe.config, and it must reside in the same folder as the executable file.</span></span> <span data-ttu-id="c986c-144">En una aplicación web, es el archivo Web.config asociado al proyecto.</span><span class="sxs-lookup"><span data-stu-id="c986c-144">For a Web application, this is the Web.config file associated with the project.</span></span>

<span data-ttu-id="c986c-145">Cuando la aplicación ejecuta el código que crea una instancia de una clase por primera vez, comprueba el archivo de configuración para obtener información sobre el objeto.</span><span class="sxs-lookup"><span data-stu-id="c986c-145">When your application executes the code that creates an instance of a class for the first time, it checks the configuration file for information about the object.</span></span> <span data-ttu-id="c986c-146">En el caso del objeto `Log` , estos sucede la primera vez que se accede al objeto `Log` .</span><span class="sxs-lookup"><span data-stu-id="c986c-146">For the `Log` object, this happens the first time the `Log` object is accessed.</span></span> <span data-ttu-id="c986c-147">El sistema examina el archivo de configuración una sola vez par cada objeto concreto (la primera vez que la aplicación crea el objeto).</span><span class="sxs-lookup"><span data-stu-id="c986c-147">The system examines the configuration file only once for any particular object—the first time your application creates the object.</span></span> <span data-ttu-id="c986c-148">Por lo tanto, es posible que deba reiniciar la aplicación para que los cambios surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="c986c-148">Therefore, you may need to restart the application for the changes to take effect.</span></span>

<span data-ttu-id="c986c-149">En una aplicación implementada, el código de seguimiento se habilita volviendo a configurar los objetos modificadores antes de que se inicie la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c986c-149">In a deployed application, you enable trace code by reconfiguring switch objects before your application starts.</span></span> <span data-ttu-id="c986c-150">Normalmente, esto implica activar y desactivar los objetos modificadores. Para ello, se deben cambiar los niveles de seguimiento y, luego, reiniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c986c-150">Typically, this involves turning the switch objects on and off or by changing the tracing levels, and then restarting your application.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="c986c-151">Consideraciones sobre la seguridad</span><span class="sxs-lookup"><span data-stu-id="c986c-151">Security Considerations</span></span>

<span data-ttu-id="c986c-152">Tenga en cuenta lo siguiente al escribir datos en el registro:</span><span class="sxs-lookup"><span data-stu-id="c986c-152">Consider the following when writing data to the log:</span></span>

- <span data-ttu-id="c986c-153">**Evite la pérdida de información de usuario.**</span><span class="sxs-lookup"><span data-stu-id="c986c-153">**Avoid leaking user information.**</span></span> <span data-ttu-id="c986c-154">Asegúrese de que la aplicación solo escribe información aprobada en el registro.</span><span class="sxs-lookup"><span data-stu-id="c986c-154">Ensure that your application writes only approved information to the log.</span></span> <span data-ttu-id="c986c-155">Por ejemplo, es posible que se acepte que el registro de la aplicación contenga nombres de usuario, pero no contraseñas de usuario.</span><span class="sxs-lookup"><span data-stu-id="c986c-155">For example, it may be acceptable for the application log to contain user names, but not user passwords.</span></span>

- <span data-ttu-id="c986c-156">**Proteja las ubicaciones del registro.**</span><span class="sxs-lookup"><span data-stu-id="c986c-156">**Make log locations secure.**</span></span> <span data-ttu-id="c986c-157">Cualquier registro que contenga información que pueda ser confidencial debe almacenarse en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="c986c-157">Any log that contains potentially sensitive information should be stored in a secure location.</span></span>

- <span data-ttu-id="c986c-158">**Evite información engañosa.**</span><span class="sxs-lookup"><span data-stu-id="c986c-158">**Avoid misleading information.**</span></span> <span data-ttu-id="c986c-159">En general, la aplicación debe validar todos los datos introducidos por un usuario antes de usarlos.</span><span class="sxs-lookup"><span data-stu-id="c986c-159">In general, your application should validate all data entered by a user before using that data.</span></span> <span data-ttu-id="c986c-160">Se incluye la escritura de datos en el registro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c986c-160">This includes writing data to the application log.</span></span>

- <span data-ttu-id="c986c-161">**Evite la denegación de servicio.**</span><span class="sxs-lookup"><span data-stu-id="c986c-161">**Avoid denial of service.**</span></span> <span data-ttu-id="c986c-162">Si su aplicación escribe demasiada información en el registro, podría llenar el registro o dificultar la búsqueda de información importante.</span><span class="sxs-lookup"><span data-stu-id="c986c-162">If your application writes too much information to the log, it could fill the log or make finding important information difficult.</span></span>

## <a name="see-also"></a><span data-ttu-id="c986c-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="c986c-163">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [<span data-ttu-id="c986c-164">Registrar información de la aplicación</span><span class="sxs-lookup"><span data-stu-id="c986c-164">Logging Information from the Application</span></span>](index.md)

---
title: Procedimiento para depurar aplicaciones de servicios de Windows
ms.date: 03/30/2017
helpviewer_keywords:
- debugging Windows Service applications
- debugging [Visual Studio], Windows services
- Windows NT services, debugging
- Windows Service applications, debugging
- services, debugging
ms.assetid: 63ab0800-0f05-4f1e-88e6-94c73fd920a2
author: ghogen
ms.openlocfilehash: 860f2ae22eb6510dc1f1a454ae3e51ccb366078b
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053618"
---
# <a name="how-to-debug-windows-service-applications"></a><span data-ttu-id="6d810-102">Procedimiento para depurar aplicaciones de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="6d810-102">How to: Debug Windows Service Applications</span></span>
<span data-ttu-id="6d810-103">Un servicio se debe ejecutar desde el contexto del Administrador de control de servicios en lugar de desde Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6d810-103">A service must be run from within the context of the Services Control Manager rather than from within Visual Studio.</span></span> <span data-ttu-id="6d810-104">Por este motivo, la depuración de un servicio no es tan simple como depurar otros tipos de aplicaciones de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6d810-104">For this reason, debugging a service is not as straightforward as debugging other Visual Studio application types.</span></span> <span data-ttu-id="6d810-105">Para depurar un servicio, debe iniciar el servicio y, a continuación, asociar un depurador al proceso en el que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="6d810-105">To debug a service, you must start the service and then attach a debugger to the process in which it is running.</span></span> <span data-ttu-id="6d810-106">Entonces puede depurar la aplicación mediante el uso de todas las funciones de depuración estándar de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6d810-106">You can then debug your application by using all of the standard debugging functionality of Visual Studio.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="6d810-107">No debe asociarse a un proceso a menos que sepa en qué consiste el proceso y comprenda las consecuencias de la asociación al proceso y de su probable finalización.</span><span class="sxs-lookup"><span data-stu-id="6d810-107">You should not attach to a process unless you know what the process is and understand the consequences of attaching to and possibly killing that process.</span></span> <span data-ttu-id="6d810-108">Por ejemplo, si se asocia al proceso WinLogon y luego detiene la depuración, el sistema se detendrá, porque no puede funcionar sin WinLogon.</span><span class="sxs-lookup"><span data-stu-id="6d810-108">For example, if you attach to the WinLogon process and then stop debugging, the system will halt because it can’t operate without WinLogon.</span></span>  
  
 <span data-ttu-id="6d810-109">Puede asociar el depurador a un servicio en ejecución.</span><span class="sxs-lookup"><span data-stu-id="6d810-109">You can attach the debugger only to a running service.</span></span> <span data-ttu-id="6d810-110">El proceso de asociación interrumpe el funcionamiento actual del servicio; no detiene ni pausa el procesamiento del servicio.</span><span class="sxs-lookup"><span data-stu-id="6d810-110">The attachment process interrupts the current functioning of your service; it doesn’t actually stop or pause the service's processing.</span></span> <span data-ttu-id="6d810-111">Es decir, si el servicio se está ejecutando al iniciar la depuración, todavía está técnicamente en el estado Iniciado al depurarlo, pero su procesamiento se ha suspendido.</span><span class="sxs-lookup"><span data-stu-id="6d810-111">That is, if your service is running when you begin debugging, it is still technically in the Started state as you debug it, but its processing has been suspended.</span></span>  
  
 <span data-ttu-id="6d810-112">Después de asociarse al proceso, puede establecer puntos de interrupción y usarlos para depurar el código.</span><span class="sxs-lookup"><span data-stu-id="6d810-112">After attaching to the process, you can set breakpoints and use these to debug your code.</span></span> <span data-ttu-id="6d810-113">Una vez que se sale del cuadro de diálogo usado para asociarse al proceso, se encuentra en modo de depuración.</span><span class="sxs-lookup"><span data-stu-id="6d810-113">Once you exit the dialog box you use to attach to the process, you are effectively in debug mode.</span></span> <span data-ttu-id="6d810-114">Puede usar el Administrador de control de servicios para iniciar, detener, pausar y continuar el servicio, pasando por los puntos de interrupción que ha establecido.</span><span class="sxs-lookup"><span data-stu-id="6d810-114">You can use the Services Control Manager to start, stop, pause and continue your service, thus hitting the breakpoints you've set.</span></span> <span data-ttu-id="6d810-115">Más adelante puede quitar este servicio ficticio después de realizar correctamente la depuración.</span><span class="sxs-lookup"><span data-stu-id="6d810-115">You can later remove this dummy service after debugging is successful.</span></span>  
  
 <span data-ttu-id="6d810-116">En este artículo se describe la depuración de un servicio que se ejecuta en el equipo local, pero también se pueden depurar servicios de Windows que se ejecuten en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="6d810-116">This article covers debugging a service that's running on the local computer, but you can also debug Windows Services that are running on a remote computer.</span></span> <span data-ttu-id="6d810-117">Consulte [Depuración remota](/visualstudio/debugger/debug-installed-app-package).</span><span class="sxs-lookup"><span data-stu-id="6d810-117">See [Remote Debugging](/visualstudio/debugger/debug-installed-app-package).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6d810-118">Depurar el método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> puede ser difícil porque el Administrador de control de servicios impone un límite de 30 segundos en todos los intentos de iniciar un servicio.</span><span class="sxs-lookup"><span data-stu-id="6d810-118">Debugging the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method can be difficult because the Services Control Manager imposes a 30-second limit on all attempts to start a service.</span></span> <span data-ttu-id="6d810-119">Para más información, vea [Solución de problemas: depuración de servicios de Windows](troubleshooting-debugging-windows-services.md).</span><span class="sxs-lookup"><span data-stu-id="6d810-119">For more information, see [Troubleshooting: Debugging Windows Services](troubleshooting-debugging-windows-services.md).</span></span>  
  
> [!WARNING]
> <span data-ttu-id="6d810-120">Para obtener información significativa para la depuración, el depurador de Visual Studio debe buscar archivos de símbolos para los archivos binarios que se están depurando.</span><span class="sxs-lookup"><span data-stu-id="6d810-120">To get meaningful information for debugging, the Visual Studio debugger needs to find symbol files for the binaries that are being debugged.</span></span> <span data-ttu-id="6d810-121">Si depura un servicio que compiló en Visual Studio, los archivos de símbolos (archivos .pdb) están en la misma carpeta que el archivo ejecutable o la biblioteca, y el depurador los carga automáticamente.</span><span class="sxs-lookup"><span data-stu-id="6d810-121">If you are debugging a service that you built in Visual Studio, the symbol files (.pdb files) are in the same folder as the executable or library, and the debugger loads them automatically.</span></span> <span data-ttu-id="6d810-122">Si depura un servicio que no compiló, primero debe encontrar los símbolos del servicio y asegurarse de que el depurador los pueda encontrar.</span><span class="sxs-lookup"><span data-stu-id="6d810-122">If you are debugging a service that you didn't build, you should first find symbols for the service and make sure they can be found by the debugger.</span></span> <span data-ttu-id="6d810-123">Consulte [Especificar archivos de código fuente y símbolos (.pdb) en el depurador de Visual Studio](/visualstudio/debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger).</span><span class="sxs-lookup"><span data-stu-id="6d810-123">See [Specify Symbol (.pdb) and Source Files in the Visual Studio Debugger](/visualstudio/debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger).</span></span> <span data-ttu-id="6d810-124">Si depura un proceso del sistema o desea tener símbolos para las llamadas del sistema en los servicios, debe agregar los servidores de símbolos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6d810-124">If you're debugging a system process or want to have symbols for system calls in your services, you should add the Microsoft Symbol Servers.</span></span> <span data-ttu-id="6d810-125">Consulte [Símbolos de depuración](/windows/desktop/DxTechArts/debugging-with-symbols).</span><span class="sxs-lookup"><span data-stu-id="6d810-125">See [Debugging Symbols](/windows/desktop/DxTechArts/debugging-with-symbols).</span></span>  
  
### <a name="to-debug-a-service"></a><span data-ttu-id="6d810-126">Para depurar un servicio</span><span class="sxs-lookup"><span data-stu-id="6d810-126">To debug a service</span></span>  
  
1. <span data-ttu-id="6d810-127">Compile el servicio en la configuración de depuración.</span><span class="sxs-lookup"><span data-stu-id="6d810-127">Build your service in the Debug configuration.</span></span>  
  
2. <span data-ttu-id="6d810-128">Instale el servicio.</span><span class="sxs-lookup"><span data-stu-id="6d810-128">Install your service.</span></span> <span data-ttu-id="6d810-129">Para obtener más información, vea [Cómo: Instalar y desinstalar servicios](how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="6d810-129">For more information, see [How to: Install and Uninstall Services](how-to-install-and-uninstall-services.md).</span></span>  
  
3. <span data-ttu-id="6d810-130">Inicie el servicio, desde el **Administrador de control de servicios**, desde el **Explorador de servidores** o desde el código.</span><span class="sxs-lookup"><span data-stu-id="6d810-130">Start your service, either from **Services Control Manager**, **Server Explorer**, or from code.</span></span> <span data-ttu-id="6d810-131">Para obtener más información, vea [Cómo: Iniciar servicios](how-to-start-services.md).</span><span class="sxs-lookup"><span data-stu-id="6d810-131">For more information, see [How to: Start Services](how-to-start-services.md).</span></span>  
  
4. <span data-ttu-id="6d810-132">Inicie Visual Studio con credenciales administrativas, para poder asociarse a los procesos del sistema.</span><span class="sxs-lookup"><span data-stu-id="6d810-132">Start Visual Studio with administrative credentials so you can attach to system processes.</span></span>  
  
5. <span data-ttu-id="6d810-133">(Opcional) En la barra de menús de Visual Studio, elija **Herramientas**, **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="6d810-133">(Optional) On the Visual Studio menu bar, choose **Tools**, **Options**.</span></span> <span data-ttu-id="6d810-134">En el cuadro de diálogo **Opciones**, elija **Depuración**, **Símbolos**, active la casilla **Servidores de símbolos de Microsoft** y, a continuación, elija el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6d810-134">In the **Options** dialog box, choose **Debugging**, **Symbols**, select the **Microsoft Symbol Servers** check box, and then choose the **OK** button.</span></span>  
  
6. <span data-ttu-id="6d810-135">En la barra de menús, elija **Asociar al proceso** en el menú **Depurar** o **Herramientas**.</span><span class="sxs-lookup"><span data-stu-id="6d810-135">On the menu bar, choose **Attach to Process** from the **Debug** or **Tools** menu.</span></span> <span data-ttu-id="6d810-136">(Teclado: Ctrl+Alt+P)</span><span class="sxs-lookup"><span data-stu-id="6d810-136">(Keyboard: Ctrl+Alt+P)</span></span>  
  
     <span data-ttu-id="6d810-137">Aparecerá el cuadro de diálogo **Procesos**.</span><span class="sxs-lookup"><span data-stu-id="6d810-137">The **Processes** dialog box appears.</span></span>  
  
7. <span data-ttu-id="6d810-138">Active la casilla **Mostrar los procesos de todos los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="6d810-138">Select the **Show processes from all users** check box.</span></span>  
  
8. <span data-ttu-id="6d810-139">En la sección **Procesos disponibles**, elija el proceso del servicio y, a continuación, seleccione **Asociar**.</span><span class="sxs-lookup"><span data-stu-id="6d810-139">In the **Available Processes** section, choose the process for your service, and then choose **Attach**.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="6d810-140">El proceso tendrá el mismo nombre que el archivo ejecutable para el servicio.</span><span class="sxs-lookup"><span data-stu-id="6d810-140">The process will have the same name as the executable file for your service.</span></span>  
  
     <span data-ttu-id="6d810-141">Aparecerá el cuadro de diálogo **Asociar al proceso** .</span><span class="sxs-lookup"><span data-stu-id="6d810-141">The **Attach to Process** dialog box appears.</span></span>  
  
9. <span data-ttu-id="6d810-142">Elija las opciones apropiadas y, a continuación, elija **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6d810-142">Choose the appropriate options, and then choose **OK** to close the dialog box.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="6d810-143">Ahora está en modo de depuración.</span><span class="sxs-lookup"><span data-stu-id="6d810-143">You are now in debug mode.</span></span>  
  
10. <span data-ttu-id="6d810-144">Establezca los puntos de interrupción que desee usar en el código.</span><span class="sxs-lookup"><span data-stu-id="6d810-144">Set any breakpoints you want to use in your code.</span></span>  
  
11. <span data-ttu-id="6d810-145">Obtenga acceso al Administrador de control de servicios y manipule el servicio; envíe comandos de detención, pausa y continuación para alcanzar los puntos de interrupción.</span><span class="sxs-lookup"><span data-stu-id="6d810-145">Access the Services Control Manager and manipulate your service, sending stop, pause, and continue commands to hit your breakpoints.</span></span> <span data-ttu-id="6d810-146">Para más información sobre la ejecución del Administrador de control de servicios, vea [Cómo: Iniciar servicios](how-to-start-services.md).</span><span class="sxs-lookup"><span data-stu-id="6d810-146">For more information about running the Services Control Manager, see [How to: Start Services](how-to-start-services.md).</span></span> <span data-ttu-id="6d810-147">Además, vea [Solución de problemas: depuración de servicios de Windows](troubleshooting-debugging-windows-services.md).</span><span class="sxs-lookup"><span data-stu-id="6d810-147">Also, see [Troubleshooting: Debugging Windows Services](troubleshooting-debugging-windows-services.md).</span></span>  
  
## <a name="debugging-tips-for-windows-services"></a><span data-ttu-id="6d810-148">Sugerencias de depuración para los servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="6d810-148">Debugging Tips for Windows Services</span></span>  
 <span data-ttu-id="6d810-149">Asociarse al proceso del servicio permite depurar gran parte del código de ese servicio, pero no todo.</span><span class="sxs-lookup"><span data-stu-id="6d810-149">Attaching to the service's process allows you to debug most, but not all, the code for that service.</span></span> <span data-ttu-id="6d810-150">Por ejemplo, si ya se ha iniciado el servicio, no se puede depurar el código del método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> del servicio o el código del método `Main` que se usa para cargar el servicio de esta manera.</span><span class="sxs-lookup"><span data-stu-id="6d810-150">For example, because the service has already been started, you cannot debug the code in the service's <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method or the code in the `Main` method that is used to load the service this way.</span></span> <span data-ttu-id="6d810-151">Una forma de evitar esta limitación es crear un segundo servicio temporal en la aplicación de servicio que solo exista para ayudar en la depuración.</span><span class="sxs-lookup"><span data-stu-id="6d810-151">One way to work around this limitation is to create a temporary second service in your service application that exists only to aid in debugging.</span></span> <span data-ttu-id="6d810-152">Puede instalar ambos servicios y, a continuación, iniciar este servicio ficticio para cargar el proceso del servicio.</span><span class="sxs-lookup"><span data-stu-id="6d810-152">You can install both services, and then start this dummy service to load the service process.</span></span> <span data-ttu-id="6d810-153">Una vez que el servicio temporal haya iniciado el proceso, puede usar el menú **Depuración** de Visual Studio para asociarse al proceso del servicio.</span><span class="sxs-lookup"><span data-stu-id="6d810-153">Once the temporary service has started the process, you can use the **Debug** menu in Visual Studio to attach to the service process.</span></span>  
  
 <span data-ttu-id="6d810-154">Intente agregar llamadas al método <xref:System.Threading.Thread.Sleep%2A> para retrasar la acción hasta que se pueda asociar al proceso.</span><span class="sxs-lookup"><span data-stu-id="6d810-154">Try adding calls to the <xref:System.Threading.Thread.Sleep%2A> method to delay action until you’re able to attach to the process.</span></span>  
  
 <span data-ttu-id="6d810-155">Intente cambiar el programa a una aplicación de consola normal.</span><span class="sxs-lookup"><span data-stu-id="6d810-155">Try changing the program to a regular console application.</span></span> <span data-ttu-id="6d810-156">Para ello, vuelva a escribir el método `Main` como se indica a continuación, de manera que se pueda ejecutar como un servicio de Windows y como una aplicación de consola, en función de cómo se inicie.</span><span class="sxs-lookup"><span data-stu-id="6d810-156">To do this, rewrite the `Main` method as follows so it can run both as a Windows Service and as a console application, depending on how it's started.</span></span>  
  
#### <a name="how-to-run-a-windows-service-as-a-console-application"></a><span data-ttu-id="6d810-157">Procedimiento para ejecutar un servicio de Windows como una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="6d810-157">How to: Run a Windows Service as a console application</span></span>  
  
1. <span data-ttu-id="6d810-158">Agregue un método al servicio que ejecute los métodos <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y <xref:System.ServiceProcess.ServiceBase.OnStop%2A>:</span><span class="sxs-lookup"><span data-stu-id="6d810-158">Add a method to your service that runs the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> methods:</span></span>  
  
    ```csharp  
    internal void TestStartupAndStop(string[] args)  
    {  
        this.OnStart(args);  
        Console.ReadLine();  
        this.OnStop();  
    }  
    ```  
  
2. <span data-ttu-id="6d810-159">Vuelva a escribir el método `Main` como sigue:</span><span class="sxs-lookup"><span data-stu-id="6d810-159">Rewrite the `Main` method as follows:</span></span>  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        if (Environment.UserInteractive)  
        {  
            MyNewService service1 = new MyNewService(args);  
            service1.TestStartupAndStop(args);  
        }  
        else  
        {  
            // Put the body of your old Main method here.  
        }  
    }
    ```  
  
3. <span data-ttu-id="6d810-160">En la pestaña **Aplicación** de las propiedades del proyecto, establezca el **Tipo de salida** en **Aplicación de consola**.</span><span class="sxs-lookup"><span data-stu-id="6d810-160">In the **Application** tab of the project's properties, set the **Output type** to **Console Application**.</span></span>  
  
4. <span data-ttu-id="6d810-161">Elija **Iniciar depuración** (F5).</span><span class="sxs-lookup"><span data-stu-id="6d810-161">Choose **Start Debugging** (F5).</span></span>  
  
5. <span data-ttu-id="6d810-162">Para volver a ejecutar el programa como un servicio de Windows, instálelo e inícielo de la manera habitual para un servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="6d810-162">To run the program as a Windows Service again, install it and start it as usual for a Windows Service.</span></span> <span data-ttu-id="6d810-163">No es necesario invertir estos cambios.</span><span class="sxs-lookup"><span data-stu-id="6d810-163">It's not necessary to reverse these changes.</span></span>  
  
 <span data-ttu-id="6d810-164">En algunos casos, como cuando desea depurar un problema que se produce solo al iniciar el sistema, debe usar el depurador de Windows.</span><span class="sxs-lookup"><span data-stu-id="6d810-164">In some cases, such as when you want to debug an issue that occurs only on system startup, you have to use the Windows debugger.</span></span> <span data-ttu-id="6d810-165">[Descargue Windows Driver Kit (WDK)](/windows-hardware/drivers/download-the-wdk) y consulte [Cómo depurar los servicios de Windows](https://support.microsoft.com/kb/824344).</span><span class="sxs-lookup"><span data-stu-id="6d810-165">[Download the Windows Driver Kit (WDK)](/windows-hardware/drivers/download-the-wdk) and see [How to debug Windows Services](https://support.microsoft.com/kb/824344).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d810-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d810-166">See also</span></span>

- [<span data-ttu-id="6d810-167">Introducción a las aplicaciones de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="6d810-167">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="6d810-168">Cómo: Instalar y desinstalar servicios</span><span class="sxs-lookup"><span data-stu-id="6d810-168">How to: Install and Uninstall Services</span></span>](how-to-install-and-uninstall-services.md)
- [<span data-ttu-id="6d810-169">Cómo: Iniciar servicios</span><span class="sxs-lookup"><span data-stu-id="6d810-169">How to: Start Services</span></span>](how-to-start-services.md)
- [<span data-ttu-id="6d810-170">Depuración de un servicio</span><span class="sxs-lookup"><span data-stu-id="6d810-170">Debugging a Service</span></span>](/windows/desktop/Services/debugging-a-service)

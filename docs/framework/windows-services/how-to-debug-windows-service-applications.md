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
# <a name="how-to-debug-windows-service-applications"></a>Procedimiento para depurar aplicaciones de servicios de Windows
Un servicio se debe ejecutar desde el contexto del Administrador de control de servicios en lugar de desde Visual Studio. Por este motivo, la depuración de un servicio no es tan simple como depurar otros tipos de aplicaciones de Visual Studio. Para depurar un servicio, debe iniciar el servicio y, a continuación, asociar un depurador al proceso en el que se ejecuta. Entonces puede depurar la aplicación mediante el uso de todas las funciones de depuración estándar de Visual Studio.  
  
> [!CAUTION]
> No debe asociarse a un proceso a menos que sepa en qué consiste el proceso y comprenda las consecuencias de la asociación al proceso y de su probable finalización. Por ejemplo, si se asocia al proceso WinLogon y luego detiene la depuración, el sistema se detendrá, porque no puede funcionar sin WinLogon.  
  
 Puede asociar el depurador a un servicio en ejecución. El proceso de asociación interrumpe el funcionamiento actual del servicio; no detiene ni pausa el procesamiento del servicio. Es decir, si el servicio se está ejecutando al iniciar la depuración, todavía está técnicamente en el estado Iniciado al depurarlo, pero su procesamiento se ha suspendido.  
  
 Después de asociarse al proceso, puede establecer puntos de interrupción y usarlos para depurar el código. Una vez que se sale del cuadro de diálogo usado para asociarse al proceso, se encuentra en modo de depuración. Puede usar el Administrador de control de servicios para iniciar, detener, pausar y continuar el servicio, pasando por los puntos de interrupción que ha establecido. Más adelante puede quitar este servicio ficticio después de realizar correctamente la depuración.  
  
 En este artículo se describe la depuración de un servicio que se ejecuta en el equipo local, pero también se pueden depurar servicios de Windows que se ejecuten en un equipo remoto. Consulte [Depuración remota](/visualstudio/debugger/debug-installed-app-package).  
  
> [!NOTE]
> Depurar el método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> puede ser difícil porque el Administrador de control de servicios impone un límite de 30 segundos en todos los intentos de iniciar un servicio. Para más información, vea [Solución de problemas: depuración de servicios de Windows](troubleshooting-debugging-windows-services.md).  
  
> [!WARNING]
> Para obtener información significativa para la depuración, el depurador de Visual Studio debe buscar archivos de símbolos para los archivos binarios que se están depurando. Si depura un servicio que compiló en Visual Studio, los archivos de símbolos (archivos .pdb) están en la misma carpeta que el archivo ejecutable o la biblioteca, y el depurador los carga automáticamente. Si depura un servicio que no compiló, primero debe encontrar los símbolos del servicio y asegurarse de que el depurador los pueda encontrar. Consulte [Especificar archivos de código fuente y símbolos (.pdb) en el depurador de Visual Studio](/visualstudio/debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger). Si depura un proceso del sistema o desea tener símbolos para las llamadas del sistema en los servicios, debe agregar los servidores de símbolos de Microsoft. Consulte [Símbolos de depuración](/windows/desktop/DxTechArts/debugging-with-symbols).  
  
### <a name="to-debug-a-service"></a>Para depurar un servicio  
  
1. Compile el servicio en la configuración de depuración.  
  
2. Instale el servicio. Para obtener más información, vea [Cómo: Instalar y desinstalar servicios](how-to-install-and-uninstall-services.md).  
  
3. Inicie el servicio, desde el **Administrador de control de servicios**, desde el **Explorador de servidores** o desde el código. Para obtener más información, vea [Cómo: Iniciar servicios](how-to-start-services.md).  
  
4. Inicie Visual Studio con credenciales administrativas, para poder asociarse a los procesos del sistema.  
  
5. (Opcional) En la barra de menús de Visual Studio, elija **Herramientas**, **Opciones**. En el cuadro de diálogo **Opciones**, elija **Depuración**, **Símbolos**, active la casilla **Servidores de símbolos de Microsoft** y, a continuación, elija el botón **Aceptar**.  
  
6. En la barra de menús, elija **Asociar al proceso** en el menú **Depurar** o **Herramientas**. (Teclado: Ctrl+Alt+P)  
  
     Aparecerá el cuadro de diálogo **Procesos**.  
  
7. Active la casilla **Mostrar los procesos de todos los usuarios**.  
  
8. En la sección **Procesos disponibles**, elija el proceso del servicio y, a continuación, seleccione **Asociar**.  
  
    > [!TIP]
    > El proceso tendrá el mismo nombre que el archivo ejecutable para el servicio.  
  
     Aparecerá el cuadro de diálogo **Asociar al proceso** .  
  
9. Elija las opciones apropiadas y, a continuación, elija **Aceptar** para cerrar el cuadro de diálogo.  
  
    > [!NOTE]
    > Ahora está en modo de depuración.  
  
10. Establezca los puntos de interrupción que desee usar en el código.  
  
11. Obtenga acceso al Administrador de control de servicios y manipule el servicio; envíe comandos de detención, pausa y continuación para alcanzar los puntos de interrupción. Para más información sobre la ejecución del Administrador de control de servicios, vea [Cómo: Iniciar servicios](how-to-start-services.md). Además, vea [Solución de problemas: depuración de servicios de Windows](troubleshooting-debugging-windows-services.md).  
  
## <a name="debugging-tips-for-windows-services"></a>Sugerencias de depuración para los servicios de Windows  
 Asociarse al proceso del servicio permite depurar gran parte del código de ese servicio, pero no todo. Por ejemplo, si ya se ha iniciado el servicio, no se puede depurar el código del método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> del servicio o el código del método `Main` que se usa para cargar el servicio de esta manera. Una forma de evitar esta limitación es crear un segundo servicio temporal en la aplicación de servicio que solo exista para ayudar en la depuración. Puede instalar ambos servicios y, a continuación, iniciar este servicio ficticio para cargar el proceso del servicio. Una vez que el servicio temporal haya iniciado el proceso, puede usar el menú **Depuración** de Visual Studio para asociarse al proceso del servicio.  
  
 Intente agregar llamadas al método <xref:System.Threading.Thread.Sleep%2A> para retrasar la acción hasta que se pueda asociar al proceso.  
  
 Intente cambiar el programa a una aplicación de consola normal. Para ello, vuelva a escribir el método `Main` como se indica a continuación, de manera que se pueda ejecutar como un servicio de Windows y como una aplicación de consola, en función de cómo se inicie.  
  
#### <a name="how-to-run-a-windows-service-as-a-console-application"></a>Procedimiento para ejecutar un servicio de Windows como una aplicación de consola  
  
1. Agregue un método al servicio que ejecute los métodos <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y <xref:System.ServiceProcess.ServiceBase.OnStop%2A>:  
  
    ```csharp  
    internal void TestStartupAndStop(string[] args)  
    {  
        this.OnStart(args);  
        Console.ReadLine();  
        this.OnStop();  
    }  
    ```  
  
2. Vuelva a escribir el método `Main` como sigue:  
  
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
  
3. En la pestaña **Aplicación** de las propiedades del proyecto, establezca el **Tipo de salida** en **Aplicación de consola**.  
  
4. Elija **Iniciar depuración** (F5).  
  
5. Para volver a ejecutar el programa como un servicio de Windows, instálelo e inícielo de la manera habitual para un servicio de Windows. No es necesario invertir estos cambios.  
  
 En algunos casos, como cuando desea depurar un problema que se produce solo al iniciar el sistema, debe usar el depurador de Windows. [Descargue Windows Driver Kit (WDK)](/windows-hardware/drivers/download-the-wdk) y consulte [Cómo depurar los servicios de Windows](https://support.microsoft.com/kb/824344).  
  
## <a name="see-also"></a>Vea también

- [Introducción a las aplicaciones de servicios de Windows](introduction-to-windows-service-applications.md)
- [Cómo: Instalar y desinstalar servicios](how-to-install-and-uninstall-services.md)
- [Cómo: Iniciar servicios](how-to-start-services.md)
- [Depuración de un servicio](/windows/desktop/Services/debugging-a-service)

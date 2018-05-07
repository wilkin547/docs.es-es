---
title: Introducción a las aplicaciones de servicios de Windows
ms.date: 03/30/2017
f1_keywords:
- ServiceController
helpviewer_keywords:
- Windows Service applications, deploying
- OnStop method
- OnPause method
- services, about services
- Service class, Windows Service applications
- framework services, creating services
- ServiceController components, about Windows services
- Win32OwnProcess service type
- services, lifetime
- OnContinue method
- Windows Service applications, about Windows Service applications
- services, states
- service states
- WaitForStatus method
- Win32ShareProcess service type
- Windows Service applications, lifetime
ms.assetid: 1b1b5e67-3ff3-40c0-8154-322cfd6ef0ae
author: ghogen
manager: douge
ms.openlocfilehash: e0720b90d89e5117cbac15ce7e38a41071f1c13e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="introduction-to-windows-service-applications"></a>Introducción a las aplicaciones de servicios de Windows
Servicios de Microsoft Windows, antes conocidos como servicios NT, permiten crear aplicaciones ejecutables de larga duración que se ejecutan en sus propias sesiones de Windows. Estos servicios pueden iniciarse automáticamente cuando el equipo arranca, se pueden pausar y reiniciar y no muestran ninguna interfaz de usuario. Estas características dificultan servicios ideal para su uso en un servidor o siempre que tenga funcionalidad de ejecución prolongada que no interfiere con otros usuarios que trabajan en el mismo equipo. También puede ejecutar servicios en el contexto de seguridad de una cuenta de usuario que sea diferente del usuario que ha iniciado sesión o la cuenta de equipo predeterminada. Para obtener más información sobre los servicios y sesiones de Windows, consulte la documentación del SDK de Windows.  
  
 Puede crear fácilmente servicios mediante la creación de una aplicación que se instala como un servicio. Por ejemplo, imagine que desea supervisar los datos de contador de rendimiento y reaccionar a valores de umbral. Puede escribir una aplicación de servicio de Windows que realiza escuchas para los datos del contador de rendimiento, implementar la aplicación y empezar a recopilar y analizar los datos.  
  
 Crear el servicio como un proyecto de Microsoft Visual Studio, defina el código que controla qué comandos puede enviarse al servicio y qué acciones deben ejecutarse cuando se reciben esos comandos. Los comandos que se pueden enviar a un servicio incluyen iniciar, pausar, reanudar y detener el servicio; También puede ejecutar comandos personalizados.  
  
 Después de crear y compilar la aplicación, puede instalarlo mediante la ejecución de la utilidad de línea de comandos InstallUtil.exe y pase la ruta de acceso al archivo ejecutable del servicio. A continuación, puede usar el **Administrador de Control de servicios** para iniciar, detener, pausar, reanudar y configurar el servicio. También puede realizar muchas de estas mismas tareas en el **servicios** nodo **Explorador de servidores** o mediante la <xref:System.ServiceProcess.ServiceController> clase.  
  
## <a name="service-applications-vs-other-visual-studio-applications"></a>Frente a las aplicaciones de servicio. Otras aplicaciones de Visual Studio  
 Función de las aplicaciones de servicio de manera diferente a muchos otros tipos de proyecto de varias maneras:  
  
-   El archivo ejecutable compilado que crea un proyecto de aplicación de servicio debe instalarse en el servidor antes de que el proyecto pueda funcionar de forma significativa. No puede depurar o ejecutar una aplicación de servicio, presione la tecla F5 o F11; no se puede ejecutar inmediatamente un servicio o un paso en su código. En su lugar, debe instalar e iniciar el servicio y, a continuación, adjuntar a un depurador al proceso del servicio. Para obtener más información, consulte [Cómo: depurar aplicaciones de servicios de Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md).  
  
-   A diferencia de algunos tipos de proyectos, debe crear componentes de instalación para las aplicaciones de servicio. Los componentes de instalación, instalar y registrar el servicio en el servidor y crear una entrada para el servicio con las ventanas **Administrador de Control de servicios**. Para obtener más información, consulte [Cómo: agregar instaladores a la aplicación de servicio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
-   El `Main` método para la aplicación de servicio debe emitir el comando Run para los servicios de su proyecto contiene. El `Run` método carga los servicios en la **Administrador de Control de servicios** en el servidor apropiado. Si usas el **Windows Services** plantilla de proyecto, este método se escribirá automáticamente. Tenga en cuenta que cargar un servicio no es lo mismo que iniciar el servicio. Vea "Duración del servicio" a continuación para obtener más información.  
  
-   Aplicaciones de servicios de Windows se ejecutan en una estación de ventana diferente a la sesión interactiva del usuario que ha iniciado sesión. Una estación de ventana es un objeto seguro que contiene un Portapapeles, un conjunto de átomos globales y un grupo de objetos de escritorio. Dado que la estación de servicio de Windows no es una sesión interactiva, cuadros de diálogo generan desde dentro de una ventana de aplicación de servicio no se verán y puede provocar que el programa deje de responder. Del mismo modo, mensajes de error deben se registran en el registro de eventos de Windows en lugar de hacerlo en la interfaz de usuario.  
  
     Las clases de servicio de Windows compatibles con .NET Framework no admiten la interacción con estaciones interactivas, es decir, el usuario ha iniciado sesión. .NET Framework no también incluye clases que representan las estaciones y escritorios. Si el servicio de Windows debe interactuar con otras estaciones, debe tener acceso a la API no administrada de Windows. Para obtener más información, consulte la documentación del SDK de Windows.  
  
     La interacción de las ventanas de servicio con el usuario u otras estaciones debe diseñarse con cuidado para que incluya casos tales como que se va a ningún usuario ha iniciado sesión o el usuario tenga un conjunto inesperado de objetos de escritorio. En algunos casos, puede ser más adecuado escribir una aplicación de Windows que se ejecuta bajo el control del usuario.  
  
-   Las aplicaciones de servicio de Windows se ejecutan en su propio contexto de seguridad y se inician antes el usuario inicia sesión en el equipo de Windows en el que se instalan. Debe considerar detenidamente en qué cuenta de usuario para ejecutar el servicio; un servicio que se ejecuta bajo la cuenta del sistema tiene más permisos y privilegios que una cuenta de usuario.  
  
## <a name="service-lifetime"></a>Duración del servicio  
 Un servicio pasa por varios Estados internos de su duración. En primer lugar, el servicio está instalado en el sistema en el que se ejecutará. Este proceso ejecuta los instaladores para el proyecto de servicio y carga el servicio en la **Administrador de Control de servicios** de ese equipo. El **Administrador de Control de servicios** es la utilidad central que proporciona Windows para administrar servicios.  
  
 Después de haberse cargado el servicio, debe estar iniciado. Iniciando el servicio le permite comenzar a funcionar. Puede iniciar un servicio desde el **Administrador de Control de servicios**, de **Explorador de servidores**, o desde el código mediante una llamada a la <xref:System.ServiceProcess.ServiceController.Start%2A> método. El <xref:System.ServiceProcess.ServiceController.Start%2A> método pasa el procesamiento a la aplicación <xref:System.ServiceProcess.ServiceBase.OnStart%2A> método y procesa el código que haya definido allí.  
  
 Puede existir un servicio en ejecución en este estado indefinidamente hasta que se ha detenido o en pausa o hasta que el equipo se apaga. Un servicio puede residir en uno de estos tres estados básicos: <xref:System.ServiceProcess.ServiceControllerStatus.Running>, <xref:System.ServiceProcess.ServiceControllerStatus.Paused>, o <xref:System.ServiceProcess.ServiceControllerStatus.Stopped>. El servicio también puede informar del estado de un comando pendiente: <xref:System.ServiceProcess.ServiceControllerStatus.ContinuePending>, <xref:System.ServiceProcess.ServiceControllerStatus.PausePending>, <xref:System.ServiceProcess.ServiceControllerStatus.StartPending>, o <xref:System.ServiceProcess.ServiceControllerStatus.StopPending>. Estos estados indican que un comando ha sido emitido, por ejemplo, un comando para pausar un servicio en ejecución, pero no se ha efectuado aún. Puede consultar la <xref:System.ServiceProcess.ServiceController.Status%2A> para determinar lo que un servicio de estado, o usar el <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A> para llevar a cabo una acción cuando cualquiera de estos estados se produce.  
  
 Puede pausar, detener o reanudar un servicio desde el **Administrador de Control de servicios**, de **Explorador de servidores**, o puede llamar a métodos en el código. Cada una de estas acciones puede llamar a un procedimiento asociado en el servicio (<xref:System.ServiceProcess.ServiceBase.OnStop%2A>, <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, o <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>), en el que puede definir un procesamiento adicional que se realizará cuando el servicio cambia el estado.  
  
## <a name="types-of-services"></a>Tipos de servicios  
 Hay dos tipos de servicios que puede crear en Visual Studio con .NET Framework. Servicios que son el único servicio en un proceso se asignan al tipo <xref:System.ServiceProcess.ServiceType.Win32OwnProcess>. Los servicios que comparten un proceso con otro servicio se asignan al tipo <xref:System.ServiceProcess.ServiceType.Win32ShareProcess>. Puede recuperar el tipo de servicio consultando la <xref:System.ServiceProcess.ServiceController.ServiceType%2A> propiedad.  
  
 En ocasiones, podría ver otros tipos de servicios si consulta servicios existentes que no se crearon en Visual Studio. Para obtener más información al respecto, consulte el <xref:System.ServiceProcess.ServiceType>.  
  
## <a name="services-and-the-servicecontroller-component"></a>Servicios y el componente ServiceController  
 El <xref:System.ServiceProcess.ServiceController> componente se utiliza para conectarse a un servicio instalado y manipular su estado; mediante una <xref:System.ServiceProcess.ServiceController> , componente, puede iniciar y detener un servicio, pausar y continuar con su funcionamiento y enviar comandos personalizados a un servicio. Sin embargo, no es necesario usar un <xref:System.ServiceProcess.ServiceController> componente cuando se crea una aplicación de servicio. De hecho, en la mayoría de los casos la <xref:System.ServiceProcess.ServiceController> componente debe existir en una aplicación independiente de la aplicación de servicio de Windows que define el servicio.  
  
 Para obtener más información, consulta <xref:System.ServiceProcess.ServiceController>.  
  
## <a name="requirements"></a>Requisitos  
  
-   Servicios deben crearse en un **servicio de Windows** proyecto de aplicación o en otro proyecto compatible con .NET Framework que crea un archivo .exe cuando se compila y se hereda de la <xref:System.ServiceProcess.ServiceBase> clase.  
  
-   Proyectos que contienen servicios de Windows deben tener componentes de instalación para el proyecto y sus servicios. Esto puede realizarse fácilmente desde la **propiedades** ventana. Para obtener más información, consulte [Cómo: agregar instaladores a la aplicación de servicio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
## <a name="see-also"></a>Vea también  
 [Aplicaciones de servicios de Windows](../../../docs/framework/windows-services/index.md)  
 [Arquitectura de programación de aplicaciones de servicio](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 [Creación de servicios de Windows](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [Instalación y desinstalación de servicios](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)  
 [Inicio de servicios](../../../docs/framework/windows-services/how-to-start-services.md)  
 [Depuración de aplicaciones de servicios de Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)  
 [Tutorial: Creación de una aplicación de servicios de Windows en el Diseñador de componentes](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 [Adición de instaladores a una aplicación de servicio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)

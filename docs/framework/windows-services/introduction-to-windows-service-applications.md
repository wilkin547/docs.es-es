---
title: Introducción a las aplicaciones de servicios de Windows
description: Lea una introducción sobre las aplicaciones de servicios de Windows. Los servicios permiten crear aplicaciones ejecutables de larga ejecución que se ejecutan en sus propias sesiones de Windows.
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
ms.openlocfilehash: fd69ca11d42a229b861bafd642383e89f0119815
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96270476"
---
# <a name="introduction-to-windows-service-applications"></a>Introducción a las aplicaciones de servicios de Windows

Los servicios de Microsoft Windows, anteriormente conocidos como servicios NT, le permiten crear aplicaciones de larga ejecución que se ejecutan en sesiones propias de Windows. Estos servicios se pueden iniciar automáticamente al arrancar el equipo, se pueden pausar y reiniciar, y no muestran ninguna interfaz de usuario. Estas características hacen que los servicios sean idóneos para su uso en un servidor o siempre que necesite una funcionalidad de larga duración que no interfiera con otros usuarios que estén trabajando en el mismo equipo. También puede ejecutar servicios en el contexto de seguridad de una cuenta de usuario específica que sea diferente del usuario conectado o de la cuenta de equipo predeterminada. Para obtener más información acerca de los servicios y las sesiones de Windows, consulte la documentación de Windows SDK.  
  
 Puede crear servicios fácilmente mediante la creación de una aplicación que se instale como un servicio. Por ejemplo, suponga que desea supervisar datos del contador de rendimiento y reaccionar a valores de umbral. Puede escribir una aplicación de servicio de Windows que escuche los datos del contador de rendimiento, implemente la aplicación y comience a recopilar y analizar datos.  
  
 Cree el servicio como un proyecto de Microsoft Visual Studio y defina el código dentro de él que controle qué comandos se pueden enviar al servicio y qué acciones se deben realizar cuando se reciben esos comandos. Los comandos que se pueden enviar a un servicio incluyen iniciar, pausar, reanudar y detener el servicio; también puede ejecutar comandos personalizados.  
  
 Después de crear y compilar la aplicación, puede instalarla mediante la ejecución de la utilidad de línea de comandos InstallUtil.exe y el paso de la ruta de acceso al archivo ejecutable del servicio. A continuación, puede usar el **Administrador de control de servicios** para iniciar, detener, pausar, reanudar y configurar el servicio. También puede realizar muchas de estas mismas tareas en el nodo **Servicios** en el **Explorador de servidores** o utilizando la clase <xref:System.ServiceProcess.ServiceController>.  
  
## <a name="service-applications-vs-other-visual-studio-applications"></a>Aplicaciones de servicios y Otras aplicaciones de Visual Studio  

 Las aplicaciones de servicios funcionan de forma diferente a muchos otros tipos de proyectos de varias maneras:  
  
- El archivo ejecutable compilado que crea un proyecto de aplicación de servicio debe instalarse en el servidor antes de que el proyecto pueda funcionar de forma significativa. No puede depurar o ejecutar una aplicación de servicio, presione las teclas F5 o F11; no puede ejecutar inmediatamente un servicio o depurar paso a paso el código por instrucciones. En su lugar, debe instalar e iniciar el servicio y, después, asociar un depurador al proceso del servicio. Para obtener más información, vea [Cómo: Depurar aplicaciones de servicios de Windows](how-to-debug-windows-service-applications.md).  
  
- A diferencia de algunos tipos de proyectos, debe crear componentes de instalación para aplicaciones de servicios. Los componentes de instalación instalan y registran el servicio en el servidor y crean una entrada para el servicio con el **Administrador de control de servicios de Windows**. Para obtener más información, vea [Cómo: Agregar instaladores a una aplicación de servicio](how-to-add-installers-to-your-service-application.md).  
  
- El método `Main` para la aplicación de servicio debe emitir el comando Ejecutar para los servicios que contiene el proyecto. El método `Run` carga los servicios en el **Administrador de control de servicios** en el servidor apropiado. Si utiliza la plantilla de proyecto de **servicios de Windows**, este método se escribe automáticamente. Tenga en cuenta que cargar un servicio no es lo mismo que iniciarlo. Consulte "Duración del servicio" más abajo para obtener más información.  
  
- Las aplicaciones de servicios de Windows se ejecutan en una estación de ventana diferente a la sesión interactiva del usuario que ha iniciado sesión. Una estación de ventana es un objeto seguro que contiene un Portapapeles, un conjunto de átomos globales y un grupo de objetos de escritorio. Debido a que la estación del servicio Windows no es una estación interactiva, no se verán los cuadros de diálogo que aparecen desde una aplicación de servicio de Windows y es posible que el programa deje de responder. Del mismo modo, los mensajes de error deben registrarse en el registro de eventos de Windows en lugar de aparecer en la interfaz de usuario.  
  
     Las clases de servicio de Windows compatibles con .NET Framework no admiten la interacción con estaciones interactivas, es decir, el usuario conectado. .NET Framework tampoco incluye clases que representan las estaciones y escritorios. Si el servicio de Windows debe interactuar con otras estaciones, debe tener acceso a la API no administrada de Windows. Para más información, consulte la documentación de Windows SDK.  
  
     La interacción del servicio de Windows con el usuario u otras estaciones debe diseñarse cuidadosamente para incluir escenarios tales como que no haya ningún usuario conectado o que el usuario tenga un conjunto inesperado de objetos de escritorio. En algunos casos, puede ser más adecuado escribir una aplicación de Windows que se ejecute bajo el control del usuario.  
  
- Las aplicaciones de servicios de Windows se ejecutan en su propio contexto de seguridad y se inician antes de que el usuario inicie sesión en el equipo con Windows en el que están instaladas. Debe planificar cuidadosamente la cuenta de usuario en la que se ejecutará el servicio; un servicio que se ejecute bajo la cuenta del sistema tiene más permisos y privilegios que una cuenta de usuario.  
  
## <a name="service-lifetime"></a>Duración del servicio  

 Un servicio pasa por varios estados internos durante su vigencia. En primer lugar, el servicio se instala en el sistema en el que se va a ejecutar. Este proceso ejecuta los instaladores para el proyecto de servicio y carga el servicio en el **Administrador de control de servicios** de ese equipo. El **Administrador de control de servicios** es la utilidad central que proporciona Windows para administrar servicios.  
  
 Después de que se haya cargado el servicio, debe iniciarse. Iniciar el servicio le permite comenzar a funcionar. Puede iniciar un servicio desde el **Administrador de control de servicios**, desde el **Explorador de servidores** o desde el código llamando al método <xref:System.ServiceProcess.ServiceController.Start%2A>. El método <xref:System.ServiceProcess.ServiceController.Start%2A> pasa el procesamiento al método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> de la aplicación y procesa cualquier código que haya definido allí.  
  
 Un servicio en ejecución puede existir en este estado indefinidamente hasta que se detenga o esté en pausa o hasta que el equipo se apague. Un servicio puede existir en uno de estos tres estados básicos: <xref:System.ServiceProcess.ServiceControllerStatus.Running>, <xref:System.ServiceProcess.ServiceControllerStatus.Paused> o <xref:System.ServiceProcess.ServiceControllerStatus.Stopped>. El servicio también puede informar del estado de un comando pendiente: <xref:System.ServiceProcess.ServiceControllerStatus.ContinuePending>, <xref:System.ServiceProcess.ServiceControllerStatus.PausePending>, <xref:System.ServiceProcess.ServiceControllerStatus.StartPending> o <xref:System.ServiceProcess.ServiceControllerStatus.StopPending>. Estos estados indican que se ha emitido un comando, como un comando para pausar un servicio en ejecución, pero que aún no se ha ejecutado. Puede consultar <xref:System.ServiceProcess.ServiceController.Status%2A> para determinar en qué estado se encuentra un servicio, o utilizar <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A> para llevar a cabo una acción cuando se produce cualquiera de estos estados.  
  
 Puede pausar, detener o reanudar un servicio desde el **Administrador de control de servicios**, desde el **Explorador de servidores** o llamando a métodos en el código. Cada una de estas acciones puede llamar a un procedimiento asociado en el servicio (<xref:System.ServiceProcess.ServiceBase.OnStop%2A>, <xref:System.ServiceProcess.ServiceBase.OnPause%2A> o <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>), en el que se puede definir el procesamiento adicional que se realizará cuando el servicio cambie de estado.  
  
## <a name="types-of-services"></a>Tipos de servicios  

 Hay dos tipos de servicios que puede crear en Visual Studio con .NET Framework. Los servicios que son el único servicio de un proceso se asignan al tipo <xref:System.ServiceProcess.ServiceType.Win32OwnProcess>. Los servicios que comparten un proceso con otro servicio se asignan al tipo <xref:System.ServiceProcess.ServiceType.Win32ShareProcess>. Puede recuperar el tipo de servicio consultando la propiedad <xref:System.ServiceProcess.ServiceController.ServiceType%2A>.  
  
 Ocasionalmente puede ver otros tipos de servicio si consulta los servicios existentes que no se crearon en Visual Studio. Para más información sobre ellos, consulte <xref:System.ServiceProcess.ServiceType>.  
  
## <a name="services-and-the-servicecontroller-component"></a>Servicios y el componente ServiceController  

 El componente <xref:System.ServiceProcess.ServiceController> se utiliza para conectarse a un servicio instalado y manipular su estado; mediante un componente <xref:System.ServiceProcess.ServiceController>, puede iniciar y detener un servicio, hacer una pausa y continuar su funcionamiento, y enviar comandos personalizados a un servicio. Sin embargo, no es necesario usar un componente <xref:System.ServiceProcess.ServiceController> cuando se crea una aplicación de servicio. De hecho, en la mayoría de los casos el componente <xref:System.ServiceProcess.ServiceController> debería existir en una aplicación independiente de la aplicación de servicio de Windows que define el servicio.  
  
 Para obtener más información, vea <xref:System.ServiceProcess.ServiceController>.  
  
## <a name="requirements"></a>Requisitos  
  
- Los servicios deben crearse en un proyecto de aplicación de **servicio de Windows** u otro proyecto habilitado para .NET Framework que cree un archivo .exe cuando se crea y herede de la clase <xref:System.ServiceProcess.ServiceBase>.  
  
- Los proyectos que contengan servicios de Windows deben tener componentes de instalación para el proyecto y sus servicios. Esto se puede lograr fácilmente desde la ventana **Propiedades**. Para obtener más información, vea [Cómo: Agregar instaladores a una aplicación de servicio](how-to-add-installers-to-your-service-application.md).  
  
## <a name="see-also"></a>Vea también

- [Aplicaciones de servicios de Windows](index.md)
- [Arquitectura de programación de aplicaciones de servicio](service-application-programming-architecture.md)
- [Cómo: Creación de servicios de Windows](how-to-create-windows-services.md)
- [Cómo: Instalar y desinstalar servicios](how-to-install-and-uninstall-services.md)
- [Cómo: Iniciar servicios](how-to-start-services.md)
- [Cómo: Depurar aplicaciones de servicios de Windows](how-to-debug-windows-service-applications.md)
- [Tutorial: Creación de una aplicación de servicios de Windows en el Diseñador de componentes](walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
- [Cómo: Adición de instaladores a una aplicación de servicio](how-to-add-installers-to-your-service-application.md)

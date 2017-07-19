---
title: "Introduction to Windows Service Applications | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ServiceController"
helpviewer_keywords: 
  - "Windows Service applications, deploying"
  - "OnStop method"
  - "OnPause method"
  - "services, about services"
  - "Service class, Windows Service applications"
  - "framework services, creating services"
  - "ServiceController components, about Windows services"
  - "Win32OwnProcess service type"
  - "services, lifetime"
  - "OnContinue method"
  - "Windows Service applications, about Windows Service applications"
  - "services, states"
  - "service states"
  - "WaitForStatus method"
  - "Win32ShareProcess service type"
  - "Windows Service applications, lifetime"
ms.assetid: 1b1b5e67-3ff3-40c0-8154-322cfd6ef0ae
caps.latest.revision: 17
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 17
---
# Introduction to Windows Service Applications
Los servicios de Microsoft Windows, antes conocidos como servicios NT, permiten crear aplicaciones ejecutables de larga duración, que se ejecutan en sus propias sesiones de Windows.  Estos servicios pueden iniciarse automáticamente cuando el equipo arranca, se pueden pausar y reiniciar, y no muestran ninguna interfaz de usuario.  Estas características hacen que los servicios resulten perfectos para ejecutarse en un servidor o donde se necesite una funcionalidad de ejecución larga que no interfiera con los demás usuarios que trabajen en el mismo equipo.  También puede ejecutar servicios en el contexto de seguridad de una cuenta de usuario específica, diferente de la del usuario que inició la sesión o de la cuenta predeterminada del equipo.  Para obtener más información sobre los servicios y sesiones de Windows, consulte la documentación referente a Windows SDK en MSDN Library.  
  
 Puede crear servicios fácilmente mediante el desarrollo de aplicaciones que se instalan como servicios.  Por ejemplo, suponga que desea supervisar los datos del contador de rendimiento y reaccionar a valores umbral.  Podría escribir una aplicación de servicios de Windows que lea los datos del contador de rendimiento, implementar la aplicación y comenzar a recoger y analizar los datos.  
  
 El servicio se crea como proyecto de Microsoft Visual Studio, se define el código que controla qué comandos se pueden enviar al servicio y qué acciones se deben realizar al recibir esos comandos.  Entre los comandos que se pueden enviar a un servicio se encuentran los comandos de inicio, pausa, reanudación y detención del servicio; asimismo, puede ejecutar comandos personalizados.  
  
 Después de crear y generar la aplicación, puede instalarla ejecutando la utilidad de línea de comandos InstallUtil.exe y pasando la ruta de acceso al archivo ejecutable del servicio.  A continuación, puede utilizar el **Administrador de control de servicios** para iniciar, detener, pausar, reanudar y configurar el servicio.  Además, puede realizar muchas de estas mismas tareas en el nodo **Servicios** del **Explorador de servidores** o al usar la clase <xref:System.ServiceProcess.ServiceController>.  
  
## Aplicaciones de servicio frente a otras aplicaciones de Visual Studio  
 Las aplicaciones de servicios funcionan, en varios aspectos, de forma diferente a muchos otros tipos de proyectos:  
  
-   El archivo ejecutable compilado que crea un proyecto de aplicación de servicios debe instalarse en el servidor para que el proyecto pueda funcionar de forma significativa.  No es posible depurar o ejecutar una aplicación de servicios presionando F5 o F11; no es posible ejecutar inmediatamente un servicio o ejecutarlo paso a paso en su código.  En su lugar, es necesario instalar e iniciar el servicio y, a continuación, adjuntar un depurador al proceso del servicio.  Para obtener más información, vea [How to: Debug Windows Service Applications](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md).  
  
-   A diferencia de algunos tipos de proyectos, deberá crear componentes de instalación para las aplicaciones de servicios.  Los componentes de instalación instalan y registran el servicio en el servidor y crean una entrada para el servicio con el **Administrador de control de servicios** de Windows.  Para obtener más información, vea [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
-   El método `Main` para la aplicación de servicios debe emitir el comando Run para los servicios que contiene el proyecto.  El método `Run` carga los servicios en el **Administrador de control de servicios** del servidor adecuado.  Si utiliza la plantilla de proyecto **Servicios de Windows**, este método se escribirá automáticamente.  Tenga en cuenta que cargar un servicio no es lo mismo que iniciarlo.  Vea el apartado "Duración de los servicios" para obtener más información.  
  
-   Las aplicaciones de servicios de Windows se ejecutan en una sesión de ventana diferente a la sesión interactiva del usuario que ha iniciado una sesión.  Una estación de ventana es un objeto seguro que contiene un Portapapeles, un conjunto de átomos globales y un grupo de objetos de escritorio.  Puesto que la estación de un servicio de Windows no es interactiva, los cuadros de diálogo que proceden de una aplicación de servicio de Windows no se ven y pueden causar que el programa deje de responder.  Asimismo, es recomendable registrar los mensajes de error en el registro de eventos de Windows, en lugar de hacerlo en la interfaz del usuario.  
  
     Las clases de servicios de Windows compatibles con .NET Framework no admiten la interacción con estaciones interactivas, es decir, con el usuario que ha iniciado una sesión.  .NET Framework tampoco incluye clases que representen estaciones y escritorios.  Si el servicio de Windows debe interactuar con otras estaciones, deberá obtener acceso a la API de Windows no administrada.  Para obtener más información, consulte la documentación referente a Windows SDK.  
  
     La interacción del servicio de Windows con el usuario u otras estaciones debe diseñarse con cuidado para que incluya casos como, por ejemplo, que no exista un usuario que haya iniciado una sesión o que el usuario tenga un conjunto inesperado de objetos de escritorio.  En algunos casos, puede ser más apropiado escribir una aplicación para Windows que se ejecute bajo el control del usuario.  
  
-   Las aplicaciones de servicios de Windows se ejecutan en su propio contexto de seguridad y se inician antes de que el usuario inicie la sesión en el equipo Windows en el que se encuentran instaladas.  Debe considerar detenidamente en qué cuenta de usuario se ejecutará el servicio; un servicio que se ejecute bajo la cuenta del sistema tendrá más permisos y privilegios que una cuenta de usuario.  
  
## Duración de los servicios  
 Un servicio pasa por varios estados internos a lo largo de su duración.  En primer lugar, se instala el servicio en el sistema en el que se ejecutará.  Este proceso ejecuta los instaladores para el proyecto del servicio y carga el servicio en el **Administrador de control de servicios** del equipo.  El **Administrador de control de servicios** es la utilidad central que proporciona Windows para administrar servicios.  
  
 Una vez cargado el servicio, es necesario iniciarlo.  Al iniciar el servicio, se permite que empiece a funcionar.  Puede iniciar un servicio desde el **Administrador de control de servicios**, desde el **Explorador de servidores** o desde código llamando al método <xref:System.ServiceProcess.ServiceController.Start%2A>.  El método <xref:System.ServiceProcess.ServiceController.Start%2A> pasa el procesamiento al método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> de la aplicación y procesa el código que haya definido allí.  
  
 Un servicio en ejecución puede permanecer indefinidamente en este estado, hasta que se detiene o se pausa, o hasta que se apaga el equipo.  Un servicio puede estar en uno de estos tres estados básicos: <xref:System.ServiceProcess.ServiceControllerStatus>, <xref:System.ServiceProcess.ServiceControllerStatus> o <xref:System.ServiceProcess.ServiceControllerStatus>.  El servicio también puede informar del estado de un comando pendiente: <xref:System.ServiceProcess.ServiceControllerStatus>, <xref:System.ServiceProcess.ServiceControllerStatus>, <xref:System.ServiceProcess.ServiceControllerStatus> o <xref:System.ServiceProcess.ServiceControllerStatus>.  Estos estados indican que se emitió un comando, por ejemplo, para hacer una pausa en un servicio en ejecución, pero que el comando aún no se ejecutó.  Puede consultar <xref:System.ServiceProcess.ServiceController.Status%2A> para determinar en qué estado se encuentra el servicio, o bien utilizar <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A> para realizar una acción cuando se produzca uno de estos estados.  
  
 Puede pausar, detener o reanudar un servicio desde el **Administrador de control de servicios**, desde el **Explorador de servidores** o llamando a los métodos adecuados desde el código.  Cada una de estas acciones puede llamar a un procedimiento asociado en el servicio \(<xref:System.ServiceProcess.ServiceBase.OnStop%2A>, <xref:System.ServiceProcess.ServiceBase.OnPause%2A> o <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>\), en el que es posible definir procesos adicionales que se realizarán cuando cambie el estado del servicio.  
  
## Tipos de servicios  
 Hay dos tipos de servicios que puede crear en Visual Studio utilizando .NET Framework.  Los servicios que son el único servicio de un proceso se asignan al tipo <xref:System.ServiceProcess.ServiceType>.  Los servicios que comparten un proceso con otro servicio se asignan al tipo <xref:System.ServiceProcess.ServiceType>.  Puede recuperar el tipo de servicio consultando la propiedad <xref:System.ServiceProcess.ServiceController.ServiceType%2A>.  
  
 Ocasionalmente, podría ver otros tipos de servicio si consulta servicios existentes que no se crearon en Visual Studio.  Para obtener más información al respecto, vea <xref:System.ServiceProcess.ServiceType>.  
  
## Los servicios y el componente ServiceController  
 El componente <xref:System.ServiceProcess.ServiceController> se utiliza para conectarse con un servicio instalado y manipular su estado. Al utilizar un componente <xref:System.ServiceProcess.ServiceController>, puede iniciar y detener un servicio, hacer una pausa y continuar con su funcionamiento, así como enviar comandos personalizados a un servicio.  Sin embargo, no necesita utilizar un componente <xref:System.ServiceProcess.ServiceController> cuando crea una aplicación de servicio.  En realidad, en la mayoría de los casos el componente <xref:System.ServiceProcess.ServiceController> deberá existir en una aplicación separada de la aplicación de servicios de Windows que define el servicio.  
  
 Para obtener más información, vea <xref:System.ServiceProcess.ServiceController>.  
  
## Requisitos  
  
-   Los servicios deben crearse en un proyecto de aplicación de **Servicio de Windows** o en otro proyecto compatible con .NET Framework que cree un archivo .exe al ser generado y que herede de la clase<xref:System.ServiceProcess.ServiceBase>.  
  
-   Los proyectos que contienen servicios de Windows deben tener componentes de instalación para el proyecto y sus servicios.  Esto se puede hacer fácilmente desde la ventana **Propiedades**.  Para obtener más información, vea [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
## Vea también  
 [Windows Service Applications](../../../docs/framework/windows-services/index.md)   
 [Service Application Programming Architecture](../../../docs/framework/windows-services/service-application-programming-architecture.md)   
 [How to: Create Windows Services](../../../docs/framework/windows-services/how-to-create-windows-services.md)   
 [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)   
 [How to: Start Services](../../../docs/framework/windows-services/how-to-start-services.md)   
 [How to: Debug Windows Service Applications](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)   
 [Walkthrough: Creating a Windows Service Application in the Component Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)   
 [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)
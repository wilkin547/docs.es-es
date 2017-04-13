---
title: "How to: Create Windows Services | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Windows Service applications, creating"
  - "templates, Windows Service"
ms.assetid: 0f5e2cbb-d95d-477c-b2b5-4b990e6b86ff
caps.latest.revision: 18
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 18
---
# How to: Create Windows Services
Al crear un servicio, puede usar una plantilla de proyecto de Visual Studio denominada **Servicio de Windows**.  Esta plantilla realiza automáticamente gran parte del trabajo: hace referencia a las clases y los espacios de nombres correctos, configura la herencia de la clase base para los servicios y reemplazar algunos de los métodos que es probable que desee reemplazar.  
  
> [!WARNING]
>  La plantilla de proyecto Servicios de Windows no está disponible en la edición Express de Visual Studio.  
  
 Como mínimo, para crear un servicio funcional, deberá:  
  
-   Establecer la propiedad <xref:System.ServiceProcess.ServiceBase.ServiceName%2A>.  
  
-   Crear los instaladores necesarios para la aplicación de servicio.  
  
-   Reemplazar y especificar el código para los métodos <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y <xref:System.ServiceProcess.ServiceBase.OnStop%2A> para personalizar el modo en que se comporta el servicio.  
  
### Para crear una aplicación de servicio de Windows  
  
1.  Cree un proyecto de **Servicio Windows**.  
  
    > [!NOTE]
    >  Para obtener instrucciones sobre cómo escribir un servicio sin usar la plantilla, vea [How to: Write Services Programmatically](../../../docs/framework/windows-services/how-to-write-services-programmatically.md).  
  
2.  En la ventana **Propiedades**, establezca la propiedad <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> para el servicio.  
  
     ![Establezca la propiedad ServiceName.](../../../docs/framework/windows-services/media/windowsservice-servicename.png "WindowsService\_ServiceName")  
  
    > [!NOTE]
    >  El valor de la propiedad <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> siempre debe coincidir con el nombre registrado en las clases del instalador.  Si cambia esta propiedad, también debe actualizar la propiedad <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> de las clases del instalador.  
  
3.  Establezca cualquiera de las siguientes propiedades para determinar cómo funcionará el servicio.  
  
    |Propiedad|Parámetro|  
    |---------------|---------------|  
    |<xref:System.ServiceProcess.ServiceBase.CanStop%2A>|`True` para indicar que el servicio aceptará solicitudes para detener la ejecución; `false` para impedir que el servicio se detenga.|  
    |<xref:System.ServiceProcess.ServiceBase.CanShutdown%2A>|`True` para indicar que el servicio desea recibir una notificación cuando se apaga el equipo en que reside, lo que le permite llamar al procedimiento <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>.|  
    |<xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A>|`True` para indicar que el servicio aceptará solicitudes para pausar o reanudar la ejecución; `false` para impedir que el servicio se pause y se reanude.|  
    |<xref:System.ServiceProcess.ServiceBase.CanHandlePowerEvent%2A>|`True`  para indicar que el servicio puede controlar la notificación de cambios en el estado de alimentación del equipo; `false` para impedir la notificación al servicio de estos cambios.|  
    |<xref:System.ServiceProcess.ServiceBase.AutoLog%2A>|`True` para escribir entradas informativas en el registro de sucesos de aplicación cuando el servicio realice una acción; `false` para deshabilitar esta funcionalidad.  Para obtener más información, vea [How to: Log Information About Services](../../../docs/framework/windows-services/how-to-log-information-about-services.md). **Note:**  De manera predeterminada, <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> se establece en `true`.|  
  
    > [!NOTE]
    >  Cuando <xref:System.ServiceProcess.ServiceBase.CanStop%2A> `` o <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> `` se establecen en `false`, el **Administrador de control de servicios** deshabilitará las opciones de menú correspondientes para detener, pausar o continuar el servicio.  
  
4.  Obtenga acceso al Editor de código y rellene el procesamiento que desee para los procedimientos <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y <xref:System.ServiceProcess.ServiceBase.OnStop%2A>.  
  
5.  Reemplace los otros métodos para los que desee definir la funcionalidad.  
  
6.  Agregar los instaladores necesarios para su aplicación de servicio.  Para obtener más información, vea [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
7.  En el menú **Compilar**, seleccione **Compilar solución** para compilar el proyecto.  
  
    > [!NOTE]
    >  No presione F5 para ejecutar el proyecto: no se puede ejecutar un proyecto de servicio de esta manera.  
  
8.  Instale el servicio.  Para obtener más información, vea [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).  
  
## Vea también  
 [Introduction to Windows Service Applications](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)   
 [How to: Write Services Programmatically](../../../docs/framework/windows-services/how-to-write-services-programmatically.md)   
 [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)   
 [How to: Log Information About Services](../../../docs/framework/windows-services/how-to-log-information-about-services.md)   
 [How to: Start Services](../../../docs/framework/windows-services/how-to-start-services.md)   
 [How to: Specify the Security Context for Services](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)   
 [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)   
 [Walkthrough: Creating a Windows Service Application in the Component Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
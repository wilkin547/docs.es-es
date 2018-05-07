---
title: 'Cómo: Crear servicios de Windows'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, creating
- templates, Windows Service
ms.assetid: 0f5e2cbb-d95d-477c-b2b5-4b990e6b86ff
author: ghogen
manager: douge
ms.openlocfilehash: 7719af9393bee816665040d6e4ced191419d0855
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-windows-services"></a>Cómo: Crear servicios de Windows
Cuando se crea un servicio, puede usar una plantilla de proyecto de Visual Studio denominada **servicio de Windows**. Esta plantilla realiza automáticamente gran parte del trabajo: hace referencia a las clases y los espacios de nombres correctos, configura la herencia de la clase base para los servicios y reemplazar algunos de los métodos que es probable que desee reemplazar.  
  
> [!WARNING]
>  La plantilla de proyecto Servicios de Windows no está disponible en la edición Express de Visual Studio.  
  
 Como mínimo, para crear un servicio funcional, deberá:  
  
-   Establecer la propiedad <xref:System.ServiceProcess.ServiceBase.ServiceName%2A>.  
  
-   Crear los instaladores necesarios para la aplicación de servicio.  
  
-   Reemplazar y especificar el código para los métodos <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y <xref:System.ServiceProcess.ServiceBase.OnStop%2A> para personalizar el modo en que se comporta el servicio.  
  
### <a name="to-create-a-windows-service-application"></a>Para crear una aplicación de servicio de Windows  
  
1.  Crear un **servicio de Windows** proyecto.  
  
    > [!NOTE]
    >  Para obtener instrucciones sobre cómo escribir un servicio sin utilizar la plantilla, consulte [Cómo: escribir servicios mediante programación](../../../docs/framework/windows-services/how-to-write-services-programmatically.md).  
  
2.  En el **propiedades** ventana, establezca el <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> propiedad para el servicio.  
  
     ![Establezca la propiedad ServiceName. ] (../../../docs/framework/windows-services/media/windowsservice-servicename.PNG "WindowsService_ServiceName")  
  
    > [!NOTE]
    >  El valor de la propiedad <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> siempre debe coincidir con el nombre registrado en las clases del instalador. Si cambia esta propiedad, también debe actualizar la propiedad <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> de las clases del instalador.  
  
3.  Establezca cualquiera de las siguientes propiedades para determinar cómo funcionará el servicio.  
  
    |Propiedad|Parámetro|  
    |--------------|-------------|  
    |<xref:System.ServiceProcess.ServiceBase.CanStop%2A>|`True` para indicar que el servicio aceptará solicitudes para detener la ejecución; `false` para impedir que el servicio se detenga.|  
    |<xref:System.ServiceProcess.ServiceBase.CanShutdown%2A>|`True` para indicar que el servicio desea recibir una notificación cuando se apaga el equipo en que reside, lo que le permite llamar al procedimiento <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>.|  
    |<xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A>|`True` para indicar que el servicio aceptará solicitudes para pausar o reanudar la ejecución; `false` para impedir que el servicio se pause y se reanude.|  
    |<xref:System.ServiceProcess.ServiceBase.CanHandlePowerEvent%2A>|`True` para indicar que el servicio puede controlar la notificación de cambios en el estado de energía del equipo; `false` para impedir que el servicio de notificación de estos cambios.|  
    |<xref:System.ServiceProcess.ServiceBase.AutoLog%2A>|`True` para escribir entradas informativas en el registro de sucesos de aplicación cuando el servicio realice una acción; `false` para deshabilitar esta funcionalidad. Para obtener más información, consulte [Cómo: obtener información acerca de servicios de registro](../../../docs/framework/windows-services/how-to-log-information-about-services.md). **Nota:** de forma predeterminada, <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> está establecido en `true`.|  
  
    > [!NOTE]
    >  Cuando <xref:System.ServiceProcess.ServiceBase.CanStop%2A> o <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> se establecen en `false`, **Service Control Manager** deshabilitará las opciones de menú correspondientes para detener, pausar o reanudar el servicio.  
  
4.  Obtenga acceso al Editor de código y rellene el procesamiento que desee para los procedimientos <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y <xref:System.ServiceProcess.ServiceBase.OnStop%2A>.  
  
5.  Reemplace los otros métodos para los que desee definir la funcionalidad.  
  
6.  Agregar los instaladores necesarios para su aplicación de servicio. Para obtener más información, consulte [Cómo: agregar instaladores a la aplicación de servicio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
7.  Compilar el proyecto seleccionando **generar solución** desde el **generar** menú.  
  
    > [!NOTE]
    >  No presione F5 para ejecutar el proyecto: no se puede ejecutar un proyecto de servicio de esta manera.  
  
8.  Instale el servicio. Para obtener más información, consulta [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).  
  
## <a name="see-also"></a>Vea también  
 [Introducción a las aplicaciones de servicios de Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Creación de servicios mediante programación](../../../docs/framework/windows-services/how-to-write-services-programmatically.md)  
 [Adición de instaladores a una aplicación de servicio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [Registro de información sobre servicios](../../../docs/framework/windows-services/how-to-log-information-about-services.md)  
 [Inicio de servicios](../../../docs/framework/windows-services/how-to-start-services.md)  
 [Definición del contexto de seguridad de los servicios](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)  
 [Instalación y desinstalación de servicios](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)  
 [Tutorial: Creación de una aplicación de servicios de Windows en el Diseñador de componentes](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)

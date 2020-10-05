---
title: Procedimiento para crear servicios de Windows
description: Use la plantilla de proyecto Servicio de Windows para crear un servicio. Establezca la propiedad ServiceName, cree instaladores e invalide los métodos OnStart y OnStop.
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, creating
- templates, Windows Service
ms.assetid: 0f5e2cbb-d95d-477c-b2b5-4b990e6b86ff
ms.openlocfilehash: 35d78acd4fae7bf98a2b3f4ce6ac8a32393c35d4
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "91608600"
---
# <a name="how-to-create-windows-services"></a>Procedimiento para crear servicios de Windows
Al crear un servicio, puede usar una plantilla de proyecto de Visual Studio denominada **Servicio de Windows**. Esta plantilla realiza automáticamente gran parte del trabajo: hace referencia a las clases y los espacios de nombres correctos, configura la herencia de la clase base para los servicios y reemplazar algunos de los métodos que es probable que desee reemplazar.  
  
> [!WARNING]
> La plantilla de proyecto Servicios de Windows no está disponible en la edición Express de Visual Studio.  
  
 Como mínimo, para crear un servicio funcional, deberá:  
  
- Establecer la propiedad <xref:System.ServiceProcess.ServiceBase.ServiceName%2A>.  
  
- Crear los instaladores necesarios para la aplicación de servicio.  
  
- Reemplazar y especificar el código para los métodos <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y <xref:System.ServiceProcess.ServiceBase.OnStop%2A> para personalizar el modo en que se comporta el servicio.  
  
### <a name="to-create-a-windows-service-application"></a>Para crear una aplicación de servicio de Windows  
  
1. Cree un proyecto de **Servicio Windows**.  
  
    > [!NOTE]
    > Para obtener instrucciones sobre cómo escribir un servicio sin usar la plantilla, vea [Cómo: Escribir servicios mediante programación](how-to-write-services-programmatically.md).  
  
2. En la ventana **Propiedades**, establezca la propiedad <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> para el servicio.  
  
     ![Establezca la propiedad ServiceName.](./media/windowsservice-servicename.PNG "WindowsService_ServiceName")  
  
    > [!NOTE]
    > El valor de la propiedad <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> siempre debe coincidir con el nombre registrado en las clases del instalador. Si cambia esta propiedad, también debe actualizar la propiedad <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> de las clases del instalador.  
  
3. Establezca cualquiera de las siguientes propiedades para determinar cómo funcionará el servicio.  
  
    |Propiedad.|Parámetro|  
    |--------------|-------------|  
    |<xref:System.ServiceProcess.ServiceBase.CanStop%2A>|`True` para indicar que el servicio aceptará solicitudes para detener la ejecución; `false` para impedir que el servicio se detenga.|  
    |<xref:System.ServiceProcess.ServiceBase.CanShutdown%2A>|`True` para indicar que el servicio desea recibir una notificación cuando se apaga el equipo en que reside, lo que le permite llamar al procedimiento <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>.|  
    |<xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A>|`True` para indicar que el servicio aceptará solicitudes para pausar o reanudar la ejecución; `false` para impedir que el servicio se pause y se reanude.|  
    |<xref:System.ServiceProcess.ServiceBase.CanHandlePowerEvent%2A>|`True` para indicar que el servicio puede controlar la notificación de cambios en el estado de alimentación del equipo; `false` para impedir la notificación al servicio de estos cambios.|  
    |<xref:System.ServiceProcess.ServiceBase.AutoLog%2A>|`True` para escribir entradas informativas en el registro de sucesos de aplicación cuando el servicio realice una acción; `false` para deshabilitar esta funcionalidad. Para obtener más información, vea [Cómo: Registrar información sobre servicios](how-to-log-information-about-services.md). **Nota:**  De manera predeterminada, <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> se establece en `true`.|  
  
    > [!NOTE]
    > Cuando <xref:System.ServiceProcess.ServiceBase.CanStop%2A> o <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> se establecen en `false`, el **Administrador de control de servicios** deshabilitará las opciones de menú correspondientes para detener, pausar o continuar el servicio.  
  
4. Obtenga acceso al Editor de código y rellene el procesamiento que desee para los procedimientos <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y <xref:System.ServiceProcess.ServiceBase.OnStop%2A>.  
  
5. Reemplace los otros métodos para los que desee definir la funcionalidad.  
  
6. Agregar los instaladores necesarios para su aplicación de servicio. Para obtener más información, vea [Cómo: Agregar instaladores a una aplicación de servicio](how-to-add-installers-to-your-service-application.md).  
  
7. En el menú **Compilar**, seleccione **Compilar solución** para compilar el proyecto.  
  
    > [!NOTE]
    > No presione F5 para ejecutar el proyecto: no se puede ejecutar un proyecto de servicio de esta manera.  
  
8. Instale el servicio. Para obtener más información, vea [Cómo: Instalar y desinstalar servicios](how-to-install-and-uninstall-services.md).  
  
## <a name="see-also"></a>Vea también

- [Introducción a las aplicaciones de servicios de Windows](introduction-to-windows-service-applications.md)
- [Cómo: Escribir servicios mediante programación](how-to-write-services-programmatically.md)
- [Cómo: Adición de instaladores a una aplicación de servicio](how-to-add-installers-to-your-service-application.md)
- [Cómo: Registrar información sobre servicios](how-to-log-information-about-services.md)
- [Cómo: Iniciar servicios](how-to-start-services.md)
- [Cómo: Especificar el contexto de seguridad de los servicios](how-to-specify-the-security-context-for-services.md)
- [Cómo: Instalar y desinstalar servicios](how-to-install-and-uninstall-services.md)
- [Tutorial: Creación de una aplicación de servicios de Windows en el Diseñador de componentes](walkthrough-creating-a-windows-service-application-in-the-component-designer.md)

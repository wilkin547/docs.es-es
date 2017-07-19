---
title: "How to: Start Services | Microsoft Docs"
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
  - "Windows Service applications, starting"
  - "services, starting"
ms.assetid: 9ea77955-2d96-4c3d-913c-14db7604cdad
caps.latest.revision: 16
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 14
---
# How to: Start Services
Una vez instalado el servicio, es necesario iniciarlo.  El proceso de inicio llama al método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> de la clase de servicio.  Normalmente, el método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> define el trabajo útil que realizará el servicio.  Después de iniciado un servicio, éste permanece activo hasta que se hace una pausa o se detiene manualmente.  
  
 Es posible configurar los servicios para que se inicien automática o manualmente.  Un servicio que se inicia automáticamente se inicia cuando el equipo en el que está instalado se reinicia o se activa por primera vez.  Los servicios que se inician manualmente deben ser iniciados por un usuario.  
  
> [!NOTE]
>  De forma predeterminada, los servicios creados con [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] se establecen para iniciarse manualmente.  
  
 Hay varias formas de iniciar manualmente un servicio: desde el **Explorador de servidores**, desde el **Administrador de control de servicios** o desde el código mediante un componente denominado <xref:System.ServiceProcess.ServiceController>.  
  
 Establezca la propiedad <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> de la clase <xref:System.ServiceProcess.ServiceInstaller> para determinar si un servicio debe iniciarse de forma manual o automática.  
  
### Para especificar cómo debe iniciarse un servicio  
  
1.  Después de crear el servicio, agregue los instaladores necesarios para él.  Para obtener más información, vea [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
2.  En el diseñador, haga clic en el instalador de servicio correspondiente al servicio con el que está trabajando.  
  
3.  En la ventana **Propiedades**, establezca la propiedad <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> en uno de los valores siguientes:  
  
    |Para hacer que el servicio se instale|Establezca este valor|  
    |-------------------------------------------|---------------------------|  
    |Al reiniciar el equipo|**Automático**|  
    |Cuando una acción explícita del usuario inicie el servicio|**Manual**|  
  
    > [!TIP]
    >  Para evitar que el servicio se inicie, puede establecer la propiedad <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> en **Deshabilitada**.  Puede hacer esto si va a reiniciar un servidor varias veces y desea ahorrar tiempo evitando que se inicien los servicios que lo harían normalmente.  
  
    > [!NOTE]
    >  Esta propiedad y otras se pueden cambiar después de instalar el servicio.  
  
     Existen varias formas en las que puede iniciar un servicio que tenga su proceso de <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> establecido en **Manual**; desde el **Explorador de servidores**, desde el **Administrador de control de servicios de Windows** o a partir de código.  Es importante observar que no todos estos métodos realmente inician el servicio en el contexto del **Administrador de control de servicios**; el **Explorador de servidores** y los métodos de inicio mediante programación del servicio manipulan realmente el controlador.  
  
### Para iniciar manualmente un servicio desde el Explorador de servidores  
  
1.  En el **Explorador de servidores**, agregue el servidor que desea si no aparece en la lista.  Para obtener más información, vea [How to: Access and Initialize Server Explorer\/Database Explorer](../Topic/How%20to:%20Access%20and%20Initialize%20Server%20Explorer-Database%20Explorer.md).  
  
2.  Expanda el nodo **Servicios** y, a continuación, busque el servicio que desee iniciar.  
  
3.  Haga clic con el botón secundario del mouse en el nombre del servicio y, a continuación, haga clic en **Iniciar**.  
  
### Para iniciar manualmente un servicio desde el Administrador de control de servicios  
  
1.  Abra el **Administrador de control de servicios** usando uno de los siguientes métodos:  
  
    -   En Windows XP y 2000 Professional, haga clic con el botón secundario del mouse en **Mi PC** en el escritorio y, a continuación, haga clic en **Administrar**.  En el cuadro de diálogo que aparece, expanda el nodo **Servicios y aplicaciones**.  
  
         O bien  
  
    -   En Windows Server 2003 y Windows 2000 Server, haga clic en **Inicio**, elija **Programas**, haga clic en **Herramientas administrativas** y, a continuación, en **Servicios**.  
  
        > [!NOTE]
        >  En Windows NT versión 4.0, puede abrir este cuadro de diálogo desde el **Panel de control**.  
  
     Podrá ver el servicio en la lista de la sección **Servicios** de la ventana.  
  
2.  Seleccione su servicio en la lista, haga clic en él con el botón secundario y luego haga clic en **Iniciar**.  
  
### Para iniciar un servicio manualmente desde el código  
  
1.  Cree una instancia de la clase <xref:System.ServiceProcess.ServiceController> y configúrela para que interactúe con el servicio que desea administrar.  
  
2.  Llame al método <xref:System.ServiceProcess.ServiceController.Start%2A> para iniciar el servicio.  
  
## Vea también  
 [Introduction to Windows Service Applications](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)   
 [How to: Create Windows Services](../../../docs/framework/windows-services/how-to-create-windows-services.md)   
 [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)   
 [How to: Access and Initialize Server Explorer\/Database Explorer](../Topic/How%20to:%20Access%20and%20Initialize%20Server%20Explorer-Database%20Explorer.md)
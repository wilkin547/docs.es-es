---
title: "How to: Add Installers to Your Service Application | Microsoft Docs"
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
  - "Windows Service applications, deploying"
  - "installation components, adding to services"
  - "installers, adding to services"
  - "Windows Service applications, adding installers"
  - "services, adding installers"
  - "ServiceInstaller class, adding installers to services"
  - "ServiceProcessInstaller class, adding installers to services"
ms.assetid: 8b698e9a-b88e-4f44-ae45-e0c5ea0ae5a8
caps.latest.revision: 14
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 14
---
# How to: Add Installers to Your Service Application
Visual Studio incluye componentes de instalación que pueden instalar recursos asociados a las aplicaciones de servicios.  Los componentes de instalación registran un servicio individual en el sistema en el que se está instalando y permiten que el Administrador de control de servicios conozca la existencia del servicio.  Cuando trabaje con una aplicación de servicios, puede seleccionar un vínculo de la ventana Propiedades para que agregue automáticamente al proyecto los instaladores adecuados.  
  
> [!NOTE]
>  Los valores de propiedad para el servicio se copian desde la clase de servicio a la clase del instalador.  Si actualiza los valores de propiedad en la clase de servicio, no se actualizarán automáticamente en el instalador.  
  
 Cuando se agrega un instalador al proyecto, se crea una nueva clase \(que se denomina, de forma predeterminada, `ProjectInstaller`\) en el proyecto y, dentro de él, se crearán instancias de los componentes de instalación adecuados.  Esta clase actúa como punto de referencia para todos los componentes de instalación que necesita el proyecto.  Por ejemplo, si agrega un segundo servicio a la aplicación y hace clic en el vínculo Agregar instalador, no se creará una segunda clase del instalador; en su lugar, se agregará a la clase existente el componente de instalación adicional necesario para el segundo servicio.  
  
 No necesitará escribir ningún código especial dentro de los instaladores para hacer que los servicios se instalen correctamente.  Sin embargo, en ocasiones necesitará modificar el contenido de los instaladores si necesita agregar funcionalidad especial al proceso de instalación.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para agregar instaladores a una aplicación de servicio  
  
1.  En el **Explorador de soluciones**, obtenga acceso a la **Vista Diseño** del servicio para el que desee agregar un componente de instalación.  
  
2.  Haga clic en el fondo del diseñador para seleccionar el propio servicio, en vez de cualquier elemento de su contenido.  
  
3.  Con el foco en el diseñador, haga clic con el botón secundario del mouse y, a continuación, haga clic en **Agregar instalador**.  
  
     Se agregará al proyecto una nueva clase `ProjectInstaller` y dos componentes de instalación, <xref:System.ServiceProcess.ServiceProcessInstaller> y <xref:System.ServiceProcess.ServiceInstaller> así como los valores de propiedad del servicio se copiarán en los componentes.  
  
4.  Haga clic en el componente <xref:System.ServiceProcess.ServiceInstaller> y compruebe que el valor de la propiedad <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> esté establecido en el mismo valor que la propiedad <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> del servicio.  
  
5.  Para determinar cómo se iniciará el servicio, haga clic en el componente <xref:System.ServiceProcess.ServiceInstaller> y establezca la propiedad <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> en el valor adecuado.  
  
    |Valor|Resultado|  
    |-----------|---------------|  
    |<xref:System.ServiceProcess.ServiceStartMode>|El servicio deberá iniciarse manualmente después de la instalación.  Para obtener más información, vea [How to: Start Services](../../../docs/framework/windows-services/how-to-start-services.md).|  
    |<xref:System.ServiceProcess.ServiceStartMode>|El servicio se iniciará por sí solo siempre que se reinicie el equipo.|  
    |<xref:System.ServiceProcess.ServiceStartMode>|El servicio no se puede iniciar.|  
  
6.  Para determinar el contexto de seguridad en el que se ejecutará el servicio, haga clic en el componente <xref:System.ServiceProcess.ServiceProcessInstaller> y establezca los valores de propiedad adecuados.  Para obtener más información, vea [How to: Specify the Security Context for Services](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md).  
  
7.  Reemplace los métodos para los que necesite ejecutar procesos personalizados.  
  
8.  Ejecute los pasos 1 a 7 para cada servicio adicional del proyecto.  
  
    > [!NOTE]
    >  Para cada servicio adicional del proyecto, deberá agregar un componente <xref:System.ServiceProcess.ServiceInstaller> adicional a la clase `ProjectInstaller`.  El componente <xref:System.ServiceProcess.ServiceProcessInstaller>, agregado en el paso tres, funciona con todos los instaladores de servicios individuales del proyecto.  
  
## Vea también  
 [Introduction to Windows Service Applications](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)   
 [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)   
 [How to: Start Services](../../../docs/framework/windows-services/how-to-start-services.md)   
 [How to: Specify the Security Context for Services](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)
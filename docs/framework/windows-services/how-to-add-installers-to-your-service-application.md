---
title: "Cómo: Agregar instaladores a una aplicación de servicio"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, deploying
- installation components, adding to services
- installers, adding to services
- Windows Service applications, adding installers
- services, adding installers
- ServiceInstaller class, adding installers to services
- ServiceProcessInstaller class, adding installers to services
ms.assetid: 8b698e9a-b88e-4f44-ae45-e0c5ea0ae5a8
caps.latest.revision: "14"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 8137e41f92335849916dfc9e9ce72afeb186e73c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-installers-to-your-service-application"></a>Cómo: Agregar instaladores a una aplicación de servicio
Visual Studio incluye componentes de instalación que pueden instalar recursos asociados con las aplicaciones de servicio. Componentes de instalación registran un servicio individual en el sistema al que se va a instalar y que el Administrador de Control de servicios sepan que existe el servicio. Cuando se trabaja con una aplicación de servicio, puede seleccionar un vínculo en la ventana Propiedades para agregar automáticamente los instaladores adecuados al proyecto.  
  
> [!NOTE]
>  Los valores de propiedad para el servicio se copian de la clase de servicio a la clase del instalador. Si actualiza los valores de propiedad en la clase de servicio, no se actualizan automáticamente en el programa de instalación.  
  
 Al agregar un instalador al proyecto, una nueva clase (que, de forma predeterminada, se denomina `ProjectInstaller`) se crea en el proyecto y las instancias de la instalación adecuada componentes se crean dentro de él. Esta clase actúa como punto central para todos los componentes de instalación de su proyecto necesite. Por ejemplo, si agrega un segundo servicio a la aplicación y haga clic en el vínculo Agregar instalador, no se crea una segunda clase del instalador; en su lugar, el componente de instalación adicional necesario para el segundo servicio se agrega a la clase existente.  
  
 No es necesario hacer ninguna codificación especial dentro de los instaladores para hacer que los servicios se instale correctamente. Sin embargo, en ocasiones, necesite modificar el contenido de los instaladores si necesita agregar funcionalidad especial al proceso de instalación.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-add-installers-to-your-service-application"></a>Para agregar a instaladores a la aplicación de servicio  
  
1.  En **el Explorador de soluciones**, acceso **diseño** vista para el servicio para el que desea agregar un componente de instalación.  
  
2.  Haga clic en el fondo del diseñador para seleccionar el servicio de sí mismo, en lugar de su contenido.  
  
3.  Con el diseñador en foco, el menú contextual y, a continuación, haga clic en **Agregar instalador**.  
  
     Una nueva clase, `ProjectInstaller`y dos componentes de instalación, <xref:System.ServiceProcess.ServiceProcessInstaller> y <xref:System.ServiceProcess.ServiceInstaller>, se agregan a su proyecto y los valores de propiedad para el servicio se copian en los componentes.  
  
4.  Haga clic en el <xref:System.ServiceProcess.ServiceInstaller> componente y compruebe que el valor de la <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> propiedad se establece en el mismo valor que el <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> propiedad en el propio servicio.  
  
5.  Para determinar cómo se iniciará el servicio, haga clic en el <xref:System.ServiceProcess.ServiceInstaller> componente y establezca el <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> propiedad en el valor adecuado.  
  
    |Valor|Resultado|  
    |-----------|------------|  
    |<xref:System.ServiceProcess.ServiceStartMode.Manual>|El servicio debe iniciarse manualmente después de la instalación. Para obtener más información, consulte [Cómo: iniciar servicios](../../../docs/framework/windows-services/how-to-start-services.md).|  
    |<xref:System.ServiceProcess.ServiceStartMode.Automatic>|El servicio se iniciará por sí mismo cada vez que el equipo se reinicia.|  
    |<xref:System.ServiceProcess.ServiceStartMode.Disabled>|No se puede iniciar el servicio.|  
  
6.  Para determinar el contexto de seguridad en el que se ejecutará el servicio, haga clic en el <xref:System.ServiceProcess.ServiceProcessInstaller> componente y establezca los valores de propiedad correspondiente. Para obtener más información, consulte [Cómo: especificar el contexto de seguridad para los servicios](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md).  
  
7.  Reemplace los métodos para la que necesita realizar el procesamiento personalizado.  
  
8.  Realice los pasos del 1 al 7 para cada servicio adicional en el proyecto.  
  
    > [!NOTE]
    >  Para cada servicio adicional en el proyecto, debe agregar otro <xref:System.ServiceProcess.ServiceInstaller> componente para el proyecto `ProjectInstaller` clase. El <xref:System.ServiceProcess.ServiceProcessInstaller> el componente se agregó en el paso tres funciona con todos los instaladores de servicio individuales en el proyecto.  
  
## <a name="see-also"></a>Vea también  
 [Introducción a las aplicaciones de servicio de Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Cómo: instalar y desinstalar servicios](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)  
 [Cómo: iniciar servicios](../../../docs/framework/windows-services/how-to-start-services.md)  
 [Cómo: especificar el contexto de seguridad para los servicios](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)

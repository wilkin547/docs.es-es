---
title: Procedimiento para agregar instaladores a una aplicación de servicio
description: Vea cómo agregar instaladores a la aplicación de servicio. Visual Studio incluye componentes de instalación que pueden instalar recursos asociados a una aplicación de servicio.
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, deploying
- installation components, adding to services
- installers, adding to services
- Windows Service applications, adding installers
- services, adding installers
- ServiceInstaller class, adding installers to services
- ServiceProcessInstaller class, adding installers to services
ms.assetid: 8b698e9a-b88e-4f44-ae45-e0c5ea0ae5a8
author: ghogen
ms.openlocfilehash: f82dd6635555ccb8fcbcdf63cba2495084194731
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925649"
---
# <a name="how-to-add-installers-to-your-service-application"></a>Procedimiento para agregar instaladores a una aplicación de servicio
Visual Studio incluye componentes de instalación que pueden instalar recursos asociados con sus aplicaciones de servicios. Los componentes de la instalación registran un servicio individual en el sistema en el que se está instalando e informan al Administrador de control de servicios que el servicio existe. Cuando trabaje con una aplicación de servicio, puede seleccionar un vínculo en la ventana Propiedades para agregar automáticamente los instaladores apropiados a su proyecto.  
  
> [!NOTE]
> Los valores de propiedad de su servicio se copian de la clase de servicio a la clase de instalador. Si actualiza los valores de las propiedades en la clase de servicio, no se actualizan automáticamente en el instalador.  
  
 Cuando agrega un instalador a su proyecto, se crea una nueva clase (que, de forma predeterminada, se llama `ProjectInstaller`) en el proyecto, y se crean instancias de los componentes de instalación apropiados dentro de él. Esta clase actúa como un punto central para todos los componentes de instalación que el proyecto necesita. Por ejemplo, si agrega un segundo servicio a la aplicación y hace clic en el vínculo Agregar instalador, no se creará una segunda clase de instalador; en su lugar, el componente de instalación adicional necesario para el segundo servicio se agregará a la clase existente.  
  
 No necesita hacer ninguna codificación especial dentro de los instaladores para que los servicios se instalen correctamente. Sin embargo, es posible que ocasionalmente tenga que modificar el contenido de los instaladores si necesita agregar funciones especiales al proceso de instalación.  
  
> [!NOTE]
> Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-installers-to-your-service-application"></a>Para agregar instaladores a la aplicación de servicio  
  
1. En el **Explorador de soluciones**, acceda a la vista **Diseño** del servicio para el que desea agregar un componente de instalación.  
  
2. Haga clic en el fondo del diseñador para seleccionar el propio servicio, en vez de cualquier elemento de su contenido.  
  
3. Con el foco en el diseñador, haga clic con el botón derecho y, a continuación, haga clic en **Agregar instalador**.  
  
     Una nueva clase, `ProjectInstaller` y dos componentes de instalación, <xref:System.ServiceProcess.ServiceProcessInstaller> y <xref:System.ServiceProcess.ServiceInstaller>, se agregan al proyecto, y los valores de propiedad del servicio se copian a los componentes.  
  
4. Haga clic en el componente <xref:System.ServiceProcess.ServiceInstaller> y compruebe que el valor de la propiedad <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> es el mismo que el de la propiedad <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> del propio servicio.  
  
5. Para determinar cómo se iniciará el servicio, haga clic en el componente <xref:System.ServiceProcess.ServiceInstaller> y establezca la propiedad <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> en el valor adecuado.  
  
    |Valor|Resultado|  
    |-----------|------------|  
    |<xref:System.ServiceProcess.ServiceStartMode.Manual>|El servicio debe iniciarse manualmente después de la instalación. Para obtener más información, vea [Cómo: Iniciar servicios](how-to-start-services.md).|  
    |<xref:System.ServiceProcess.ServiceStartMode.Automatic>|El servicio se iniciará por sí mismo cada vez que el equipo se reinicia.|  
    |<xref:System.ServiceProcess.ServiceStartMode.Disabled>|No se puede iniciar el servicio.|  
  
6. Para determinar el contexto de seguridad en el que se ejecutará el servicio, haga clic en el componente <xref:System.ServiceProcess.ServiceProcessInstaller> y establezca los valores de propiedad adecuados. Para obtener más información, vea [Cómo: Especificar el contexto de seguridad de los servicios](how-to-specify-the-security-context-for-services.md).  
  
7. Sustituya cualquier método para el que necesite realizar un procesamiento personalizado.  
  
8. Realice los pasos del 1 al 7 para cada servicio adicional en el proyecto.  
  
    > [!NOTE]
    > Por cada servicio adicional en el proyecto, debe agregar un componente adicional <xref:System.ServiceProcess.ServiceInstaller> a la clase `ProjectInstaller` del proyecto. El componente <xref:System.ServiceProcess.ServiceProcessInstaller> agregado en el paso tres funciona con todos los instaladores de servicio individuales del proyecto.  
  
## <a name="see-also"></a>Vea también

- [Introducción a las aplicaciones de servicios de Windows](introduction-to-windows-service-applications.md)
- [Cómo: Instalar y desinstalar servicios](how-to-install-and-uninstall-services.md)
- [Cómo: Iniciar servicios](how-to-start-services.md)
- [Cómo: Especificar el contexto de seguridad de los servicios](how-to-specify-the-security-context-for-services.md)

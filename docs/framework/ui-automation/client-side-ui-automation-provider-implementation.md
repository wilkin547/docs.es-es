---
title: Implementación del proveedor de UI Automation en el cliente
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, client-side provider implementation
- client-side UI Automation provider, implementation
- provider implementation, UI Automation
ms.assetid: 3584c0a1-9cd0-4968-8b63-b06390890ef6
ms.openlocfilehash: 50d7921f1c63580248b562864f9c1f398d41c9bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180256"
---
# <a name="client-side-ui-automation-provider-implementation"></a>Implementación del proveedor de UI Automation en el cliente
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 Varios [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] marcos diferentes están en uso dentro de los sistemas operativos de Microsoft, incluidos Win32, Windows Forms y [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)]. [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] expone información sobre los elementos de interfaz de usuario a los clientes. Sin embargo, el propio [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] no tiene conocimiento de los diferentes tipos de controles que existen en estos marcos de trabajo y las técnicas que se necesitan para extraen información de ellos. En su lugar, deja esta tarea a objetos denominados proveedores. Un proveedor extrae información de un control concreto y proporciona esa información a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], que luego la presenta al cliente de una manera coherente.  
  
 Los proveedores pueden existir en el lado servidor o en el lado cliente. El propio control implementa un proveedor de lado servidor. Los elementos[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] implementan proveedores, como pueden hacerlo los controles de terceros escritos teniendo en cuenta [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
 Sin embargo, los controles más antiguos, como los [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]de Win32 y Windows Forms, no admiten directamente . En su lugar, se sirven estos controles por los proveedores que existen en el proceso del cliente y obtienen información sobre los controles mediante la comunicación entre procesos; por ejemplo, al supervisar mensajes de ventana hacia y desde los controles. Estos proveedores del lado cliente a veces se denominan servidores proxy.  
  
 Windows Vista proporciona proveedores para controles estándar de Win32 y Windows Forms. Además, un proveedor [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] de reserva proporciona compatibilidad parcial a cualquier control que no sea servido por otro proveedor o proxy del lado servidor, pero que tenga una implementación de Microsoft Active Accessibility. Todos estos proveedores se cargan automáticamente y están disponibles para las aplicaciones cliente.  
  
 Para obtener más información sobre la compatibilidad con controles Win32 y Windows Forms, vea [Compatibilidad con automatización](ui-automation-support-for-standard-controls.md)de la interfaz de usuario para controles estándar .  
  
 Las aplicaciones también pueden registrar otros proveedores del lado cliente.  
  
<a name="Distributing_Client-Side_Providers"></a>
## <a name="distributing-client-side-providers"></a>Distribución de proveedores del cliente  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] espera encontrar proveedores del lado cliente en un ensamblado de código administrado. El espacio de nombres de este ensamblado debería tener el mismo nombre que el ensamblado. Por ejemplo, un ensamblado denominado ContosoProxies.dll contendría el espacio de nombres ContosoProxies. En el espacio de nombres, cree una clase <xref:UIAutomationClientsideProviders.UIAutomationClientSideProviders> . En la implementación del campo <xref:UIAutomationClientsideProviders.UIAutomationClientSideProviders.ClientSideProviderDescriptionTable> estático, cree una matriz de estructuras <xref:System.Windows.Automation.ClientSideProviderDescription> que describan los proveedores.  
  
<a name="Registering_and_Configuring_Client-Side_Providers"></a>
## <a name="registering-and-configuring-client-side-providers"></a>Registro y configuración de proveedores de lado de cliente  
 Los proveedores del lado cliente en una biblioteca <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviderAssembly%2A>de vínculos dinámicos (DLL) se cargan llamando a . No es necesario realizar ninguna acción por una aplicación cliente para usar los proveedores.  
  
 Los proveedores implementados en el propio código del cliente se registran mediante <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>. Este método toma como argumento una matriz de estructuras <xref:System.Windows.Automation.ClientSideProviderDescription> y cada una de ellas especifica las siguientes propiedades:  
  
- Una función de devolución de llamada que crea el objeto de proveedor.  
  
- El nombre de clase de los controles que suministrará el proveedor.  
  
- El nombre de la imagen de la aplicación (normalmente el nombre completo del archivo ejecutable) que suministrará el proveedor.  
  
- Marcas que rigen la manera en que el nombre de clase se compara con las clases de ventana que se encuentran en la aplicación de destino.  
  
 Los dos últimos parámetros son opcionales. El cliente puede especificar el nombre de la imagen de la aplicación de destino cuando quiera usar diferentes proveedores para distintas aplicaciones. Por ejemplo, el cliente podría usar un proveedor para un control de vista de lista Win32 en una aplicación conocida que admita el patrón de vista múltiple y otro para un control similar en otra aplicación conocida que no lo hace.  
  
## <a name="see-also"></a>Consulte también

- [Crear un proveedor de UI Automation en el cliente](create-a-client-side-ui-automation-provider.md)
- [Implementar proveedores de UI Automation en una aplicación cliente](implement-ui-automation-providers-in-a-client-application.md)

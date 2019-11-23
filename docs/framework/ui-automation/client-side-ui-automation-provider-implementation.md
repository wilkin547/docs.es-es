---
title: Implementación del proveedor de UI Automation en el cliente
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, client-side provider implementation
- client-side UI Automation provider, implementation
- provider implementation, UI Automation
ms.assetid: 3584c0a1-9cd0-4968-8b63-b06390890ef6
ms.openlocfilehash: 03df282022c39673a7e160dd5d79bdadd0c7adda
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433996"
---
# <a name="client-side-ui-automation-provider-implementation"></a>Implementación del proveedor de UI Automation en el cliente
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 Several different [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] frameworks are in use within Microsoft operating systems, including [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)], [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)], and [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)]. [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] expone información sobre los elementos de interfaz de usuario a los clientes. Sin embargo, el propio [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] no tiene conocimiento de los diferentes tipos de controles que existen en estos marcos de trabajo y las técnicas que se necesitan para extraen información de ellos. En su lugar, deja esta tarea a objetos denominados proveedores. Un proveedor extrae información de un control concreto y proporciona esa información a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], que luego la presenta al cliente de una manera coherente.  
  
 Los proveedores pueden existir en el lado servidor o en el lado cliente. El propio control implementa un proveedor de lado servidor. Los elementos[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] implementan proveedores, como pueden hacerlo los controles de terceros escritos teniendo en cuenta [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
 Sin embargo, los controles más antiguos como los de [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] y [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] no admiten directamente [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. En su lugar, se sirven estos controles por los proveedores que existen en el proceso del cliente y obtienen información sobre los controles mediante la comunicación entre procesos; por ejemplo, al supervisar mensajes de ventana hacia y desde los controles. Estos proveedores del lado cliente a veces se denominan servidores proxy.  
  
 Windows Vista supplies providers for standard [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] and Windows Forms controls. In addition, a fallback provider gives partial [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] support to any control that is not served by another server-side provider or proxy but has a Microsoft Active Accessibility implementation. Todos estos proveedores se cargan automáticamente y están disponibles para las aplicaciones cliente.  
  
 For more information on support for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] and Windows Forms controls, see [UI Automation Support for Standard Controls](ui-automation-support-for-standard-controls.md).  
  
 Las aplicaciones también pueden registrar otros proveedores del lado cliente.  
  
<a name="Distributing_Client-Side_Providers"></a>   
## <a name="distributing-client-side-providers"></a>Distribución de proveedores del cliente  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] espera encontrar proveedores del lado cliente en un ensamblado de código administrado. El espacio de nombres de este ensamblado debería tener el mismo nombre que el ensamblado. Por ejemplo, un ensamblado denominado ContosoProxies.dll contendría el espacio de nombres ContosoProxies. En el espacio de nombres, cree una clase <xref:UIAutomationClientsideProviders.UIAutomationClientSideProviders> . En la implementación del campo <xref:UIAutomationClientsideProviders.UIAutomationClientSideProviders.ClientSideProviderDescriptionTable> estático, cree una matriz de estructuras <xref:System.Windows.Automation.ClientSideProviderDescription> que describan los proveedores.  
  
<a name="Registering_and_Configuring_Client-Side_Providers"></a>   
## <a name="registering-and-configuring-client-side-providers"></a>Registro y configuración de proveedores de lado de cliente  
 Client-side providers in a dynamic-link library (DLL) are loaded by calling <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviderAssembly%2A>. No es necesario realizar ninguna acción por una aplicación cliente para usar los proveedores.  
  
 Los proveedores implementados en el propio código del cliente se registran mediante <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>. Este método toma como argumento una matriz de estructuras <xref:System.Windows.Automation.ClientSideProviderDescription> y cada una de ellas especifica las siguientes propiedades:  
  
- Una función de devolución de llamada que crea el objeto de proveedor.  
  
- El nombre de clase de los controles que suministrará el proveedor.  
  
- El nombre de la imagen de la aplicación (normalmente el nombre completo del archivo ejecutable) que suministrará el proveedor.  
  
- Marcas que rigen la manera en que el nombre de clase se compara con las clases de ventana que se encuentran en la aplicación de destino.  
  
 Los dos últimos parámetros son opcionales. El cliente puede especificar el nombre de la imagen de la aplicación de destino cuando quiera usar diferentes proveedores para distintas aplicaciones. Por ejemplo, el cliente puede usar un proveedor para un control de vista de lista [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] de una aplicación conocida que admita el patrón de vista múltiple y otro para un control similar de otra aplicación conocida que no lo hace.  
  
## <a name="see-also"></a>Vea también

- [Creación de un proveedor de Automatización de la interfaz de usuario en el cliente](create-a-client-side-ui-automation-provider.md)
- [Implementación de proveedores de Automatización de la interfaz de usuario en una aplicación cliente](implement-ui-automation-providers-in-a-client-application.md)

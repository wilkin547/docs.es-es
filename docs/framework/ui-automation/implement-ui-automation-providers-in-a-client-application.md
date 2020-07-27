---
title: Implementar proveedores de UI Automation en una aplicación cliente
description: Vea un ejemplo de cómo implementar un proveedor de automatización de la interfaz de usuario del lado cliente en una aplicación. Tenga en cuenta que se trata de un escenario poco frecuente.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- client-side UI Automation provider, implementation within applications
- UI Automation, implementing client-side provider within application
ms.assetid: f325f0d8-1715-41ea-85ca-45b82ffea8bc
ms.openlocfilehash: c604b68021886abdf06360bfb8afefe3640c12fe
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164125"
---
# <a name="implement-ui-automation-providers-in-a-client-application"></a>Implementar proveedores de UI Automation en una aplicación cliente
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 Este tema contiene código de ejemplo que muestra cómo implementar un proveedor de Automatización de la interfaz de usuario del lado cliente dentro de una aplicación.  
  
 Se trata de un escenario poco común. A menudo, una aplicación cliente de Automatización de la interfaz de usuario utiliza proveedores del lado servidor o proveedores del lado cliente que residen en un archivo DLL.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente implementa un proveedor simple para una ventana de consola. El código no tiene ninguna funcionalidad práctica, pero está pensado para mostrar los pasos básicos para configurar un proveedor dentro de código de cliente y registrarlo mediante <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>.  
  
 [!code-csharp[UIAClientSideProvider_snip#201](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/ClientImplementationProgram.cs#201)]
 [!code-vb[UIAClientSideProvider_snip#201](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/clientimplementationprogram.vb#201)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre proveedores de UI Automation](ui-automation-providers-overview.md)
- [Registrar un ensamblado de proveedor de cliente](register-a-client-side-provider-assembly.md)
- [Crear un proveedor de UI Automation en el cliente](create-a-client-side-ui-automation-provider.md)
- [Implementación del proveedor de UI Automation en el cliente](client-side-ui-automation-provider-implementation.md)

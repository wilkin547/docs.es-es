---
title: Implementar proveedores de UI Automation en una aplicación cliente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- client-side UI Automation provider, implementation within applications
- UI Automation, implementing client-side provider within application
ms.assetid: f325f0d8-1715-41ea-85ca-45b82ffea8bc
ms.openlocfilehash: b368ab3bc842fda5a99a64e0220093ebd60698b0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105929"
---
# <a name="implement-ui-automation-providers-in-a-client-application"></a>Implementar proveedores de UI Automation en una aplicación cliente
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: Automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Este tema contiene código de ejemplo que muestra cómo implementar un proveedor de Automatización de la interfaz de usuario del lado cliente dentro de una aplicación.  
  
 Se trata de un escenario poco común. A menudo, una aplicación cliente de Automatización de la interfaz de usuario utiliza proveedores del lado servidor o proveedores del lado cliente que residen en un archivo DLL.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente implementa un proveedor simple para una ventana de consola. El código no tiene ninguna funcionalidad práctica, pero está pensado para mostrar los pasos básicos para configurar un proveedor dentro de código de cliente y registrarlo mediante <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>.  
  
 [!code-csharp[UIAClientSideProvider_snip#201](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/ClientImplementationProgram.cs#201)]
 [!code-vb[UIAClientSideProvider_snip#201](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/clientimplementationprogram.vb#201)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre proveedores de UI Automation](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
- [Registrar un ensamblado de proveedor de cliente](../../../docs/framework/ui-automation/register-a-client-side-provider-assembly.md)
- [Crear un proveedor de UI Automation en el cliente](../../../docs/framework/ui-automation/create-a-client-side-ui-automation-provider.md)
- [Implementación del proveedor de UI Automation en el cliente](../../../docs/framework/ui-automation/client-side-ui-automation-provider-implementation.md)

---
title: Crear un proveedor de UI Automation en el cliente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, creating client-side provider
- client-side UI Automation provider, creating
ms.assetid: d91edaf2-be28-41ec-a508-af421cb43c3d
ms.openlocfilehash: 03f64386271565b3494b9dac42cf969fc777e40b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211314"
---
# <a name="create-a-client-side-ui-automation-provider"></a>Crear un proveedor de UI Automation en el cliente
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: Automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Este tema contiene código de ejemplo que muestra cómo implementar un proveedor de Automatización de la interfaz de usuario del lado cliente.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente se puede compilar en un archivo [!INCLUDE[TLA#tla_dll](../../../includes/tlasharptla-dll-md.md)] que implemente un proveedor de cliente muy simple para una ventana de consola. El código no tiene ninguna funcionalidad práctica, pero está pensado para mostrar los pasos básicos para configurar un ensamblado de proveedor que se pueda registrar mediante una aplicación de cliente de Automatización de la interfaz de usuario.  
  
 [!code-csharp[UIAClientSideProvider_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSProviderProgram.cs#101)]
 [!code-vb[UIAClientSideProvider_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csproviderprogram.vb#101)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre proveedores de UI Automation](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
- [Registrar un ensamblado de proveedor de cliente](../../../docs/framework/ui-automation/register-a-client-side-provider-assembly.md)

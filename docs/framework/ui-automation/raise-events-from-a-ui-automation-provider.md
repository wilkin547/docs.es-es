---
title: Provocar eventos desde un proveedor de UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, raising events
- raising UI Automation events
ms.assetid: 9fe2f01b-f7d8-49a8-a185-d4472b9976c0
ms.openlocfilehash: c973d6ddba498f4bdab4be764a4be6bff1cacf9e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966373"
---
# <a name="raise-events-from-a-ui-automation-provider"></a>Provocar eventos desde un proveedor de UI Automation
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para obtener la información más [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]reciente acerca [de, consulte API de automatización de Windows: Automatización](https://go.microsoft.com/fwlink/?LinkID=156746)de la interfaz de usuario.  
  
 Este tema contiene código de ejemplo que muestra cómo desencadenar un evento desde un proveedor de Automatización de la interfaz de usuario.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, un evento de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] se genera en la implementación de un control de botón personalizado. La implementación permite a una aplicación cliente de Automatización de la interfaz de usuario simular un clic de botón.  
  
 Para evitar un procesamiento innecesario, el ejemplo comprueba <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> para ver si se deben generar eventos.  
  
 [!code-csharp[UIAProvider_snip#150](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAProvider_snip/CSharp/FragmentRoot.cs#150)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre proveedores de la Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)

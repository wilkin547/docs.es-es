---
title: Exponer un proveedor de UI Automation en el servidor
description: Vea un ejemplo que muestra cómo exponer un proveedor de automatización de la interfaz de usuario del lado servidor que se hospeda en una ventana System. Windows. Forms. control.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- expose a server-side UI Automation provider
- UI Automation, server-side provider, exposing
- server-side UI Automation provider, exposing
ms.assetid: 55d419c0-2201-4101-90c9-2888df4dbb47
ms.openlocfilehash: be39130c7a91fc081256bf14a87f503d27f45129
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276534"
---
# <a name="expose-a-server-side-ui-automation-provider"></a>Exponer un proveedor de UI Automation en el servidor

> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 Este tema contiene código de ejemplo que muestra cómo exponer un proveedor de automatización de interfaz de usuario del lado servidor que se hospeda en una ventana <xref:System.Windows.Forms.Control?displayProperty=nameWithType> .  
  
 El ejemplo invalida el procedimiento de ventana para interceptar WM_GETOBJECT, que es el mensaje enviado por el servicio principal [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] cuando una aplicación cliente solicita información sobre la ventana.  
  
## <a name="example"></a>Ejemplo  

 [!code-csharp[UIAFragmentProvider_snip#116](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#116)]
 [!code-vb[UIAFragmentProvider_snip#116](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#116)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre proveedores de UI Automation](ui-automation-providers-overview.md)
- [Implementación del proveedor de UI Automation en el servidor](server-side-ui-automation-provider-implementation.md)

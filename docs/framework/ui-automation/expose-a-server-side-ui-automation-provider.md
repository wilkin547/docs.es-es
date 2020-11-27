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
# <a name="expose-a-server-side-ui-automation-provider"></a><span data-ttu-id="56dbc-103">Exponer un proveedor de UI Automation en el servidor</span><span class="sxs-lookup"><span data-stu-id="56dbc-103">Expose a Server-side UI Automation Provider</span></span>

> [!NOTE]
> <span data-ttu-id="56dbc-104">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="56dbc-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="56dbc-105">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="56dbc-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="56dbc-106">Este tema contiene código de ejemplo que muestra cómo exponer un proveedor de automatización de interfaz de usuario del lado servidor que se hospeda en una ventana <xref:System.Windows.Forms.Control?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="56dbc-106">This topic contains example code that shows how to expose a server-side UI Automation provider that is hosted in a <xref:System.Windows.Forms.Control?displayProperty=nameWithType> window.</span></span>  
  
 <span data-ttu-id="56dbc-107">El ejemplo invalida el procedimiento de ventana para interceptar WM_GETOBJECT, que es el mensaje enviado por el servicio principal [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] cuando una aplicación cliente solicita información sobre la ventana.</span><span class="sxs-lookup"><span data-stu-id="56dbc-107">The example overrides the window procedure to trap WM_GETOBJECT, which is the message sent by the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] core service when a client application requests information about the window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56dbc-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="56dbc-108">Example</span></span>  

 [!code-csharp[UIAFragmentProvider_snip#116](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#116)]
 [!code-vb[UIAFragmentProvider_snip#116](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#116)]  
  
## <a name="see-also"></a><span data-ttu-id="56dbc-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="56dbc-109">See also</span></span>

- [<span data-ttu-id="56dbc-110">Información general sobre proveedores de UI Automation</span><span class="sxs-lookup"><span data-stu-id="56dbc-110">UI Automation Providers Overview</span></span>](ui-automation-providers-overview.md)
- [<span data-ttu-id="56dbc-111">Implementación del proveedor de UI Automation en el servidor</span><span class="sxs-lookup"><span data-stu-id="56dbc-111">Server-Side UI Automation Provider Implementation</span></span>](server-side-ui-automation-provider-implementation.md)

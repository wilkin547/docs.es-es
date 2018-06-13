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
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 5a391215bb03ca7af010e90443479848f05e4985
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403720"
---
# <a name="create-a-client-side-ui-automation-provider"></a><span data-ttu-id="6b791-102">Crear un proveedor de UI Automation en el cliente</span><span class="sxs-lookup"><span data-stu-id="6b791-102">Create a Client-Side UI Automation Provider</span></span>
> [!NOTE]
>  <span data-ttu-id="6b791-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="6b791-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="6b791-104">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="6b791-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="6b791-105">Este tema contiene código de ejemplo que muestra cómo implementar un proveedor de Automatización de la interfaz de usuario del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="6b791-105">This topic contains example code that shows how to implement a client-side UI Automation provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b791-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6b791-106">Example</span></span>  
 <span data-ttu-id="6b791-107">El ejemplo de código siguiente se puede compilar en un archivo [!INCLUDE[TLA#tla_dll](../../../includes/tlasharptla-dll-md.md)] que implemente un proveedor de cliente muy simple para una ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="6b791-107">The following example code can be built into a [!INCLUDE[TLA#tla_dll](../../../includes/tlasharptla-dll-md.md)] that implements a very simple client-side provider for a console window.</span></span> <span data-ttu-id="6b791-108">El código no tiene ninguna funcionalidad práctica, pero está pensado para mostrar los pasos básicos para configurar un ensamblado de proveedor que se pueda registrar mediante una aplicación de cliente de Automatización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="6b791-108">The code does not have any useful functionality, but is intended to demonstrate the basic steps in setting up a provider assembly that can be registered by a UI Automation client application.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSProviderProgram.cs#101)]
 [!code-vb[UIAClientSideProvider_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csproviderprogram.vb#101)]  
  
## <a name="see-also"></a><span data-ttu-id="6b791-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b791-109">See Also</span></span>  
 [<span data-ttu-id="6b791-110">Información general sobre proveedores de la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="6b791-110">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)  
 [<span data-ttu-id="6b791-111">Registro de un ensamblado de proveedor del lado cliente</span><span class="sxs-lookup"><span data-stu-id="6b791-111">Register a Client-Side Provider Assembly</span></span>](../../../docs/framework/ui-automation/register-a-client-side-provider-assembly.md)

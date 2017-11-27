---
title: "Implementar proveedores de UI Automation en una aplicación cliente"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- client-side UI Automation provider, implementation within applications
- UI Automation, implementing client-side provider within application
ms.assetid: f325f0d8-1715-41ea-85ca-45b82ffea8bc
caps.latest.revision: "6"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: ae7b478ec8d836f1e0772d81185b9bb0119c0fa8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="implement-ui-automation-providers-in-a-client-application"></a><span data-ttu-id="370c0-102">Implementar proveedores de UI Automation en una aplicación cliente</span><span class="sxs-lookup"><span data-stu-id="370c0-102">Implement UI Automation Providers in a Client Application</span></span>
> [!NOTE]
>  <span data-ttu-id="370c0-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="370c0-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="370c0-104">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="370c0-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="370c0-105">Este tema contiene código de ejemplo que muestra cómo implementar un proveedor de Automatización de la interfaz de usuario del lado cliente dentro de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="370c0-105">This topic contains example code that shows how to implement a client-side UI Automation provider within an application.</span></span>  
  
 <span data-ttu-id="370c0-106">Se trata de un escenario poco común.</span><span class="sxs-lookup"><span data-stu-id="370c0-106">This is an uncommon scenario.</span></span> <span data-ttu-id="370c0-107">A menudo, una aplicación cliente de Automatización de la interfaz de usuario utiliza proveedores del lado servidor o proveedores del lado cliente que residen en un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="370c0-107">Most often, a UI Automation client application uses server-side providers, or client-side providers that reside in a DLL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="370c0-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="370c0-108">Example</span></span>  
 <span data-ttu-id="370c0-109">El ejemplo de código siguiente implementa un proveedor simple para una ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="370c0-109">The following example code implements a simple provider for a console window.</span></span> <span data-ttu-id="370c0-110">El código no tiene ninguna funcionalidad práctica, pero está pensado para mostrar los pasos básicos para configurar un proveedor dentro de código de cliente y registrarlo mediante <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>.</span><span class="sxs-lookup"><span data-stu-id="370c0-110">The code does not have any useful functionality, but is intended to demonstrate the basic steps in setting up a provider within client code and registering it by using <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#201](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/ClientImplementationProgram.cs#201)]
 [!code-vb[UIAClientSideProvider_snip#201](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/clientimplementationprogram.vb#201)]  
  
## <a name="see-also"></a><span data-ttu-id="370c0-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="370c0-111">See Also</span></span>  
 [<span data-ttu-id="370c0-112">Información general sobre proveedores UI Automation</span><span class="sxs-lookup"><span data-stu-id="370c0-112">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)  
 [<span data-ttu-id="370c0-113">Registrar un ensamblado de proveedor del lado cliente</span><span class="sxs-lookup"><span data-stu-id="370c0-113">Register a Client-Side Provider Assembly</span></span>](../../../docs/framework/ui-automation/register-a-client-side-provider-assembly.md)  
 [<span data-ttu-id="370c0-114">Crear un proveedor de automatización de la interfaz de usuario de cliente</span><span class="sxs-lookup"><span data-stu-id="370c0-114">Create a Client-Side UI Automation Provider</span></span>](../../../docs/framework/ui-automation/create-a-client-side-ui-automation-provider.md)  
 [<span data-ttu-id="370c0-115">Implementación del proveedor de automatización de la interfaz de usuario de cliente</span><span class="sxs-lookup"><span data-stu-id="370c0-115">Client-Side UI Automation Provider Implementation</span></span>](../../../docs/framework/ui-automation/client-side-ui-automation-provider-implementation.md)

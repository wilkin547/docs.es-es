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
ms.openlocfilehash: a60253e62f814e9e3ea7ed4c5720e98e470d7f79
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71043602"
---
# <a name="implement-ui-automation-providers-in-a-client-application"></a><span data-ttu-id="c28f4-102">Implementar proveedores de UI Automation en una aplicación cliente</span><span class="sxs-lookup"><span data-stu-id="c28f4-102">Implement UI Automation Providers in a Client Application</span></span>
> [!NOTE]
> <span data-ttu-id="c28f4-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="c28f4-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="c28f4-104">Para obtener la información más [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]reciente acerca [de, consulte API de automatización de Windows: Automatización](https://go.microsoft.com/fwlink/?LinkID=156746)de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="c28f4-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="c28f4-105">Este tema contiene código de ejemplo que muestra cómo implementar un proveedor de Automatización de la interfaz de usuario del lado cliente dentro de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="c28f4-105">This topic contains example code that shows how to implement a client-side UI Automation provider within an application.</span></span>  
  
 <span data-ttu-id="c28f4-106">Se trata de un escenario poco común.</span><span class="sxs-lookup"><span data-stu-id="c28f4-106">This is an uncommon scenario.</span></span> <span data-ttu-id="c28f4-107">A menudo, una aplicación cliente de Automatización de la interfaz de usuario utiliza proveedores del lado servidor o proveedores del lado cliente que residen en un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="c28f4-107">Most often, a UI Automation client application uses server-side providers, or client-side providers that reside in a DLL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c28f4-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c28f4-108">Example</span></span>  
 <span data-ttu-id="c28f4-109">El ejemplo de código siguiente implementa un proveedor simple para una ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="c28f4-109">The following example code implements a simple provider for a console window.</span></span> <span data-ttu-id="c28f4-110">El código no tiene ninguna funcionalidad práctica, pero está pensado para mostrar los pasos básicos para configurar un proveedor dentro de código de cliente y registrarlo mediante <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>.</span><span class="sxs-lookup"><span data-stu-id="c28f4-110">The code does not have any useful functionality, but is intended to demonstrate the basic steps in setting up a provider within client code and registering it by using <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#201](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/ClientImplementationProgram.cs#201)]
 [!code-vb[UIAClientSideProvider_snip#201](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/clientimplementationprogram.vb#201)]  
  
## <a name="see-also"></a><span data-ttu-id="c28f4-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="c28f4-111">See also</span></span>

- [<span data-ttu-id="c28f4-112">Información general sobre proveedores de la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="c28f4-112">UI Automation Providers Overview</span></span>](ui-automation-providers-overview.md)
- [<span data-ttu-id="c28f4-113">Registro de un ensamblado de proveedor del lado cliente</span><span class="sxs-lookup"><span data-stu-id="c28f4-113">Register a Client-Side Provider Assembly</span></span>](register-a-client-side-provider-assembly.md)
- [<span data-ttu-id="c28f4-114">Creación de un proveedor de Automatización de la interfaz de usuario en el cliente</span><span class="sxs-lookup"><span data-stu-id="c28f4-114">Create a Client-Side UI Automation Provider</span></span>](create-a-client-side-ui-automation-provider.md)
- [<span data-ttu-id="c28f4-115">Implementación del proveedor de Automatización de la interfaz de usuario en el cliente</span><span class="sxs-lookup"><span data-stu-id="c28f4-115">Client-Side UI Automation Provider Implementation</span></span>](client-side-ui-automation-provider-implementation.md)

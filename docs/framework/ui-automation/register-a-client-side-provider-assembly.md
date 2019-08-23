---
title: Registrar un ensamblado de proveedor de cliente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- registering client-side provider assemblies
- client-side provider assemblies, registering
- UI Automation, registering provider assemblies
- provider assemblies, registering
ms.assetid: a03af4d9-2771-43cc-b07b-d468dca23190
ms.openlocfilehash: ed45b7e5d60e42f03bce8b9dc4abbf8226916304
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966355"
---
# <a name="register-a-client-side-provider-assembly"></a><span data-ttu-id="5d1a8-102">Registrar un ensamblado de proveedor de cliente</span><span class="sxs-lookup"><span data-stu-id="5d1a8-102">Register a Client-Side Provider Assembly</span></span>
> [!NOTE]
> <span data-ttu-id="5d1a8-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="5d1a8-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="5d1a8-104">Para obtener la información más [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]reciente acerca [de, consulte API de automatización de Windows: Automatización](https://go.microsoft.com/fwlink/?LinkID=156746)de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="5d1a8-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="5d1a8-105">En este tema se muestra cómo registrar una DLL que contiene los proveedores de Automatización de la interfaz de usuario del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="5d1a8-105">This topic shows how to register a DLL that contains client-side UI Automation providers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d1a8-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5d1a8-106">Example</span></span>  
 <span data-ttu-id="5d1a8-107">En el ejemplo siguiente se muestra cómo registrar un ensamblado que contiene un proveedor para una ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="5d1a8-107">The following example shows how to register an assembly that contains a provider for a console window.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSClientProgram.cs#102)]
 [!code-vb[UIAClientSideProvider_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csclientprogram.vb#102)]  
  
## <a name="see-also"></a><span data-ttu-id="5d1a8-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d1a8-108">See also</span></span>

- [<span data-ttu-id="5d1a8-109">Creación de un proveedor de Automatización de la interfaz de usuario en el cliente</span><span class="sxs-lookup"><span data-stu-id="5d1a8-109">Create a Client-Side UI Automation Provider</span></span>](../../../docs/framework/ui-automation/create-a-client-side-ui-automation-provider.md)

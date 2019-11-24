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
ms.openlocfilehash: 72e1349eee90bbe5078fec037b5f29c51c84b8ec
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438452"
---
# <a name="register-a-client-side-provider-assembly"></a><span data-ttu-id="7f99d-102">Registrar un ensamblado de proveedor de cliente</span><span class="sxs-lookup"><span data-stu-id="7f99d-102">Register a Client-Side Provider Assembly</span></span>
> [!NOTE]
> <span data-ttu-id="7f99d-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="7f99d-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="7f99d-104">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="7f99d-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="7f99d-105">En este tema se muestra cómo registrar una DLL que contiene los proveedores de Automatización de la interfaz de usuario del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="7f99d-105">This topic shows how to register a DLL that contains client-side UI Automation providers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f99d-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f99d-106">Example</span></span>  
 <span data-ttu-id="7f99d-107">En el ejemplo siguiente se muestra cómo registrar un ensamblado que contiene un proveedor para una ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="7f99d-107">The following example shows how to register an assembly that contains a provider for a console window.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSClientProgram.cs#102)]
 [!code-vb[UIAClientSideProvider_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csclientprogram.vb#102)]  
  
## <a name="see-also"></a><span data-ttu-id="7f99d-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f99d-108">See also</span></span>

- [<span data-ttu-id="7f99d-109">Creación de un proveedor de Automatización de la interfaz de usuario en el cliente</span><span class="sxs-lookup"><span data-stu-id="7f99d-109">Create a Client-Side UI Automation Provider</span></span>](create-a-client-side-ui-automation-provider.md)

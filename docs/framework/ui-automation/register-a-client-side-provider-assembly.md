---
title: Registrar un ensamblado de proveedor de cliente
description: Revise un ejemplo en el que se muestra cómo registrar un archivo DLL que contiene los proveedores de automatización de la interfaz de usuario del lado cliente.
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
ms.openlocfilehash: 1c6f7685b796b544925207a22679e6a4da455844
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250468"
---
# <a name="register-a-client-side-provider-assembly"></a><span data-ttu-id="3a144-103">Registrar un ensamblado de proveedor de cliente</span><span class="sxs-lookup"><span data-stu-id="3a144-103">Register a Client-Side Provider Assembly</span></span>

> [!NOTE]
> <span data-ttu-id="3a144-104">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="3a144-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="3a144-105">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="3a144-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="3a144-106">En este tema se muestra cómo registrar una DLL que contiene los proveedores de Automatización de la interfaz de usuario del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="3a144-106">This topic shows how to register a DLL that contains client-side UI Automation providers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a144-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3a144-107">Example</span></span>  

 <span data-ttu-id="3a144-108">En el ejemplo siguiente se muestra cómo registrar un ensamblado que contiene un proveedor para una ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="3a144-108">The following example shows how to register an assembly that contains a provider for a console window.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSClientProgram.cs#102)]
 [!code-vb[UIAClientSideProvider_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csclientprogram.vb#102)]  
  
## <a name="see-also"></a><span data-ttu-id="3a144-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a144-109">See also</span></span>

- [<span data-ttu-id="3a144-110">Crear un proveedor de UI Automation en el cliente</span><span class="sxs-lookup"><span data-stu-id="3a144-110">Create a Client-Side UI Automation Provider</span></span>](create-a-client-side-ui-automation-provider.md)

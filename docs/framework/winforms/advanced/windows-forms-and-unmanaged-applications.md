---
title: Aplicaciones de Windows Forms y aplicaciones no administradas
ms.date: 03/30/2017
helpviewer_keywords:
- ActiveX controls [Windows Forms]
- COM interop [Windows Forms], Windows Forms
- COM [Windows Forms]
- Windows Forms, unmanaged
- Windows Forms, interop
ms.assetid: 81bc100c-fa49-4614-85a6-0f7ab59eac8a
ms.openlocfilehash: c51645fb64f512b5974000f89e8e98f884a7381d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526206"
---
# <a name="windows-forms-and-unmanaged-applications"></a><span data-ttu-id="e4d55-102">Aplicaciones de Windows Forms y aplicaciones no administradas</span><span class="sxs-lookup"><span data-stu-id="e4d55-102">Windows Forms and Unmanaged Applications</span></span>
<span data-ttu-id="e4d55-103">Los controles y aplicaciones de Windows Forms pueden interoperar con aplicaciones no administradas, con algunas advertencias.</span><span class="sxs-lookup"><span data-stu-id="e4d55-103">Windows Forms applications and controls can interoperate with unmanaged applications, with some caveats.</span></span> <span data-ttu-id="e4d55-104">En las secciones siguientes se describen los escenarios y las configuraciones que las aplicaciones y los controles de Windows Forms admiten y no admiten.</span><span class="sxs-lookup"><span data-stu-id="e4d55-104">The following sections describe the scenarios and configurations that Windows Forms applications and controls support and those that they do not support.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e4d55-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e4d55-105">In This Section</span></span>  
 [<span data-ttu-id="e4d55-106">Información general sobre formularios Windows Forms y aplicaciones no administradas</span><span class="sxs-lookup"><span data-stu-id="e4d55-106">Windows Forms and Unmanaged Applications Overview</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications-overview.md)  
 <span data-ttu-id="e4d55-107">Proporciona información general acerca de cómo utilizar e implementar controles de Windows Forms que funcionan con aplicaciones no administradas.</span><span class="sxs-lookup"><span data-stu-id="e4d55-107">Offers general information about how to use and implement Windows Forms controls that work with unmanaged applications.</span></span>  
  
 [<span data-ttu-id="e4d55-108">Admitir la interoperabilidad COM al mostrar Windows Forms con el método ShowDialog</span><span class="sxs-lookup"><span data-stu-id="e4d55-108">How to: Support COM Interop by Displaying a Windows Form with the ShowDialog Method</span></span>](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md)  
 <span data-ttu-id="e4d55-109">Proporciona un ejemplo de código que muestra cómo utilizar el método <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> para ejecutar Windows Forms en una aplicación no administrada.</span><span class="sxs-lookup"><span data-stu-id="e4d55-109">Provides a code example that shows how to use the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method to run a Windows Form in an unmanaged application.</span></span>  
  
 [<span data-ttu-id="e4d55-110">Cómo: Admitir la interoperabilidad COM al mostrar Windows Forms en sus propios subprocesos</span><span class="sxs-lookup"><span data-stu-id="e4d55-110">How to: Support COM Interop by Displaying Each Windows Form on Its Own Thread</span></span>](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)  
 <span data-ttu-id="e4d55-111">Proporciona un ejemplo de código que muestra cómo ejecutar Windows Forms en su propio subproceso.</span><span class="sxs-lookup"><span data-stu-id="e4d55-111">Provides a code example that shows how to run a Windows Form on its own thread.</span></span>  
  
 <span data-ttu-id="e4d55-112">Consulte también [Tutorial: Admitir la interoperabilidad COM al mostrar Windows Forms en su propio subproceso](http://msdn.microsoft.com/library/ms233639\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="e4d55-112">Also see [Walkthrough: Supporting COM Interop by Displaying Each Windows Form on Its Own Thread](http://msdn.microsoft.com/library/ms233639\(v=vs.110\)).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e4d55-113">Referencia</span><span class="sxs-lookup"><span data-stu-id="e4d55-113">Reference</span></span>  
 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType>  
 <span data-ttu-id="e4d55-114">Se utiliza para crear un subproceso independiente para Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="e4d55-114">Used to create a separate thread for a Windows Form.</span></span>  
  
 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>  
 <span data-ttu-id="e4d55-115">Inicia un bucle de mensajes para un subproceso.</span><span class="sxs-lookup"><span data-stu-id="e4d55-115">Starts a message loop for a thread.</span></span>  
  
 <xref:System.Windows.Forms.Control.Invoke%2A>  
 <span data-ttu-id="e4d55-116">Calcula las referencias de llamadas desde una aplicación no administrada a un formulario.</span><span class="sxs-lookup"><span data-stu-id="e4d55-116">Marshals calls from an unmanaged application to a form.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e4d55-117">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="e4d55-117">Related Sections</span></span>  
 [<span data-ttu-id="e4d55-118">Exponer componentes de .NET Framework en COM</span><span class="sxs-lookup"><span data-stu-id="e4d55-118">Exposing .NET Framework Components to COM</span></span>](../../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 <span data-ttu-id="e4d55-119">Proporciona información general acerca de cómo utilizar tipos de .NET Framework en aplicaciones no administradas.</span><span class="sxs-lookup"><span data-stu-id="e4d55-119">Offers general information about how to use .NET Framework types in unmanaged applications.</span></span>

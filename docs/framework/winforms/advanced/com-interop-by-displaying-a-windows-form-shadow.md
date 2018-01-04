---
title: "Cómo: Admitir la interoperabilidad COM al mostrar Windows Forms con el método ShowDialog"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM [Windows Forms]
- Windows Forms, unmanaged
- COM interop [Windows Forms], calling methods
- ActiveX controls [Windows Forms], COM interop
- Windows Forms, interop
ms.assetid: 87aac8ad-3c04-43b3-9b0c-d0b00df9ee74
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 415ffebbcf196a163932b1b83e32a6128f0bf1a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a><span data-ttu-id="5c45d-102">Cómo: Admitir la interoperabilidad COM al mostrar Windows Forms con el método ShowDialog</span><span class="sxs-lookup"><span data-stu-id="5c45d-102">How to: Support COM Interop by Displaying a Windows Form with the ShowDialog Method</span></span>
<span data-ttu-id="5c45d-103">Puede resolver problemas de interoperabilidad del Modelo de objetos componentes (COM) mostrando el formulario de Windows Forms en un bucle de mensajes de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], que se crea con el método <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5c45d-103">You can resolve Component Object Model (COM) interoperability problems by displaying your Windows Form on a [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] message loop, which is created by using the <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="5c45d-104">Para que un formulario funcione correctamente con una aplicación cliente COM, debe ejecutarlo en un bucle de mensajes de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5c45d-104">To make a form work correctly from a COM client application, you must run it on a Windows Forms message loop.</span></span> <span data-ttu-id="5c45d-105">Para ello, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="5c45d-105">To do this, use one of the following approaches:</span></span>  
  
-   <span data-ttu-id="5c45d-106">Use el método <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> para mostrar el formulario de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5c45d-106">Use the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method to display the Windows Form;</span></span>  
  
-   <span data-ttu-id="5c45d-107">Muestre cada Windows Form en un subproceso independiente.</span><span class="sxs-lookup"><span data-stu-id="5c45d-107">Display each Windows Form on a separate thread.</span></span> <span data-ttu-id="5c45d-108">Para obtener más información, consulta [How to: Support COM Interop by Displaying Each Windows Form on Its Own Thread](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md).</span><span class="sxs-lookup"><span data-stu-id="5c45d-108">For more information, see [How to: Support COM Interop by Displaying Each Windows Form on Its Own Thread](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="5c45d-109">Procedimiento</span><span class="sxs-lookup"><span data-stu-id="5c45d-109">Procedure</span></span>  
 <span data-ttu-id="5c45d-110">El uso del método <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> puede ser la manera más fácil de mostrar un formulario en un bucle de mensajes de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] porque, de todos los enfoques, es el que necesita menos código para su implementación.</span><span class="sxs-lookup"><span data-stu-id="5c45d-110">Using the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method can be the easiest way to display a form on a [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] message loop because, of all the approaches, it requires the least code to implement.</span></span>  
  
 <span data-ttu-id="5c45d-111">El método <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> suspende el bucle de mensajes de la aplicación no administrada y muestra el formulario en forma de cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5c45d-111">The <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method suspends the unmanaged application's message loop and displays the form as a dialog box.</span></span> <span data-ttu-id="5c45d-112">Una vez suspendido el bucle de mensajes de la aplicación host, el método <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> crea otro bucle de mensajes de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para procesar los mensajes del formulario.</span><span class="sxs-lookup"><span data-stu-id="5c45d-112">Because the host application's message loop has been suspended, the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method creates a new [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] message loop to process the form's messages.</span></span>  
  
 <span data-ttu-id="5c45d-113">La desventaja a la hora de usar el método <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> es que el formulario se abrirá como un cuadro de diálogo modal.</span><span class="sxs-lookup"><span data-stu-id="5c45d-113">The disadvantage of using the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method is that the form will be opened as a modal dialog box.</span></span> <span data-ttu-id="5c45d-114">Este comportamiento bloquea cualquier interfaz de usuario (IU) de la aplicación que hace la llamada mientras el formulario de Windows Forms esté abierto.</span><span class="sxs-lookup"><span data-stu-id="5c45d-114">This behavior blocks any user interface (UI) in the calling application while the Windows Form is open.</span></span> <span data-ttu-id="5c45d-115">Cuando el usuario sale del formulario, el bucle de mensajes de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] se cierra y el bucle de mensajes de la primera aplicación vuelve a ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="5c45d-115">When the user exits the form, the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] message loop closes and the earlier application's message loop starts running again.</span></span>  
  
 <span data-ttu-id="5c45d-116">Puede crear una biblioteca de clases en Windows Forms que tenga un método para mostrar el formulario y, después, compilar la biblioteca de clases para la interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="5c45d-116">You can create a class library in Windows Forms which has a method to show the form, and then build the class library for COM interop.</span></span> <span data-ttu-id="5c45d-117">Puede usar este archivo DLL desde Visual Basic 6.0 o desde Microsoft Foundation Classes (MFC); además, desde cualquiera de estos entornos puede llamar al método <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> para mostrar el formulario.</span><span class="sxs-lookup"><span data-stu-id="5c45d-117">You can use this DLL file from Visual Basic 6.0 or Microsoft Foundation Classes (MFC), and from either of these environments you can call the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method to display the form.</span></span>  
  
#### <a name="to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a><span data-ttu-id="5c45d-118">Para admitir la interoperabilidad COM mostrando un formulario de Windows Forms con el método ShowDialog</span><span class="sxs-lookup"><span data-stu-id="5c45d-118">To support COM interop by displaying a windows form with the ShowDialog method</span></span>  
  
-   <span data-ttu-id="5c45d-119">Reemplace todas las llamadas al método <xref:System.Windows.Forms.Form.Show%2A?displayProperty=nameWithType> por llamadas al método <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> en su componente de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c45d-119">Replace all calls to the <xref:System.Windows.Forms.Form.Show%2A?displayProperty=nameWithType> method with calls to the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method in your [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c45d-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c45d-120">See Also</span></span>  
 [<span data-ttu-id="5c45d-121">Exponer componentes de .NET Framework en COM</span><span class="sxs-lookup"><span data-stu-id="5c45d-121">Exposing .NET Framework Components to COM</span></span>](../../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 [<span data-ttu-id="5c45d-122">Cómo: Admitir la interoperabilidad COM al mostrar Windows Forms en sus propios subprocesos</span><span class="sxs-lookup"><span data-stu-id="5c45d-122">How to: Support COM Interop by Displaying Each Windows Form on Its Own Thread</span></span>](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)  
 [<span data-ttu-id="5c45d-123">Aplicaciones de Windows Forms y aplicaciones no administradas</span><span class="sxs-lookup"><span data-stu-id="5c45d-123">Windows Forms and Unmanaged Applications</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications.md)

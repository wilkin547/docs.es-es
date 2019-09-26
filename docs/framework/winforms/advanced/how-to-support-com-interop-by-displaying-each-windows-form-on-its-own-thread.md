---
title: Procedimiento para admitir la interoperabilidad COM al mostrar formularios Windows Forms en sus propios subprocesos
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- COM interop [Windows Forms], Windows Forms
- COM [Windows Forms]
- Windows Forms, unmanaged
- ActiveX controls [Windows Forms], COM interop
- Windows Forms, interop
ms.assetid: a9e04765-d2de-4389-a494-a9a6d07aa6ee
ms.openlocfilehash: 41af4d81995a0a4eac912ecce7dc70cf04f012cd
ms.sourcegitcommit: 1e72e2990220b3635cebc39586828af9deb72d8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2019
ms.locfileid: "71306387"
---
# <a name="how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread"></a><span data-ttu-id="f5a2b-102">Procedimiento Compatibilidad con la interoperabilidad COM mostrando cada Windows Forms en su propio subproceso</span><span class="sxs-lookup"><span data-stu-id="f5a2b-102">How to: Support COM interop by displaying each Windows Form on its own thread</span></span>

<span data-ttu-id="f5a2b-103">Puede resolver problemas de interoperabilidad COM mostrando el formulario en un bucle de mensajes .NET Framework, que puede crear mediante el <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="f5a2b-103">You can resolve COM interoperability problems by displaying your form on a .NET Framework message loop, which you can create by using the <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="f5a2b-104">Para que un Windows Form funcione correctamente con una aplicación cliente COM, debe ejecutar el formulario en un bucle de mensajes de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f5a2b-104">To make a Windows Form work correctly from a COM client application, you must run the form on a Windows Forms message loop.</span></span> <span data-ttu-id="f5a2b-105">Para ello, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="f5a2b-105">To do this, use one of the following approaches:</span></span>

- <span data-ttu-id="f5a2b-106">Use el método <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> para mostrar el Windows Form.</span><span class="sxs-lookup"><span data-stu-id="f5a2b-106">Use the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method to display the Windows Form.</span></span> <span data-ttu-id="f5a2b-107">Para obtener más información, vea [Cómo: Compatibilidad con la interoperabilidad COM al mostrar Windows Forms](com-interop-by-displaying-a-windows-form-shadow.md)con el método ShowDialog.</span><span class="sxs-lookup"><span data-stu-id="f5a2b-107">For more information, see [How to: Support COM Interop by Displaying a Windows Form with the ShowDialog Method](com-interop-by-displaying-a-windows-form-shadow.md).</span></span>

- <span data-ttu-id="f5a2b-108">Muestre cada Windows Form en un subproceso independiente.</span><span class="sxs-lookup"><span data-stu-id="f5a2b-108">Display each Windows Form on a separate thread.</span></span>

<span data-ttu-id="f5a2b-109">Hay una amplia compatibilidad para esta característica en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f5a2b-109">There is extensive support for this feature in Visual Studio.</span></span>

<span data-ttu-id="f5a2b-110">Consulte [también Tutorial: Compatibilidad con la interoperabilidad COM al mostrar cada Windows Forms en su propio subproceso](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233639(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f5a2b-110">Also see [Walkthrough: Supporting COM Interop by Displaying Each Windows Form on Its Own Thread](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233639(v=vs.100)).</span></span>

## <a name="example"></a><span data-ttu-id="f5a2b-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f5a2b-111">Example</span></span>

<span data-ttu-id="f5a2b-112">En el ejemplo de código siguiente se ilustra cómo mostrar el formulario en un subproceso independiente y cómo llamar al método <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> para iniciar un bombeo de mensajes de Windows Forms en ese subproceso.</span><span class="sxs-lookup"><span data-stu-id="f5a2b-112">The following code example demonstrates how to display the form on a separate thread and call the <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> method to start a Windows Forms message pump on that thread.</span></span> <span data-ttu-id="f5a2b-113">Para usar este enfoque, debe calcular las referencias de las llamadas al formulario desde la aplicación no administrada usando el método <xref:System.Windows.Forms.Control.Invoke%2A> .</span><span class="sxs-lookup"><span data-stu-id="f5a2b-113">To use this approach, you must marshal any calls to the form from the unmanaged application by using the <xref:System.Windows.Forms.Control.Invoke%2A> method.</span></span>

<span data-ttu-id="f5a2b-114">Este enfoque requiere que cada instancia de un formulario se ejecuta en su propio subproceso usando su propio bucle de mensajes.</span><span class="sxs-lookup"><span data-stu-id="f5a2b-114">This approach requires that each instance of a form runs on its own thread by using its own message loop.</span></span> <span data-ttu-id="f5a2b-115">No puede tener más de un bucle de mensajes en ejecución por subproceso.</span><span class="sxs-lookup"><span data-stu-id="f5a2b-115">You cannot have more than one message loop running per thread.</span></span> <span data-ttu-id="f5a2b-116">Por lo tanto, no puede cambiar el bucle de mensajes de la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="f5a2b-116">Therefore, you cannot change the client application's message loop.</span></span> <span data-ttu-id="f5a2b-117">Sin embargo, puede modificar el componente de .NET Framework para iniciar un nuevo subproceso que use su propio bucle de mensajes.</span><span class="sxs-lookup"><span data-stu-id="f5a2b-117">However, you can modify the .NET Framework component to start a new thread that uses its own message loop.</span></span>

[!code-vb[System.Windows.Forms.ComInterop#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/COMForm.vb#1)]

[!code-vb[System.Windows.Forms.ComInterop#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/FormManager.vb#10)]

[!code-vb[System.Windows.Forms.ComInterop#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/Form1.vb#100)]

## <a name="compile-the-code"></a><span data-ttu-id="f5a2b-118">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="f5a2b-118">Compile the code</span></span>

<span data-ttu-id="f5a2b-119">Compile los tipos `COMForm`, `Form1`y `FormManager` en un ensamblado llamado `COMWinform.dll`.</span><span class="sxs-lookup"><span data-stu-id="f5a2b-119">Compile the `COMForm`, `Form1`, and `FormManager` types into an assembly called `COMWinform.dll`.</span></span> <span data-ttu-id="f5a2b-120">Registre el ensamblado para la interoperabilidad COM usando uno de los métodos descritos en [Packaging an Assembly for COM](../../interop/packaging-an-assembly-for-com.md).</span><span class="sxs-lookup"><span data-stu-id="f5a2b-120">Register the assembly for COM interop by using one of the methods described in [Packaging an Assembly for COM](../../interop/packaging-an-assembly-for-com.md).</span></span> <span data-ttu-id="f5a2b-121">Ahora puede usar el ensamblado y el archivo de biblioteca de tipos (.tlb) correspondiente en las aplicaciones no administradas.</span><span class="sxs-lookup"><span data-stu-id="f5a2b-121">You can now use the assembly and its corresponding type library (.tlb) file in unmanaged applications.</span></span> <span data-ttu-id="f5a2b-122">Por ejemplo, puede usar la biblioteca de tipos como una referencia en un proyecto ejecutable de Visual Basic 6.0.</span><span class="sxs-lookup"><span data-stu-id="f5a2b-122">For example, you can use the type library as a reference in a Visual Basic 6.0 executable project.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5a2b-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5a2b-123">See also</span></span>

- [<span data-ttu-id="f5a2b-124">Exponer componentes de .NET Framework en COM</span><span class="sxs-lookup"><span data-stu-id="f5a2b-124">Exposing .NET Framework Components to COM</span></span>](../../interop/exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="f5a2b-125">Empaquetar un ensamblado para COM</span><span class="sxs-lookup"><span data-stu-id="f5a2b-125">Packaging an Assembly for COM</span></span>](../../interop/packaging-an-assembly-for-com.md)
- [<span data-ttu-id="f5a2b-126">Registrar ensamblados con COM</span><span class="sxs-lookup"><span data-stu-id="f5a2b-126">Registering Assemblies with COM</span></span>](../../interop/registering-assemblies-with-com.md)
- [<span data-ttu-id="f5a2b-127">Cómo: Compatibilidad con la interoperabilidad COM al mostrar Windows Forms con el método ShowDialog</span><span class="sxs-lookup"><span data-stu-id="f5a2b-127">How to: Support COM Interop by Displaying a Windows Form with the ShowDialog Method</span></span>](com-interop-by-displaying-a-windows-form-shadow.md)
- [<span data-ttu-id="f5a2b-128">Información general sobre formularios Windows Forms y aplicaciones no administradas</span><span class="sxs-lookup"><span data-stu-id="f5a2b-128">Windows Forms and Unmanaged Applications Overview</span></span>](windows-forms-and-unmanaged-applications-overview.md)

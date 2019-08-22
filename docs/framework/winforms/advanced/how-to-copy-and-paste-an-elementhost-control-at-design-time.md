---
title: Filtrar para copiar y pegar un control ElementHost en tiempo de diseño
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: dfe5244e0c5b61fdf6d940dd16d8c280f013b12c
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666177"
---
# <a name="how-to-copy-and-paste-an-elementhost-control"></a><span data-ttu-id="93f43-102">Filtrar Copiar y pegar un control ElementHost</span><span class="sxs-lookup"><span data-stu-id="93f43-102">How to: Copy and paste an ElementHost control</span></span>

<span data-ttu-id="93f43-103">En este procedimiento se muestra cómo copiar un control de Windows Presentation Foundation (WPF) en Windows Forms en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="93f43-103">This procedure shows you how to copy a Windows Presentation Foundation (WPF) control on a Windows Form in Visual Studio.</span></span>

1. <span data-ttu-id="93f43-104">En Visual Studio, agregue un nuevo WPF <xref:System.Windows.Controls.UserControl> a un proyecto Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="93f43-104">In Visual Studio, add a new WPF <xref:System.Windows.Controls.UserControl> to a Windows Forms project.</span></span> <span data-ttu-id="93f43-105">Use el nombre predeterminado del tipo de control, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="93f43-105">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="93f43-106">Para obtener más información, vea [Tutorial: Crear nuevo contenido de WPF en Windows Forms en tiempo](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)de diseño.</span><span class="sxs-lookup"><span data-stu-id="93f43-106">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="93f43-107">En la ventana **propiedades** , establezca el valor de las <xref:System.Windows.FrameworkElement.Width%2A> propiedades <xref:System.Windows.FrameworkElement.Height%2A> y de `UserControl1` en **200**.</span><span class="sxs-lookup"><span data-stu-id="93f43-107">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties of `UserControl1` to **200**.</span></span>

3. <span data-ttu-id="93f43-108">Establezca el valor de la <xref:System.Windows.Controls.Control.Background%2A> propiedad en **azul**.</span><span class="sxs-lookup"><span data-stu-id="93f43-108">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to **Blue**.</span></span>

4. <span data-ttu-id="93f43-109">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="93f43-109">Build the project.</span></span>

5. <span data-ttu-id="93f43-110">Abra `Form1` en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="93f43-110">Open `Form1` in the Windows Forms Designer.</span></span>

6. <span data-ttu-id="93f43-111">En el **cuadro de herramientas**, arrastre una `UserControl1` instancia de al formulario.</span><span class="sxs-lookup"><span data-stu-id="93f43-111">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>

   <span data-ttu-id="93f43-112">La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="93f43-112">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

7. <span data-ttu-id="93f43-113">Con `elementHost1` seleccionado, presione **Ctrl**+**C** para copiarlo en el portapapeles.</span><span class="sxs-lookup"><span data-stu-id="93f43-113">With `elementHost1` selected, press **Ctrl**+**C** to copy it to the clipboard.</span></span>

8. <span data-ttu-id="93f43-114">Presione **Ctrl**+**V** para pegar el control copiado en el formulario.</span><span class="sxs-lookup"><span data-stu-id="93f43-114">Press **Ctrl**+**V** to paste the copied control onto the form.</span></span>

   <span data-ttu-id="93f43-115">Se crea <xref:System.Windows.Forms.Integration.ElementHost> un nuevo `elementHost2` control denominado en el formulario.</span><span class="sxs-lookup"><span data-stu-id="93f43-115">A new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost2` is created on the form.</span></span>

## <a name="see-also"></a><span data-ttu-id="93f43-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="93f43-116">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="93f43-117">Migración e interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="93f43-117">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="93f43-118">Utilizar controles WPF</span><span class="sxs-lookup"><span data-stu-id="93f43-118">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="93f43-119">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="93f43-119">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)

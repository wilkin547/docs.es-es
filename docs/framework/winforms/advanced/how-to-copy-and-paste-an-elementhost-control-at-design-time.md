---
title: 'Cómo: Copiar y pegar un control ElementHost en tiempo de diseño'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: e89510558274558e560bf810afe746e250ff26a4
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459228"
---
# <a name="how-to-copy-and-paste-an-elementhost-control"></a><span data-ttu-id="ec95e-102">Cómo: copiar y pegar un control ElementHost</span><span class="sxs-lookup"><span data-stu-id="ec95e-102">How to: Copy and paste an ElementHost control</span></span>

<span data-ttu-id="ec95e-103">En este procedimiento se muestra cómo copiar un control de Windows Presentation Foundation (WPF) en Windows Forms en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ec95e-103">This procedure shows you how to copy a Windows Presentation Foundation (WPF) control on a Windows Form in Visual Studio.</span></span>

1. <span data-ttu-id="ec95e-104">En Visual Studio, agregue un nuevo <xref:System.Windows.Controls.UserControl> de WPF a un proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ec95e-104">In Visual Studio, add a new WPF <xref:System.Windows.Controls.UserControl> to a Windows Forms project.</span></span> <span data-ttu-id="ec95e-105">Use el nombre predeterminado del tipo de control, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="ec95e-105">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="ec95e-106">Para obtener más información, vea [Tutorial: crear nuevo contenido de WPF en Windows Forms en tiempo de diseño](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="ec95e-106">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="ec95e-107">En la ventana **propiedades** , establezca el valor de las propiedades <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> de `UserControl1` en **200**.</span><span class="sxs-lookup"><span data-stu-id="ec95e-107">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties of `UserControl1` to **200**.</span></span>

3. <span data-ttu-id="ec95e-108">Establezca el valor de la propiedad <xref:System.Windows.Controls.Control.Background%2A> en **Blue**.</span><span class="sxs-lookup"><span data-stu-id="ec95e-108">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to **Blue**.</span></span>

4. <span data-ttu-id="ec95e-109">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="ec95e-109">Build the project.</span></span>

5. <span data-ttu-id="ec95e-110">Abra `Form1` en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ec95e-110">Open `Form1` in the Windows Forms Designer.</span></span>

6. <span data-ttu-id="ec95e-111">En el **cuadro de herramientas**, arrastre una instancia de `UserControl1` al formulario.</span><span class="sxs-lookup"><span data-stu-id="ec95e-111">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>

   <span data-ttu-id="ec95e-112">La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="ec95e-112">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

7. <span data-ttu-id="ec95e-113">Con `elementHost1` seleccionado, presione **Ctrl**+**C** para copiarlo en el portapapeles.</span><span class="sxs-lookup"><span data-stu-id="ec95e-113">With `elementHost1` selected, press **Ctrl**+**C** to copy it to the clipboard.</span></span>

8. <span data-ttu-id="ec95e-114">Presione **Ctrl**+**V** para pegar el control copiado en el formulario.</span><span class="sxs-lookup"><span data-stu-id="ec95e-114">Press **Ctrl**+**V** to paste the copied control onto the form.</span></span>

   <span data-ttu-id="ec95e-115">En el formulario se crea un nuevo control de <xref:System.Windows.Forms.Integration.ElementHost> denominado `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="ec95e-115">A new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost2` is created on the form.</span></span>

## <a name="see-also"></a><span data-ttu-id="ec95e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec95e-116">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="ec95e-117">Migración e interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="ec95e-117">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="ec95e-118">Utilizar controles WPF</span><span class="sxs-lookup"><span data-stu-id="ec95e-118">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="ec95e-119">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ec95e-119">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)

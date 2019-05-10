---
title: Procedimiento para copiar y pegar un control ElementHost en tiempo de diseño
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
ms.openlocfilehash: 0f3367deaaec04744a3f812d7f2d08047d7eb588
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211395"
---
# <a name="how-to-copy-and-paste-an-elementhost-control-at-design-time"></a><span data-ttu-id="88e22-102">Procedimiento para copiar y pegar un control ElementHost en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="88e22-102">How to: Copy and Paste an ElementHost Control at Design Time</span></span>

<span data-ttu-id="88e22-103">Este procedimiento muestra cómo copiar un control de Windows Presentation Foundation (WPF) en un formulario Windows Forms en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="88e22-103">This procedure shows you how to copy a Windows Presentation Foundation (WPF) control on a Windows Form in Visual Studio.</span></span>

## <a name="copy-and-paste-an-elementhost-control-at-design-time"></a><span data-ttu-id="88e22-104">Copiar y pegar un control ElementHost en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="88e22-104">Copy and paste an ElementHost control at design time</span></span>

1. <span data-ttu-id="88e22-105">Agregue un nuevo WPF <xref:System.Windows.Controls.UserControl> a su proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="88e22-105">Add a new WPF <xref:System.Windows.Controls.UserControl> to your Windows Forms project.</span></span> <span data-ttu-id="88e22-106">Use el nombre predeterminado del tipo de control, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="88e22-106">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="88e22-107">Para obtener más información, vea [Tutorial: Crear nuevo contenido WPF en Windows Forms en tiempo de diseño](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="88e22-107">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="88e22-108">En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> propiedades de `UserControl1` a `200`.</span><span class="sxs-lookup"><span data-stu-id="88e22-108">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties of `UserControl1` to `200`.</span></span>

3. <span data-ttu-id="88e22-109">Establezca el valor de la propiedad <xref:System.Windows.Controls.Control.Background%2A> en `Blue`.</span><span class="sxs-lookup"><span data-stu-id="88e22-109">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Blue`.</span></span>

4. <span data-ttu-id="88e22-110">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="88e22-110">Build the project.</span></span>

5. <span data-ttu-id="88e22-111">Abra `Form1` en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="88e22-111">Open `Form1` in the Windows Forms Designer.</span></span>

6. <span data-ttu-id="88e22-112">Desde el **cuadro de herramientas**, arrastre una instancia de `UserControl1` hasta el formulario.</span><span class="sxs-lookup"><span data-stu-id="88e22-112">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>

   <span data-ttu-id="88e22-113">La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="88e22-113">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

7. <span data-ttu-id="88e22-114">Con `elementHost1` seleccionado, presione CTRL+C para copiarlo en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="88e22-114">With `elementHost1` selected, press CTRL+C to copy it to the clipboard.</span></span>

8. <span data-ttu-id="88e22-115">Presione CTRL+V para pegar el control copiado en el formulario.</span><span class="sxs-lookup"><span data-stu-id="88e22-115">Press CTRL+V to paste the copied control onto the form.</span></span>

   <span data-ttu-id="88e22-116">Un nuevo <xref:System.Windows.Forms.Integration.ElementHost> control denominado `elementHost2` se crea en el formulario.</span><span class="sxs-lookup"><span data-stu-id="88e22-116">A new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost2` is created on the form.</span></span>

## <a name="see-also"></a><span data-ttu-id="88e22-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="88e22-117">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="88e22-118">Migración e interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="88e22-118">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="88e22-119">Utilizar controles WPF</span><span class="sxs-lookup"><span data-stu-id="88e22-119">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="88e22-120">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="88e22-120">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)

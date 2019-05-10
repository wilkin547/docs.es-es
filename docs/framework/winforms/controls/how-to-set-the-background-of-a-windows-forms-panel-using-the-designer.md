---
title: Procedimiento para establecer el fondo de un control Panel de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: 6927a7118c43ced03623a9764a3ef1e0814c95cb
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211639"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a><span data-ttu-id="a02d6-102">Procedimiento Establecer el fondo de un panel de Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="a02d6-102">How to: Set the background of a Windows Forms panel using the Designer</span></span>

<span data-ttu-id="a02d6-103">Un formulario Windows Forms <xref:System.Windows.Forms.Panel> control puede mostrar un color de fondo y una imagen de fondo.</span><span class="sxs-lookup"><span data-stu-id="a02d6-103">A Windows Forms <xref:System.Windows.Forms.Panel> control can display both a background color and a background image.</span></span> <span data-ttu-id="a02d6-104">El <xref:System.Windows.Forms.Control.BackColor%2A> propiedad establece el color de fondo para los controles que se encuentran en el panel, como etiquetas y botones de radio.</span><span class="sxs-lookup"><span data-stu-id="a02d6-104">The <xref:System.Windows.Forms.Control.BackColor%2A> property sets the background color for controls that are contained in the panel, such as labels and radio buttons.</span></span> <span data-ttu-id="a02d6-105">Si el <xref:System.Windows.Forms.Control.BackgroundImage%2A> no se establece la propiedad, el <xref:System.Windows.Forms.Control.BackColor%2A> selección llenará el panel.</span><span class="sxs-lookup"><span data-stu-id="a02d6-105">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is not set, the <xref:System.Windows.Forms.Control.BackColor%2A> selection will fill all of the panel.</span></span> <span data-ttu-id="a02d6-106">Si el <xref:System.Windows.Forms.Control.BackgroundImage%2A> propiedad está establecida, la imagen se mostrará detrás de los controles que se encuentran en el panel.</span><span class="sxs-lookup"><span data-stu-id="a02d6-106">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is set, the image will be displayed behind the controls that are contained in the panel.</span></span>

<span data-ttu-id="a02d6-107">El procedimiento siguiente requiere una **aplicación Windows** proyecto con un formulario que contiene un <xref:System.Windows.Forms.Panel> control.</span><span class="sxs-lookup"><span data-stu-id="a02d6-107">The following procedure requires a **Windows Application** project with a form that contains a <xref:System.Windows.Forms.Panel> control.</span></span> <span data-ttu-id="a02d6-108">Para obtener información acerca de cómo configurar dicho proyecto en Visual Studio, vea [Cómo: Cree un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="a02d6-108">For information about how to set up such a project in Visual Studio, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="set-the-background-in-the-windows-forms-designer"></a><span data-ttu-id="a02d6-109">Establecer el fondo en el Diseñador de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a02d6-109">Set the background in the Windows Forms Designer</span></span>

1. <span data-ttu-id="a02d6-110">Abra el proyecto en Visual Studio y seleccione el <xref:System.Windows.Forms.Panel> control.</span><span class="sxs-lookup"><span data-stu-id="a02d6-110">Open the project in Visual Studio and select the <xref:System.Windows.Forms.Panel> control.</span></span>

2. <span data-ttu-id="a02d6-111">En el **propiedades** ventana, haga clic en el botón de flecha situado junto a la <xref:System.Windows.Forms.Control.BackColor%2A> propiedad para mostrar una ventana con tres fichas.</span><span class="sxs-lookup"><span data-stu-id="a02d6-111">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackColor%2A> property to display a window with three tabs.</span></span>

3. <span data-ttu-id="a02d6-112">Seleccione el **personalizado** ficha para mostrar una paleta de colores.</span><span class="sxs-lookup"><span data-stu-id="a02d6-112">Select the **Custom** tab to display a palette of colors.</span></span>

4. <span data-ttu-id="a02d6-113">Seleccione el **Web** o **sistema** ficha para mostrar una lista de nombres de colores predefinidos y, a continuación, seleccione un color.</span><span class="sxs-lookup"><span data-stu-id="a02d6-113">Select the **Web** or **System** tab to display a list of predefined names for colors, and then select a color.</span></span>

5. <span data-ttu-id="a02d6-114">En el **propiedades** ventana, haga clic en el botón de flecha situado junto a la <xref:System.Windows.Forms.Control.BackgroundImage%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="a02d6-114">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span>

6. <span data-ttu-id="a02d6-115">En el **abierto** cuadro de diálogo, seleccione el archivo que desea mostrar.</span><span class="sxs-lookup"><span data-stu-id="a02d6-115">In the **Open** dialog box, select the file that you want to display.</span></span>

## <a name="see-also"></a><span data-ttu-id="a02d6-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a02d6-116">See also</span></span>

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [<span data-ttu-id="a02d6-117">Panel (control)</span><span class="sxs-lookup"><span data-stu-id="a02d6-117">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="a02d6-118">Información general del control Panel</span><span class="sxs-lookup"><span data-stu-id="a02d6-118">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="a02d6-119">Cómo: Agrupar controles con el Control de Panel de Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="a02d6-119">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>](group-controls-with-wf-panel-control-using-the-designer.md)

---
title: Establecer el fondo de un panel mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: 8bdefba433632f7ba02f549a549c52c7aa56c2d7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731917"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a><span data-ttu-id="42a7f-102">Cómo: establecer el fondo de un panel de Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="42a7f-102">How to: Set the background of a Windows Forms panel using the Designer</span></span>

<span data-ttu-id="42a7f-103">Un control de <xref:System.Windows.Forms.Panel> de Windows Forms puede mostrar un color de fondo y una imagen de fondo.</span><span class="sxs-lookup"><span data-stu-id="42a7f-103">A Windows Forms <xref:System.Windows.Forms.Panel> control can display both a background color and a background image.</span></span> <span data-ttu-id="42a7f-104">La propiedad <xref:System.Windows.Forms.Control.BackColor%2A> establece el color de fondo de los controles contenidos en el panel, como etiquetas y botones de radio.</span><span class="sxs-lookup"><span data-stu-id="42a7f-104">The <xref:System.Windows.Forms.Control.BackColor%2A> property sets the background color for controls that are contained in the panel, such as labels and radio buttons.</span></span> <span data-ttu-id="42a7f-105">Si no se establece la propiedad <xref:System.Windows.Forms.Control.BackgroundImage%2A>, la selección de <xref:System.Windows.Forms.Control.BackColor%2A> rellenará todo el panel.</span><span class="sxs-lookup"><span data-stu-id="42a7f-105">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is not set, the <xref:System.Windows.Forms.Control.BackColor%2A> selection will fill all of the panel.</span></span> <span data-ttu-id="42a7f-106">Si se establece la propiedad <xref:System.Windows.Forms.Control.BackgroundImage%2A>, la imagen se mostrará detrás de los controles contenidos en el panel.</span><span class="sxs-lookup"><span data-stu-id="42a7f-106">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is set, the image will be displayed behind the controls that are contained in the panel.</span></span>

<span data-ttu-id="42a7f-107">El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que contenga un control <xref:System.Windows.Forms.Panel>.</span><span class="sxs-lookup"><span data-stu-id="42a7f-107">The following procedure requires a **Windows Application** project with a form that contains a <xref:System.Windows.Forms.Panel> control.</span></span> <span data-ttu-id="42a7f-108">Para obtener información sobre cómo configurar este tipo de proyecto en Visual Studio, vea [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="42a7f-108">For information about how to set up such a project in Visual Studio, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="set-the-background-in-the-windows-forms-designer"></a><span data-ttu-id="42a7f-109">Establecer el fondo en el Diseñador de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="42a7f-109">Set the background in the Windows Forms Designer</span></span>

1. <span data-ttu-id="42a7f-110">Abra el proyecto en Visual Studio y seleccione el control <xref:System.Windows.Forms.Panel>.</span><span class="sxs-lookup"><span data-stu-id="42a7f-110">Open the project in Visual Studio and select the <xref:System.Windows.Forms.Panel> control.</span></span>

2. <span data-ttu-id="42a7f-111">En la ventana **propiedades** , haga clic en el botón de flecha situado junto a la propiedad <xref:System.Windows.Forms.Control.BackColor%2A> para mostrar una ventana con tres pestañas.</span><span class="sxs-lookup"><span data-stu-id="42a7f-111">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackColor%2A> property to display a window with three tabs.</span></span>

3. <span data-ttu-id="42a7f-112">Seleccione la pestaña **personalizado** para mostrar una paleta de colores.</span><span class="sxs-lookup"><span data-stu-id="42a7f-112">Select the **Custom** tab to display a palette of colors.</span></span>

4. <span data-ttu-id="42a7f-113">Seleccione la pestaña **Web** o **sistema** para mostrar una lista de nombres predefinidos para los colores y, a continuación, seleccione un color.</span><span class="sxs-lookup"><span data-stu-id="42a7f-113">Select the **Web** or **System** tab to display a list of predefined names for colors, and then select a color.</span></span>

5. <span data-ttu-id="42a7f-114">En la ventana **propiedades** , haga clic en el botón de flecha situado junto a la propiedad <xref:System.Windows.Forms.Control.BackgroundImage%2A>.</span><span class="sxs-lookup"><span data-stu-id="42a7f-114">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span>

6. <span data-ttu-id="42a7f-115">En el cuadro de diálogo **abrir** , seleccione el archivo que desea mostrar.</span><span class="sxs-lookup"><span data-stu-id="42a7f-115">In the **Open** dialog box, select the file that you want to display.</span></span>

## <a name="see-also"></a><span data-ttu-id="42a7f-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="42a7f-116">See also</span></span>

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [<span data-ttu-id="42a7f-117">Panel (control)</span><span class="sxs-lookup"><span data-stu-id="42a7f-117">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="42a7f-118">Información general del control Panel</span><span class="sxs-lookup"><span data-stu-id="42a7f-118">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="42a7f-119">Agrupar controles con el control Panel de Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="42a7f-119">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>](group-controls-with-wf-panel-control-using-the-designer.md)

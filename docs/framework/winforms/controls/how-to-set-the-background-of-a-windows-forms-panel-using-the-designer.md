---
title: 'Cómo: Establecer el fondo de un control Panel de formularios Windows Forms mediante el Diseñador'
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: 86ab8bc979765fe79ccc76db9a0566459fde6e46
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43499918"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a><span data-ttu-id="45a13-102">Cómo: Establecer el fondo de un control Panel de formularios Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="45a13-102">How to: Set the Background of a Windows Forms Panel Using the Designer</span></span>
<span data-ttu-id="45a13-103">Un formulario Windows Forms <xref:System.Windows.Forms.Panel> control puede mostrar un color de fondo y una imagen de fondo.</span><span class="sxs-lookup"><span data-stu-id="45a13-103">A Windows Forms <xref:System.Windows.Forms.Panel> control can display both a background color and a background image.</span></span> <span data-ttu-id="45a13-104">El <xref:System.Windows.Forms.Control.BackColor%2A> propiedad establece el color de fondo para los controles que se encuentran en el panel, como etiquetas y botones de radio.</span><span class="sxs-lookup"><span data-stu-id="45a13-104">The <xref:System.Windows.Forms.Control.BackColor%2A> property sets the background color for controls that are contained in the panel, such as labels and radio buttons.</span></span> <span data-ttu-id="45a13-105">Si el <xref:System.Windows.Forms.Control.BackgroundImage%2A> no se establece la propiedad, el <xref:System.Windows.Forms.Control.BackColor%2A> selección llenará el panel.</span><span class="sxs-lookup"><span data-stu-id="45a13-105">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is not set, the <xref:System.Windows.Forms.Control.BackColor%2A> selection will fill all of the panel.</span></span> <span data-ttu-id="45a13-106">Si el <xref:System.Windows.Forms.Control.BackgroundImage%2A> propiedad está establecida, la imagen se mostrará detrás de los controles que se encuentran en el panel.</span><span class="sxs-lookup"><span data-stu-id="45a13-106">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is set, the image will be displayed behind the controls that are contained in the panel.</span></span>  
  
 <span data-ttu-id="45a13-107">El procedimiento siguiente requiere una **aplicación Windows** proyecto con un formulario que contiene un <xref:System.Windows.Forms.Panel> control.</span><span class="sxs-lookup"><span data-stu-id="45a13-107">The following procedure requires a **Windows Application** project with a form that contains a <xref:System.Windows.Forms.Panel> control.</span></span> <span data-ttu-id="45a13-108">Para obtener información acerca de cómo configurar un proyecto de este tipo, consulte [Cómo: crear un proyecto de aplicación Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: agregar controles a Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="45a13-108">For information about how to set up such a project, see [How to: Create a Windows Application Project](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="45a13-109">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="45a13-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="45a13-110">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="45a13-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="45a13-111">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="45a13-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-set-the-background-in-the-windows-forms-designer"></a><span data-ttu-id="45a13-112">Para establecer el fondo en el Diseñador de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="45a13-112">To set the background in the Windows Forms Designer</span></span>  
  
1.  <span data-ttu-id="45a13-113">Seleccione el control <xref:System.Windows.Forms.Panel>.</span><span class="sxs-lookup"><span data-stu-id="45a13-113">Select the <xref:System.Windows.Forms.Panel> control.</span></span>  
  
2.  <span data-ttu-id="45a13-114">En el **propiedades** ventana, haga clic en el botón de flecha situado junto a la <xref:System.Windows.Forms.Control.BackColor%2A> propiedad para mostrar una ventana con tres fichas.</span><span class="sxs-lookup"><span data-stu-id="45a13-114">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackColor%2A> property to display a window with three tabs.</span></span>  
  
3.  <span data-ttu-id="45a13-115">Seleccione el **personalizado** ficha para mostrar una paleta de colores.</span><span class="sxs-lookup"><span data-stu-id="45a13-115">Select the **Custom** tab to display a palette of colors.</span></span>  
  
4.  <span data-ttu-id="45a13-116">Seleccione el **Web** o **sistema** ficha para mostrar una lista de nombres de colores predefinidos y, a continuación, seleccione un color.</span><span class="sxs-lookup"><span data-stu-id="45a13-116">Select the **Web** or **System** tab to display a list of predefined names for colors, and then select a color.</span></span>  
  
5.  <span data-ttu-id="45a13-117">En el **propiedades** ventana, haga clic en el botón de flecha situado junto a la <xref:System.Windows.Forms.Control.BackgroundImage%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="45a13-117">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span>  
  
6.  <span data-ttu-id="45a13-118">En el **abierto** cuadro de diálogo, seleccione el archivo que desea mostrar.</span><span class="sxs-lookup"><span data-stu-id="45a13-118">In the **Open** dialog box, select the file that you want to display.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45a13-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="45a13-119">See Also</span></span>  
 <xref:System.Windows.Forms.Control.BackColor%2A>  
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>  
 [<span data-ttu-id="45a13-120">Panel (control)</span><span class="sxs-lookup"><span data-stu-id="45a13-120">Panel Control</span></span>](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)  
 [<span data-ttu-id="45a13-121">Información general del control Panel</span><span class="sxs-lookup"><span data-stu-id="45a13-121">Panel Control Overview</span></span>](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [<span data-ttu-id="45a13-122">Agrupar controles con el control Panel de Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="45a13-122">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/group-controls-with-wf-panel-control-using-the-designer.md)

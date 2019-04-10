---
title: Filtrar para agrupar controles con el control Panel de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
ms.openlocfilehash: 1a3fcac56df1328c12d7a5dcb542138afdb486f5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59214837"
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a><span data-ttu-id="3a194-102">Filtrar para agrupar controles con el control Panel de formularios Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="3a194-102">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>
<span data-ttu-id="3a194-103">Windows Forms <xref:System.Windows.Forms.Panel> controles se usan para agrupar otros controles.</span><span class="sxs-lookup"><span data-stu-id="3a194-103">Windows Forms <xref:System.Windows.Forms.Panel> controls are used to group other controls.</span></span> <span data-ttu-id="3a194-104">Existen tres razones para agrupar controles.</span><span class="sxs-lookup"><span data-stu-id="3a194-104">There are three reasons to group controls.</span></span> <span data-ttu-id="3a194-105">Para agrupar elementos de formulario relacionados para una interfaz de usuario clara; forma visual otra es mediante programación de agrupación, de botones de radio, por ejemplo; el último es para mover los controles como una unidad de tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="3a194-105">One is visual grouping of related form elements for a clear user interface; another is programmatic grouping, of radio buttons for example; the last is for moving the controls as a unit at design time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a194-106">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="3a194-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="3a194-107">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="3a194-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="3a194-108">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="3a194-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="3a194-109">Para crear un grupo de controles</span><span class="sxs-lookup"><span data-stu-id="3a194-109">To create a group of controls</span></span>  
  
1.  <span data-ttu-id="3a194-110">Arrastre un <xref:System.Windows.Forms.Panel> controlar desde la **Windows Forms** ficha del cuadro de herramientas hasta un formulario.</span><span class="sxs-lookup"><span data-stu-id="3a194-110">Drag a <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab of the Toolbox onto a form.</span></span>  
  
2.  <span data-ttu-id="3a194-111">Agregue otros controles al panel, cada uno dentro del panel de dibujo.</span><span class="sxs-lookup"><span data-stu-id="3a194-111">Add other controls to the panel, drawing each inside the panel.</span></span>  
  
     <span data-ttu-id="3a194-112">Si tiene controles que desee incluir en un panel, puede seleccionar todos los controles, cortarlos en el Portapapeles, seleccione el <xref:System.Windows.Forms.Panel> controlar y, a continuación, péguelos en el panel.</span><span class="sxs-lookup"><span data-stu-id="3a194-112">If you have existing controls that you want to enclose in a panel, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.Panel> control, and then paste them into the panel.</span></span> <span data-ttu-id="3a194-113">También puede arrastrar al panel.</span><span class="sxs-lookup"><span data-stu-id="3a194-113">You can also drag them into the panel.</span></span>  
  
3.  <span data-ttu-id="3a194-114">(Opcional) Si desea agregar un borde a un panel, establezca su <xref:System.Windows.Forms.BorderStyle> propiedad.</span><span class="sxs-lookup"><span data-stu-id="3a194-114">(Optional) If you want to add a border to a panel, set its <xref:System.Windows.Forms.BorderStyle> property.</span></span> <span data-ttu-id="3a194-115">Hay tres opciones: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, y <xref:System.Windows.Forms.BorderStyle.None>.</span><span class="sxs-lookup"><span data-stu-id="3a194-115">There are three choices: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, and <xref:System.Windows.Forms.BorderStyle.None>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a194-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a194-116">See also</span></span>

- [<span data-ttu-id="3a194-117">Control Panel</span><span class="sxs-lookup"><span data-stu-id="3a194-117">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="3a194-118">Información general sobre el control Panel</span><span class="sxs-lookup"><span data-stu-id="3a194-118">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="3a194-119">Filtrar para establecer el fondo de un control Panel</span><span class="sxs-lookup"><span data-stu-id="3a194-119">How to: Set the Background of a Panel</span></span>](how-to-set-the-background-of-a-windows-forms-panel.md)

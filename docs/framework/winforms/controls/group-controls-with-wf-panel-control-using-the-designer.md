---
title: 'Cómo: Agrupar controles con el control Panel de Windows Forms mediante el Diseñador'
ms.date: 03/30/2017
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
ms.openlocfilehash: 1cf4519a9aaaa1c4f0df321ab38c3f543c87b2a2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525628"
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a><span data-ttu-id="efc9a-102">Cómo: Agrupar controles con el control Panel de Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="efc9a-102">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>
<span data-ttu-id="efc9a-103">Formularios Windows Forms <xref:System.Windows.Forms.Panel> controles se utilizan para agrupar otros controles.</span><span class="sxs-lookup"><span data-stu-id="efc9a-103">Windows Forms <xref:System.Windows.Forms.Panel> controls are used to group other controls.</span></span> <span data-ttu-id="efc9a-104">Hay tres razones para agrupar controles.</span><span class="sxs-lookup"><span data-stu-id="efc9a-104">There are three reasons to group controls.</span></span> <span data-ttu-id="efc9a-105">Uno es visual de agrupación de elementos de formulario relacionados para una interfaz de usuario clara; otra razón es la programación de agrupación, de botones de radio, por ejemplo, el último es para mover los controles como una unidad en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="efc9a-105">One is visual grouping of related form elements for a clear user interface; another is programmatic grouping, of radio buttons for example; the last is for moving the controls as a unit at design time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="efc9a-106">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="efc9a-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="efc9a-107">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="efc9a-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="efc9a-108">Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="efc9a-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="efc9a-109">Para crear un grupo de controles</span><span class="sxs-lookup"><span data-stu-id="efc9a-109">To create a group of controls</span></span>  
  
1.  <span data-ttu-id="efc9a-110">Arrastre un <xref:System.Windows.Forms.Panel> controlar desde la **formularios Windows Forms** ficha del cuadro de herramientas hasta un formulario.</span><span class="sxs-lookup"><span data-stu-id="efc9a-110">Drag a <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab of the Toolbox onto a form.</span></span>  
  
2.  <span data-ttu-id="efc9a-111">Agregar otros controles al panel, cada uno de ellos dentro del panel de dibujo.</span><span class="sxs-lookup"><span data-stu-id="efc9a-111">Add other controls to the panel, drawing each inside the panel.</span></span>  
  
     <span data-ttu-id="efc9a-112">Si dispone de los controles existentes que desee incluir en un panel, puede seleccionar todos los controles, como cortar a ellos en el Portapapeles, seleccione la <xref:System.Windows.Forms.Panel> de control y, a continuación, pegarlos en el panel.</span><span class="sxs-lookup"><span data-stu-id="efc9a-112">If you have existing controls that you want to enclose in a panel, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.Panel> control, and then paste them into the panel.</span></span> <span data-ttu-id="efc9a-113">También puede arrastrar al panel.</span><span class="sxs-lookup"><span data-stu-id="efc9a-113">You can also drag them into the panel.</span></span>  
  
3.  <span data-ttu-id="efc9a-114">(Opcional) Si desea agregar un borde a un panel, establezca su <xref:System.Windows.Forms.BorderStyle> propiedad.</span><span class="sxs-lookup"><span data-stu-id="efc9a-114">(Optional) If you want to add a border to a panel, set its <xref:System.Windows.Forms.BorderStyle> property.</span></span> <span data-ttu-id="efc9a-115">Hay tres opciones: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, y <xref:System.Windows.Forms.BorderStyle.None>.</span><span class="sxs-lookup"><span data-stu-id="efc9a-115">There are three choices: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, and <xref:System.Windows.Forms.BorderStyle.None>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efc9a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="efc9a-116">See Also</span></span>  
 [<span data-ttu-id="efc9a-117">Panel (control)</span><span class="sxs-lookup"><span data-stu-id="efc9a-117">Panel Control</span></span>](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)  
 [<span data-ttu-id="efc9a-118">Información general del control Panel</span><span class="sxs-lookup"><span data-stu-id="efc9a-118">Panel Control Overview</span></span>](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [<span data-ttu-id="efc9a-119">Establecer el fondo de un panel</span><span class="sxs-lookup"><span data-stu-id="efc9a-119">How to: Set the Background of a Panel</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md)

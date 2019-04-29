---
title: Procedimiento para agregar y quitar fichas con el control TabControl de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabPage control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 480633db-413a-45d2-9c8f-0427cc13adbe
ms.openlocfilehash: 23fe9fa2b8405a6ebe66e8f0cee1d81d45f2395b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61640378"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol-using-the-designer"></a><span data-ttu-id="6ed87-102">Procedimiento para agregar y quitar fichas con el control TabControl de formularios Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="6ed87-102">How to: Add and Remove Tabs with the Windows Forms TabControl Using the Designer</span></span>
<span data-ttu-id="6ed87-103">Cuando coloca un <xref:System.Windows.Forms.TabControl> control en el formulario, contiene dos pestañas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6ed87-103">When you place a <xref:System.Windows.Forms.TabControl> control on your form, it contains two tabs by default.</span></span> <span data-ttu-id="6ed87-104">Puede agregar o quitar fichas mediante el diseñador.</span><span class="sxs-lookup"><span data-stu-id="6ed87-104">You can add or remove tabs using the designer.</span></span>  
  
 <span data-ttu-id="6ed87-105">El procedimiento siguiente requiere una **aplicación Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.TabControl> control.</span><span class="sxs-lookup"><span data-stu-id="6ed87-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TabControl> control.</span></span> <span data-ttu-id="6ed87-106">Para obtener información acerca de cómo configurar un proyecto de este tipo, vea [Cómo: Cree un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="6ed87-106">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ed87-107">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="6ed87-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="6ed87-108">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="6ed87-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="6ed87-109">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="6ed87-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-or-remove-a-tab-using-the-designer"></a><span data-ttu-id="6ed87-110">Para agregar o quitar una pestaña con el diseñador</span><span class="sxs-lookup"><span data-stu-id="6ed87-110">To add or remove a tab using the designer</span></span>  
  
- <span data-ttu-id="6ed87-111">En la etiqueta inteligente del control, haga clic en **Agregar pestaña** o **Quitar ficha**</span><span class="sxs-lookup"><span data-stu-id="6ed87-111">On the control's smart tag, click **Add Tab** or **Remove Tab**</span></span>  
  
     <span data-ttu-id="6ed87-112">-o bien-</span><span class="sxs-lookup"><span data-stu-id="6ed87-112">-or-</span></span>  
  
     <span data-ttu-id="6ed87-113">En el **propiedades** ventana, haga clic en el **puntos suspensivos** botón (![de pantalla de VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) junto a el <xref:System.Windows.Forms.TabControl.TabPages%2A> propiedad para abrir el **Editor de la colección TabPage**.</span><span class="sxs-lookup"><span data-stu-id="6ed87-113">In the **Properties** window, click the **Ellipsis** button (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.TabControl.TabPages%2A> property to open the **TabPage Collection Editor**.</span></span> <span data-ttu-id="6ed87-114">Haga clic en el **agregar** o **quitar** botón.</span><span class="sxs-lookup"><span data-stu-id="6ed87-114">Click the **Add** or **Remove** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ed87-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ed87-115">See also</span></span>

- [<span data-ttu-id="6ed87-116">TabControl (control)</span><span class="sxs-lookup"><span data-stu-id="6ed87-116">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="6ed87-117">Información general del control TabControl</span><span class="sxs-lookup"><span data-stu-id="6ed87-117">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="6ed87-118">Cómo: Agregar un Control a una página de ficha</span><span class="sxs-lookup"><span data-stu-id="6ed87-118">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="6ed87-119">Cómo: Deshabilitar páginas de fichas</span><span class="sxs-lookup"><span data-stu-id="6ed87-119">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="6ed87-120">Cómo: Cambiar la apariencia del control TabControl de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="6ed87-120">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)

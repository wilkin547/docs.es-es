---
title: "Cómo: Agregar y quitar fichas de un control TabControl de formularios Windows Forms mediante el Diseñador"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabPage control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 480633db-413a-45d2-9c8f-0427cc13adbe
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 666cade349220e9975a5770328e03db0e948d7d1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol-using-the-designer"></a><span data-ttu-id="f2b98-102">Cómo: Agregar y quitar fichas de un control TabControl de formularios Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="f2b98-102">How to: Add and Remove Tabs with the Windows Forms TabControl Using the Designer</span></span>
<span data-ttu-id="f2b98-103">Cuando coloca un <xref:System.Windows.Forms.TabControl> control en el formulario, contiene dos pestañas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f2b98-103">When you place a <xref:System.Windows.Forms.TabControl> control on your form, it contains two tabs by default.</span></span> <span data-ttu-id="f2b98-104">Puede agregar o quitar fichas mediante el diseñador.</span><span class="sxs-lookup"><span data-stu-id="f2b98-104">You can add or remove tabs using the designer.</span></span>  
  
 <span data-ttu-id="f2b98-105">El procedimiento siguiente requiere un **aplicación de Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.TabControl> control.</span><span class="sxs-lookup"><span data-stu-id="f2b98-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TabControl> control.</span></span> <span data-ttu-id="f2b98-106">Para obtener información acerca de cómo configurar un proyecto de este tipo, consulte [Cómo: crear un proyecto de aplicación de Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="f2b98-106">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2b98-107">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="f2b98-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f2b98-108">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="f2b98-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f2b98-109">Para obtener más información, consulte [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="f2b98-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-or-remove-a-tab-using-the-designer"></a><span data-ttu-id="f2b98-110">Para agregar o quitar una ficha mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="f2b98-110">To add or remove a tab using the designer</span></span>  
  
-   <span data-ttu-id="f2b98-111">En las etiquetas inteligentes del control, haga clic en **Agregar pestaña** o **Quitar ficha**</span><span class="sxs-lookup"><span data-stu-id="f2b98-111">On the control's smart tag, click **Add Tab** or **Remove Tab**</span></span>  
  
     <span data-ttu-id="f2b98-112">O bien</span><span class="sxs-lookup"><span data-stu-id="f2b98-112">-or-</span></span>  
  
     <span data-ttu-id="f2b98-113">En el **propiedades** ventana, haga clic en el **puntos suspensivos** botón (![de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) junto a el <xref:System.Windows.Forms.TabControl.TabPages%2A> propiedad para abrir el **Editor de la colección TabPage**.</span><span class="sxs-lookup"><span data-stu-id="f2b98-113">In the **Properties** window, click the **Ellipsis** button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.TabControl.TabPages%2A> property to open the **TabPage Collection Editor**.</span></span> <span data-ttu-id="f2b98-114">Haga clic en el **agregar** o **quitar** botón.</span><span class="sxs-lookup"><span data-stu-id="f2b98-114">Click the **Add** or **Remove** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2b98-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2b98-115">See Also</span></span>  
 [<span data-ttu-id="f2b98-116">TabControl (control)</span><span class="sxs-lookup"><span data-stu-id="f2b98-116">TabControl Control</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)  
 [<span data-ttu-id="f2b98-117">Información general del control TabControl</span><span class="sxs-lookup"><span data-stu-id="f2b98-117">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="f2b98-118">Agregar un control a una página de fichas</span><span class="sxs-lookup"><span data-stu-id="f2b98-118">How to: Add a Control to a Tab Page</span></span>](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [<span data-ttu-id="f2b98-119">Deshabilitar páginas de ficha</span><span class="sxs-lookup"><span data-stu-id="f2b98-119">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [<span data-ttu-id="f2b98-120">Cambiar la apariencia del control TabControl de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f2b98-120">How to: Change the Appearance of the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)

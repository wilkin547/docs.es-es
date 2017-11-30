---
title: "Cómo: Crear formularios principales MDI"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parent forms
- MDI [Windows Forms], creating forms
ms.assetid: 12c71221-2377-4bb6-b10b-7b4b300fd462
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f768e01981f75e5e322fd984e73ccf7b185c5e20
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-mdi-parent-forms"></a><span data-ttu-id="c703e-102">Cómo: Crear formularios principales MDI</span><span class="sxs-lookup"><span data-stu-id="c703e-102">How to: Create MDI Parent Forms</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="c703e-103">En este tema se usa el control <xref:System.Windows.Forms.MainMenu>, que se ha reemplazado por el control <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="c703e-103">This topic uses the <xref:System.Windows.Forms.MainMenu> control, which has been replaced by the <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="c703e-104">El control <xref:System.Windows.Forms.MainMenu> se conserva por razones de compatibilidad con versiones anteriores y uso en el futuro, si así lo decide.</span><span class="sxs-lookup"><span data-stu-id="c703e-104">The <xref:System.Windows.Forms.MainMenu> control is retained for both backward compatibility and future use, if you choose.</span></span>  <span data-ttu-id="c703e-105">Para obtener información acerca de cómo crear una MDI formulario primario mediante el uso de un <xref:System.Windows.Forms.MenuStrip>, consulte [Cómo: crear una lista de ventanas MDI con MenuStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="c703e-105">For information about creating a MDI parent Form by using a <xref:System.Windows.Forms.MenuStrip>, see [How to: Create an MDI Window List with MenuStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md).</span></span>  
  
 <span data-ttu-id="c703e-106">La base de una aplicación de interfaz de múltiples documentos (MDI) es el formulario primario MDI.</span><span class="sxs-lookup"><span data-stu-id="c703e-106">The foundation of a Multiple-Document Interface (MDI) application is the MDI parent form.</span></span> <span data-ttu-id="c703e-107">Se trata del formulario que contiene las ventanas secundarias de MDI, que son las subventanas donde el usuario interactúa con la aplicación MDI.</span><span class="sxs-lookup"><span data-stu-id="c703e-107">This is the form that contains the MDI child windows, which are the sub-windows wherein the user interacts with the MDI application.</span></span> <span data-ttu-id="c703e-108">Crear un formulario primario MDI es fácil, tanto en el Diseñador de Windows Forms como mediante programación.</span><span class="sxs-lookup"><span data-stu-id="c703e-108">Creating an MDI parent form is easy, both in the Windows Forms Designer and programmatically.</span></span>  
  
### <a name="to-create-an-mdi-parent-form-at-design-time"></a><span data-ttu-id="c703e-109">Para crear un formulario primario MDI en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="c703e-109">To create an MDI parent form at design time</span></span>  
  
1.  <span data-ttu-id="c703e-110">Cree un proyecto de aplicación para Windows.</span><span class="sxs-lookup"><span data-stu-id="c703e-110">Create a Windows Application project.</span></span>  
  
2.  <span data-ttu-id="c703e-111">En el **propiedades** ventana, establezca el <xref:System.Windows.Forms.Form.IsMdiContainer%2A> propiedad **true**.</span><span class="sxs-lookup"><span data-stu-id="c703e-111">In the **Properties** window, set the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to **true**.</span></span>  
  
     <span data-ttu-id="c703e-112">Esto hace que el formulario se designe como contenedor MDI de las ventanas secundarias.</span><span class="sxs-lookup"><span data-stu-id="c703e-112">This designates the form as an MDI container for child windows.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c703e-113">Mientras configura las propiedades en la ventana **Propiedades**, también puede establecer la propiedad `WindowState` en **Maximizado**, si lo desea, ya que esto facilita la manipulación de las ventanas secundarias de MDI cuando el formulario primario está maximizado.</span><span class="sxs-lookup"><span data-stu-id="c703e-113">While setting properties in the **Properties** window, you can also set the `WindowState` property to **Maximized**, if you like, as it is easiest to manipulate MDI child windows when the parent form is maximized.</span></span> <span data-ttu-id="c703e-114">Además, tenga en cuenta que el borde del formulario primario MDI seleccionará el color del sistema (definido en el Panel de Control del sistema Windows), y no el color de fondo que haya establecido en la propiedad <xref:System.Windows.Forms.Control.BackColor%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c703e-114">Additionally, be aware that the edge of the MDI parent form will pick up the system color (set in the Windows System Control Panel), rather than the back color you set using the <xref:System.Windows.Forms.Control.BackColor%2A?displayProperty=nameWithType> property.</span></span>  
  
3.  <span data-ttu-id="c703e-115">En el **Cuadro de herramientas**, arrastre un control **MenuStrip** al formulario.</span><span class="sxs-lookup"><span data-stu-id="c703e-115">From the **Toolbox**, drag a **MenuStrip** control to the form.</span></span> <span data-ttu-id="c703e-116">Cree un elemento de menú de nivel superior con la propiedad **Text** establecida en **&Archivo** con los elementos de submenú **&Nuevo** y **&Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="c703e-116">Create a top-level menu item with the **Text** property set to **&File** with submenu items called **&New** and **&Close**.</span></span> <span data-ttu-id="c703e-117">Cree también un elemento de menú de nivel superior **&Ventana**.</span><span class="sxs-lookup"><span data-stu-id="c703e-117">Also create a top-level menu item called **&Window**.</span></span>  
  
     <span data-ttu-id="c703e-118">El primer menú creará y ocultará los elementos de menú en tiempo de ejecución, mientras que el segundo realizará un seguimiento de las ventanas secundarias de MDI abiertas.</span><span class="sxs-lookup"><span data-stu-id="c703e-118">The first menu will create and hide menu items at run time, and the second menu will keep track of the open MDI child windows.</span></span> <span data-ttu-id="c703e-119">Llegado este punto, habrá creado una ventana primaria de MDI.</span><span class="sxs-lookup"><span data-stu-id="c703e-119">At this point, you have created an MDI parent window.</span></span>  
  
4.  <span data-ttu-id="c703e-120">Presione **F5** para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c703e-120">Press **F5** to run the application.</span></span> <span data-ttu-id="c703e-121">Para más información acerca de cómo crear ventanas secundarias de MDI que funcionen dentro del formulario primario MDI, vea [Cómo: Crear formularios MDI secundarios](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md).</span><span class="sxs-lookup"><span data-stu-id="c703e-121">For information about creating MDI child windows that operate within the MDI parent form, see [How to: Create MDI Child Forms](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c703e-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="c703e-122">See Also</span></span>  
 [<span data-ttu-id="c703e-123">Aplicaciones de interfaz de múltiples documentos (MDI)</span><span class="sxs-lookup"><span data-stu-id="c703e-123">Multiple-Document Interface (MDI) Applications</span></span>](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)  
 [<span data-ttu-id="c703e-124">Crear formularios MDI secundarios</span><span class="sxs-lookup"><span data-stu-id="c703e-124">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [<span data-ttu-id="c703e-125">Determinar el formulario secundario MDI activo</span><span class="sxs-lookup"><span data-stu-id="c703e-125">How to: Determine the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 [<span data-ttu-id="c703e-126">Enviar datos al formulario secundario MDI activo</span><span class="sxs-lookup"><span data-stu-id="c703e-126">How to: Send Data to the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)  
 [<span data-ttu-id="c703e-127">Cómo: Organizar formularios MDI secundarios</span><span class="sxs-lookup"><span data-stu-id="c703e-127">How to: Arrange MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)

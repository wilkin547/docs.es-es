---
title: Procedimiento para crear formularios principales MDI
description: Obtenga información sobre cómo crear un formulario MDI primario mediante programación y mediante el Diseñador de Windows Forms.
ms.date: 03/30/2017
helpviewer_keywords:
- parent forms
- MDI [Windows Forms], creating forms
ms.assetid: 12c71221-2377-4bb6-b10b-7b4b300fd462
ms.openlocfilehash: d387837a565ca247f62828c19f353990b35117c7
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174710"
---
# <a name="how-to-create-mdi-parent-forms"></a><span data-ttu-id="96125-103">Procedimiento para crear formularios principales MDI</span><span class="sxs-lookup"><span data-stu-id="96125-103">How to: Create MDI Parent Forms</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96125-104">En este tema se usa el control <xref:System.Windows.Forms.MainMenu>, que se ha reemplazado por el control <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="96125-104">This topic uses the <xref:System.Windows.Forms.MainMenu> control, which has been replaced by the <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="96125-105">El control <xref:System.Windows.Forms.MainMenu> se conserva por razones de compatibilidad con versiones anteriores y uso en el futuro, si así lo decide.</span><span class="sxs-lookup"><span data-stu-id="96125-105">The <xref:System.Windows.Forms.MainMenu> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="96125-106">Para obtener información acerca de cómo crear un formulario MDI primario mediante un <xref:System.Windows.Forms.MenuStrip> , consulte [Cómo: crear una lista de ventanas MDI con MenuStrip](../controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="96125-106">For information about creating a MDI parent Form by using a <xref:System.Windows.Forms.MenuStrip>, see [How to: Create an MDI Window List with MenuStrip](../controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md).</span></span>

<span data-ttu-id="96125-107">La base de una aplicación de interfaz de múltiples documentos (MDI) es el formulario primario MDI.</span><span class="sxs-lookup"><span data-stu-id="96125-107">The foundation of a Multiple-Document Interface (MDI) application is the MDI parent form.</span></span> <span data-ttu-id="96125-108">Se trata del formulario que contiene las ventanas secundarias de MDI, que son las subventanas donde el usuario interactúa con la aplicación MDI.</span><span class="sxs-lookup"><span data-stu-id="96125-108">This is the form that contains the MDI child windows, which are the sub-windows wherein the user interacts with the MDI application.</span></span> <span data-ttu-id="96125-109">Crear un formulario primario MDI es fácil, tanto en el Diseñador de Windows Forms como mediante programación.</span><span class="sxs-lookup"><span data-stu-id="96125-109">Creating an MDI parent form is easy, both in the Windows Forms Designer and programmatically.</span></span>

## <a name="create-an-mdi-parent-form-at-design-time"></a><span data-ttu-id="96125-110">Crear un formulario primario MDI en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="96125-110">Create an MDI parent form at design time</span></span>

1. <span data-ttu-id="96125-111">Cree un proyecto de aplicación para Windows en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="96125-111">Create a Windows Application project in Visual Studio.</span></span>

2. <span data-ttu-id="96125-112">En la ventana **propiedades** , establezca la <xref:System.Windows.Forms.Form.IsMdiContainer%2A> propiedad en **true**.</span><span class="sxs-lookup"><span data-stu-id="96125-112">In the **Properties** window, set the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to **true**.</span></span>

     <span data-ttu-id="96125-113">Esto hace que el formulario se designe como contenedor MDI de las ventanas secundarias.</span><span class="sxs-lookup"><span data-stu-id="96125-113">This designates the form as an MDI container for child windows.</span></span>

    > [!NOTE]
    > <span data-ttu-id="96125-114">Mientras configura las propiedades en la ventana **Propiedades**, también puede establecer la propiedad `WindowState` en **Maximizado**, si lo desea, ya que esto facilita la manipulación de las ventanas secundarias de MDI cuando el formulario primario está maximizado.</span><span class="sxs-lookup"><span data-stu-id="96125-114">While setting properties in the **Properties** window, you can also set the `WindowState` property to **Maximized**, if you like, as it is easiest to manipulate MDI child windows when the parent form is maximized.</span></span> <span data-ttu-id="96125-115">Además, tenga en cuenta que el borde del formulario primario MDI seleccionará el color del sistema (definido en el Panel de Control del sistema Windows), y no el color de fondo que haya establecido en la propiedad <xref:System.Windows.Forms.Control.BackColor%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="96125-115">Additionally, be aware that the edge of the MDI parent form will pick up the system color (set in the Windows System Control Panel), rather than the back color you set using the <xref:System.Windows.Forms.Control.BackColor%2A?displayProperty=nameWithType> property.</span></span>

3. <span data-ttu-id="96125-116">En el **Cuadro de herramientas**, arrastre un control **MenuStrip** al formulario.</span><span class="sxs-lookup"><span data-stu-id="96125-116">From the **Toolbox**, drag a **MenuStrip** control to the form.</span></span> <span data-ttu-id="96125-117">Cree un elemento de menú de nivel superior con la propiedad **Text** establecida en **&Archivo** con los elementos de submenú **&Nuevo** y **&Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="96125-117">Create a top-level menu item with the **Text** property set to **&File** with submenu items called **&New** and **&Close**.</span></span> <span data-ttu-id="96125-118">Cree también un elemento de menú de nivel superior **&Ventana**.</span><span class="sxs-lookup"><span data-stu-id="96125-118">Also create a top-level menu item called **&Window**.</span></span>

     <span data-ttu-id="96125-119">El primer menú creará y ocultará los elementos de menú en tiempo de ejecución, mientras que el segundo realizará un seguimiento de las ventanas secundarias de MDI abiertas.</span><span class="sxs-lookup"><span data-stu-id="96125-119">The first menu will create and hide menu items at run time, and the second menu will keep track of the open MDI child windows.</span></span> <span data-ttu-id="96125-120">Llegado este punto, habrá creado una ventana primaria de MDI.</span><span class="sxs-lookup"><span data-stu-id="96125-120">At this point, you have created an MDI parent window.</span></span>

4. <span data-ttu-id="96125-121">Presione **F5** para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="96125-121">Press **F5** to run the application.</span></span> <span data-ttu-id="96125-122">Para más información acerca de cómo crear ventanas secundarias de MDI que funcionen dentro del formulario primario MDI, vea [Cómo: Crear formularios MDI secundarios](how-to-create-mdi-child-forms.md).</span><span class="sxs-lookup"><span data-stu-id="96125-122">For information about creating MDI child windows that operate within the MDI parent form, see [How to: Create MDI Child Forms](how-to-create-mdi-child-forms.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="96125-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="96125-123">See also</span></span>

- [<span data-ttu-id="96125-124">Aplicaciones de interfaz de múltiples documentos (MDI)</span><span class="sxs-lookup"><span data-stu-id="96125-124">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="96125-125">Procedimiento para crear formularios secundarios MDI</span><span class="sxs-lookup"><span data-stu-id="96125-125">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="96125-126">Procedimiento para determinar el formulario secundario MDI activo</span><span class="sxs-lookup"><span data-stu-id="96125-126">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)
- [<span data-ttu-id="96125-127">Procedimiento para enviar datos al formulario secundario MDI activo</span><span class="sxs-lookup"><span data-stu-id="96125-127">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="96125-128">Procedimiento para organizar formularios secundarios MDI</span><span class="sxs-lookup"><span data-stu-id="96125-128">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)

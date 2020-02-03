---
title: Cambiar la apariencia de TabControl
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- icons [Windows Forms], displaying on tabs
- TabControl control [Windows Forms], changing page appearance
- tabs [Windows Forms], controlling appearance
- buttons [Windows Forms], displaying tabs as
ms.assetid: 7c6cc443-ed62-4d26-b94d-b8913b44f773
ms.openlocfilehash: 056070177e6bbaba0c93c7b94f5adfd7887be6a8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746614"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-tabcontrol"></a><span data-ttu-id="e85a3-102">Cómo: Cambiar la apariencia del control TabControl de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e85a3-102">How to: Change the Appearance of the Windows Forms TabControl</span></span>
<span data-ttu-id="e85a3-103">Puede cambiar la apariencia de las pestañas en Windows Forms mediante las propiedades de los <xref:System.Windows.Forms.TabControl> y los objetos <xref:System.Windows.Forms.TabPage> que componen las pestañas individuales en el control.</span><span class="sxs-lookup"><span data-stu-id="e85a3-103">You can change the appearance of tabs in Windows Forms by using properties of the <xref:System.Windows.Forms.TabControl> and the <xref:System.Windows.Forms.TabPage> objects that make up the individual tabs on the control.</span></span> <span data-ttu-id="e85a3-104">Al establecer estas propiedades, puede mostrar imágenes en las pestañas, mostrar las pestañas verticalmente en lugar de hacerlo horizontalmente, mostrar varias filas de pestañas y habilitar o deshabilitar las fichas mediante programación.</span><span class="sxs-lookup"><span data-stu-id="e85a3-104">By setting these properties, you can display images on tabs, display tabs vertically instead of horizontally, display multiple rows of tabs, and enable or disable tabs programmatically.</span></span>  
  
### <a name="to-display-an-icon-on-the-label-part-of-a-tab"></a><span data-ttu-id="e85a3-105">Para mostrar un icono en la parte de etiqueta de una pestaña</span><span class="sxs-lookup"><span data-stu-id="e85a3-105">To display an icon on the label part of a tab</span></span>  
  
1. <span data-ttu-id="e85a3-106">Agregue un control <xref:System.Windows.Forms.ImageList> al formulario.</span><span class="sxs-lookup"><span data-stu-id="e85a3-106">Add an <xref:System.Windows.Forms.ImageList> control to the form.</span></span>  
  
2. <span data-ttu-id="e85a3-107">Agregue imágenes a la lista de imágenes.</span><span class="sxs-lookup"><span data-stu-id="e85a3-107">Add images to the image list.</span></span>  
  
     <span data-ttu-id="e85a3-108">Para obtener más información sobre las listas de imágenes, vea [ImageList (componente](imagelist-component-windows-forms.md) ) y [Cómo: agregar o quitar imágenes con el componente ImageList de Windows Forms](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="e85a3-108">For more information about image lists, see [ImageList Component](imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
3. <span data-ttu-id="e85a3-109">Establezca la propiedad <xref:System.Windows.Forms.TabControl.ImageList%2A> del <xref:System.Windows.Forms.TabControl> en el control <xref:System.Windows.Forms.ImageList>.</span><span class="sxs-lookup"><span data-stu-id="e85a3-109">Set the <xref:System.Windows.Forms.TabControl.ImageList%2A> property of the <xref:System.Windows.Forms.TabControl> to the <xref:System.Windows.Forms.ImageList> control.</span></span>  
  
4. <span data-ttu-id="e85a3-110">Establezca la propiedad <xref:System.Windows.Forms.TabPage.ImageIndex%2A> del <xref:System.Windows.Forms.TabPage> en el índice de una imagen adecuada de la lista.</span><span class="sxs-lookup"><span data-stu-id="e85a3-110">Set the <xref:System.Windows.Forms.TabPage.ImageIndex%2A> property of the <xref:System.Windows.Forms.TabPage> to the index of an appropriate image in the list.</span></span>  
  
### <a name="to-create-multiple-rows-of-tabs"></a><span data-ttu-id="e85a3-111">Para crear varias filas de pestañas</span><span class="sxs-lookup"><span data-stu-id="e85a3-111">To create multiple rows of tabs</span></span>  
  
1. <span data-ttu-id="e85a3-112">Agregue el número de páginas de fichas que desee.</span><span class="sxs-lookup"><span data-stu-id="e85a3-112">Add the number of tab pages you want.</span></span>  
  
2. <span data-ttu-id="e85a3-113">Establezca la propiedad <xref:System.Windows.Forms.TabControl.Multiline%2A> de la <xref:System.Windows.Forms.TabControl> en `true`.</span><span class="sxs-lookup"><span data-stu-id="e85a3-113">Set the <xref:System.Windows.Forms.TabControl.Multiline%2A> property of the <xref:System.Windows.Forms.TabControl> to `true`.</span></span>  
  
3. <span data-ttu-id="e85a3-114">Si las pestañas no aparecen en varias filas, establezca la propiedad <xref:System.Windows.Forms.Control.Width%2A> del <xref:System.Windows.Forms.TabControl> para que sea más estrecha que todas las pestañas.</span><span class="sxs-lookup"><span data-stu-id="e85a3-114">If the tabs do not already appear in multiple rows, set the <xref:System.Windows.Forms.Control.Width%2A> property of the <xref:System.Windows.Forms.TabControl> to be narrower than all the tabs.</span></span>  
  
### <a name="to-arrange-tabs-on-the-side-of-the-control"></a><span data-ttu-id="e85a3-115">Para organizar las pestañas en el lateral del control</span><span class="sxs-lookup"><span data-stu-id="e85a3-115">To arrange tabs on the side of the control</span></span>  
  
- <span data-ttu-id="e85a3-116">Establezca la propiedad <xref:System.Windows.Forms.TabControl.Alignment%2A> de la <xref:System.Windows.Forms.TabControl> en <xref:System.Windows.Forms.TabAlignment.Left> o <xref:System.Windows.Forms.TabAlignment.Right>.</span><span class="sxs-lookup"><span data-stu-id="e85a3-116">Set the <xref:System.Windows.Forms.TabControl.Alignment%2A> property of the <xref:System.Windows.Forms.TabControl> to <xref:System.Windows.Forms.TabAlignment.Left> or <xref:System.Windows.Forms.TabAlignment.Right>.</span></span>  
  
### <a name="to-programmatically-enable-or-disable-all-controls-on-a-tab"></a><span data-ttu-id="e85a3-117">Para habilitar o deshabilitar todos los controles en una pestaña mediante programación</span><span class="sxs-lookup"><span data-stu-id="e85a3-117">To programmatically enable or disable all controls on a tab</span></span>  
  
1. <span data-ttu-id="e85a3-118">Establezca la propiedad <xref:System.Windows.Forms.TabPage.Enabled%2A> de la <xref:System.Windows.Forms.TabPage> en `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="e85a3-118">Set the <xref:System.Windows.Forms.TabPage.Enabled%2A> property of the <xref:System.Windows.Forms.TabPage> to `true` or `false`.</span></span>  
  
    ```vb  
    TabPage1.Enabled = False  
    ```  
  
    ```csharp  
    tabPage1.Enabled = false;  
    ```  
  
    ```cpp  
    tabPage1->Enabled = false;  
    ```  
  
### <a name="to-display-tabs-as-buttons"></a><span data-ttu-id="e85a3-119">Para mostrar las pestañas como botones</span><span class="sxs-lookup"><span data-stu-id="e85a3-119">To display tabs as buttons</span></span>  
  
- <span data-ttu-id="e85a3-120">Establezca la propiedad <xref:System.Windows.Forms.TabControl.Appearance%2A> de la <xref:System.Windows.Forms.TabControl> en <xref:System.Windows.Forms.TabAppearance.Buttons> o <xref:System.Windows.Forms.TabAppearance.FlatButtons>.</span><span class="sxs-lookup"><span data-stu-id="e85a3-120">Set the <xref:System.Windows.Forms.TabControl.Appearance%2A> property of the <xref:System.Windows.Forms.TabControl> to <xref:System.Windows.Forms.TabAppearance.Buttons> or <xref:System.Windows.Forms.TabAppearance.FlatButtons>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e85a3-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e85a3-121">See also</span></span>

- [<span data-ttu-id="e85a3-122">TabControl (control)</span><span class="sxs-lookup"><span data-stu-id="e85a3-122">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="e85a3-123">Información general del control TabControl</span><span class="sxs-lookup"><span data-stu-id="e85a3-123">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="e85a3-124">Agregar un control a una página de fichas</span><span class="sxs-lookup"><span data-stu-id="e85a3-124">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="e85a3-125">Deshabilitar páginas de ficha</span><span class="sxs-lookup"><span data-stu-id="e85a3-125">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="e85a3-126">Agregar y quitar fichas con el control TabControl de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e85a3-126">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)

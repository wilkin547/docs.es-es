---
title: Procedimiento Cambiar la apariencia del control TabControl de formularios de Windows
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
ms.openlocfilehash: 1ed062b3991d7738269d30a6ff13cda3c80927c2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54630325"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-tabcontrol"></a><span data-ttu-id="217e2-102">Procedimiento Cambiar la apariencia del control TabControl de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="217e2-102">How to: Change the Appearance of the Windows Forms TabControl</span></span>
<span data-ttu-id="217e2-103">Puede cambiar la apariencia de fichas en Windows Forms mediante el uso de las propiedades de la <xref:System.Windows.Forms.TabControl> y <xref:System.Windows.Forms.TabPage> objetos que componen las fichas individuales en el control.</span><span class="sxs-lookup"><span data-stu-id="217e2-103">You can change the appearance of tabs in Windows Forms by using properties of the <xref:System.Windows.Forms.TabControl> and the <xref:System.Windows.Forms.TabPage> objects that make up the individual tabs on the control.</span></span> <span data-ttu-id="217e2-104">Al establecer estas propiedades, puede mostrar imágenes en las fichas, mostrar pestañas verticalmente en lugar de horizontalmente, mostrar varias filas de pestañas y habilitar o deshabilitar las fichas mediante programación.</span><span class="sxs-lookup"><span data-stu-id="217e2-104">By setting these properties, you can display images on tabs, display tabs vertically instead of horizontally, display multiple rows of tabs, and enable or disable tabs programmatically.</span></span>  
  
### <a name="to-display-an-icon-on-the-label-part-of-a-tab"></a><span data-ttu-id="217e2-105">Para mostrar un icono en la parte de una pestaña de etiqueta</span><span class="sxs-lookup"><span data-stu-id="217e2-105">To display an icon on the label part of a tab</span></span>  
  
1.  <span data-ttu-id="217e2-106">Agregar un <xref:System.Windows.Forms.ImageList> control al formulario.</span><span class="sxs-lookup"><span data-stu-id="217e2-106">Add an <xref:System.Windows.Forms.ImageList> control to the form.</span></span>  
  
2.  <span data-ttu-id="217e2-107">Agregar imágenes a la lista de imágenes.</span><span class="sxs-lookup"><span data-stu-id="217e2-107">Add images to the image list.</span></span>  
  
     <span data-ttu-id="217e2-108">Para obtener más información acerca de las listas de imágenes, consulte [componente ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) y [Cómo: Agregar o quitar imágenes con el Windows Forms ImageList (componente)](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="217e2-108">For more information about image lists, see [ImageList Component](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
3.  <span data-ttu-id="217e2-109">Establecer el <xref:System.Windows.Forms.TabControl.ImageList%2A> propiedad de la <xref:System.Windows.Forms.TabControl> a la <xref:System.Windows.Forms.ImageList> control.</span><span class="sxs-lookup"><span data-stu-id="217e2-109">Set the <xref:System.Windows.Forms.TabControl.ImageList%2A> property of the <xref:System.Windows.Forms.TabControl> to the <xref:System.Windows.Forms.ImageList> control.</span></span>  
  
4.  <span data-ttu-id="217e2-110">Establecer el <xref:System.Windows.Forms.TabPage.ImageIndex%2A> propiedad de la <xref:System.Windows.Forms.TabPage> al índice de una imagen adecuada en la lista.</span><span class="sxs-lookup"><span data-stu-id="217e2-110">Set the <xref:System.Windows.Forms.TabPage.ImageIndex%2A> property of the <xref:System.Windows.Forms.TabPage> to the index of an appropriate image in the list.</span></span>  
  
### <a name="to-create-multiple-rows-of-tabs"></a><span data-ttu-id="217e2-111">Para crear varias filas de pestañas</span><span class="sxs-lookup"><span data-stu-id="217e2-111">To create multiple rows of tabs</span></span>  
  
1.  <span data-ttu-id="217e2-112">Agregue el número de páginas de ficha que desee.</span><span class="sxs-lookup"><span data-stu-id="217e2-112">Add the number of tab pages you want.</span></span>  
  
2.  <span data-ttu-id="217e2-113">Establecer el <xref:System.Windows.Forms.TabControl.Multiline%2A> propiedad de la <xref:System.Windows.Forms.TabControl> a `true`.</span><span class="sxs-lookup"><span data-stu-id="217e2-113">Set the <xref:System.Windows.Forms.TabControl.Multiline%2A> property of the <xref:System.Windows.Forms.TabControl> to `true`.</span></span>  
  
3.  <span data-ttu-id="217e2-114">Si las fichas no aparecen ya en varias filas, establezca el <xref:System.Windows.Forms.Control.Width%2A> propiedad de la <xref:System.Windows.Forms.TabControl> sea más estrechas que todas las fichas.</span><span class="sxs-lookup"><span data-stu-id="217e2-114">If the tabs do not already appear in multiple rows, set the <xref:System.Windows.Forms.Control.Width%2A> property of the <xref:System.Windows.Forms.TabControl> to be narrower than all the tabs.</span></span>  
  
### <a name="to-arrange-tabs-on-the-side-of-the-control"></a><span data-ttu-id="217e2-115">Para organizar las fichas en el lado del control</span><span class="sxs-lookup"><span data-stu-id="217e2-115">To arrange tabs on the side of the control</span></span>  
  
-   <span data-ttu-id="217e2-116">Establecer el <xref:System.Windows.Forms.TabControl.Alignment%2A> propiedad de la <xref:System.Windows.Forms.TabControl> a <xref:System.Windows.Forms.TabAlignment.Left> o <xref:System.Windows.Forms.TabAlignment.Right>.</span><span class="sxs-lookup"><span data-stu-id="217e2-116">Set the <xref:System.Windows.Forms.TabControl.Alignment%2A> property of the <xref:System.Windows.Forms.TabControl> to <xref:System.Windows.Forms.TabAlignment.Left> or <xref:System.Windows.Forms.TabAlignment.Right>.</span></span>  
  
### <a name="to-programmatically-enable-or-disable-all-controls-on-a-tab"></a><span data-ttu-id="217e2-117">Para habilitar o deshabilitar todos los controles en una ficha mediante programación</span><span class="sxs-lookup"><span data-stu-id="217e2-117">To programmatically enable or disable all controls on a tab</span></span>  
  
1.  <span data-ttu-id="217e2-118">Establecer el <xref:System.Windows.Forms.TabPage.Enabled%2A> propiedad de la <xref:System.Windows.Forms.TabPage> a `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="217e2-118">Set the <xref:System.Windows.Forms.TabPage.Enabled%2A> property of the <xref:System.Windows.Forms.TabPage> to `true` or `false`.</span></span>  
  
    ```vb  
    TabPage1.Enabled = False  
    ```  
  
    ```csharp  
    tabPage1.Enabled = false;  
    ```  
  
    ```cpp  
    tabPage1->Enabled = false;  
    ```  
  
### <a name="to-display-tabs-as-buttons"></a><span data-ttu-id="217e2-119">Para mostrar fichas como botones</span><span class="sxs-lookup"><span data-stu-id="217e2-119">To display tabs as buttons</span></span>  
  
-   <span data-ttu-id="217e2-120">Establecer el <xref:System.Windows.Forms.TabControl.Appearance%2A> propiedad de la <xref:System.Windows.Forms.TabControl> a <xref:System.Windows.Forms.TabAppearance.Buttons> o <xref:System.Windows.Forms.TabAppearance.FlatButtons>.</span><span class="sxs-lookup"><span data-stu-id="217e2-120">Set the <xref:System.Windows.Forms.TabControl.Appearance%2A> property of the <xref:System.Windows.Forms.TabControl> to <xref:System.Windows.Forms.TabAppearance.Buttons> or <xref:System.Windows.Forms.TabAppearance.FlatButtons>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="217e2-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="217e2-121">See also</span></span>
- [<span data-ttu-id="217e2-122">TabControl (control)</span><span class="sxs-lookup"><span data-stu-id="217e2-122">TabControl Control</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="217e2-123">Información general del control TabControl</span><span class="sxs-lookup"><span data-stu-id="217e2-123">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="217e2-124">Cómo: Agregar un Control a una página de ficha</span><span class="sxs-lookup"><span data-stu-id="217e2-124">How to: Add a Control to a Tab Page</span></span>](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="217e2-125">Cómo: Deshabilitar páginas de fichas</span><span class="sxs-lookup"><span data-stu-id="217e2-125">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)
- [<span data-ttu-id="217e2-126">Cómo: Agregar y quitar fichas con el control TabControl de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="217e2-126">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)

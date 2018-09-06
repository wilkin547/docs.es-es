---
title: 'Cómo: Agregar o quitar imágenes del componente ImageList mediante el Diseñador'
ms.date: 03/30/2017
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
ms.openlocfilehash: cc85306c68baa4b4a0fe3418c511672d34790ae7
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43864005"
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a><span data-ttu-id="51295-102">Cómo: Agregar o quitar imágenes del componente ImageList mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="51295-102">How to: Add or Remove ImageList Images with the Designer</span></span>
<span data-ttu-id="51295-103">Puede agregar imágenes a un <xref:System.Windows.Forms.ImageList> componente de varias maneras diferentes.</span><span class="sxs-lookup"><span data-stu-id="51295-103">You can add images to an <xref:System.Windows.Forms.ImageList> component several different ways.</span></span> <span data-ttu-id="51295-104">Puede agregar imágenes muy rápidamente mediante el uso de la etiqueta inteligente asociada a la <xref:System.Windows.Forms.ImageList>, o si va a establecer otras propiedades en el <xref:System.Windows.Forms.ImageList>, quizá le resulte más cómodo agregar imágenes con la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="51295-104">You can add images very quickly by using the smart tag associated with the <xref:System.Windows.Forms.ImageList>, or if you are setting several other properties on the <xref:System.Windows.Forms.ImageList>, you may find it more convenient to add images with the Properties window.</span></span> <span data-ttu-id="51295-105">También puede agregar imágenes mediante código.</span><span class="sxs-lookup"><span data-stu-id="51295-105">You can also add images by using code.</span></span> <span data-ttu-id="51295-106">Para obtener más información sobre cómo agregar imágenes con código, vea [Cómo: agregar o quitar imágenes con el componente ImageList de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="51295-106">For more information about how to add images with code, see [How to: Add or Remove Images with the Windows Forms ImageList Component](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span> <span data-ttu-id="51295-107">Normalmente puede rellenar el <xref:System.Windows.Forms.ImageList> componente con imágenes antes de está asociado con un control, pero esto no es necesario.</span><span class="sxs-lookup"><span data-stu-id="51295-107">Typically you populate the <xref:System.Windows.Forms.ImageList> component with images before it is associated with a control, but this is not required.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51295-108">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="51295-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="51295-109">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="51295-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="51295-110">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="51295-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-or-remove-images-by-using-the-properties-window"></a><span data-ttu-id="51295-111">Para agregar o quitar imágenes mediante el uso de la ventana Propiedades</span><span class="sxs-lookup"><span data-stu-id="51295-111">To add or remove images by using the Properties window</span></span>  
  
1.  <span data-ttu-id="51295-112">Seleccione el <xref:System.Windows.Forms.ImageList> componente, o agregue uno al formulario.</span><span class="sxs-lookup"><span data-stu-id="51295-112">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>  
  
2.  <span data-ttu-id="51295-113">En la ventana Propiedades, haga clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) junto a la <xref:System.Windows.Forms.ImageList.Images%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="51295-113">In the Properties window, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>  
  
3.  <span data-ttu-id="51295-114">En el **Editor de colección de imágenes**, haga clic en **agregar** o **quitar** para agregar o quitar imágenes de la lista.</span><span class="sxs-lookup"><span data-stu-id="51295-114">In the **Image Collection Editor**, click **Add** or **Remove** to add or remove images from the list.</span></span>  
  
### <a name="to-add-or-remove-images-using-the-smart-tag"></a><span data-ttu-id="51295-115">Para agregar o quitar imágenes con la etiqueta inteligente</span><span class="sxs-lookup"><span data-stu-id="51295-115">To add or remove images using the smart tag</span></span>  
  
1.  <span data-ttu-id="51295-116">Seleccione el <xref:System.Windows.Forms.ImageList> componente, o agregue uno al formulario.</span><span class="sxs-lookup"><span data-stu-id="51295-116">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>  
  
2.  <span data-ttu-id="51295-117">Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span><span class="sxs-lookup"><span data-stu-id="51295-117">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span></span>  
  
3.  <span data-ttu-id="51295-118">En el **ImageList tareas** cuadro de diálogo, seleccione **elegir imágenes**.</span><span class="sxs-lookup"><span data-stu-id="51295-118">In the **ImageList Tasks** dialog box, select **Choose Images**.</span></span>  
  
4.  <span data-ttu-id="51295-119">En el **Editor Kolekce Images** haga clic en **agregar** o **quitar** para agregar o quitar imágenes de la lista.</span><span class="sxs-lookup"><span data-stu-id="51295-119">In the **Images Collection Editor** click **Add** or **Remove** to add or remove images from the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51295-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="51295-120">See Also</span></span>  
 [<span data-ttu-id="51295-121">Imágenes, mapas de bits y metarchivos</span><span class="sxs-lookup"><span data-stu-id="51295-121">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="51295-122">Tutorial: Realizar tareas comunes utilizando etiquetas inteligentes en controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="51295-122">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md)  
 [<span data-ttu-id="51295-123">ImageList (componente)</span><span class="sxs-lookup"><span data-stu-id="51295-123">ImageList Component</span></span>](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)

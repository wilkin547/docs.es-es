---
title: Filtrar para agregar o quitar imágenes del componente ImageList mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
ms.openlocfilehash: 732267b431c5058fa7039f0fb132e6161c37d4a6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59303133"
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a><span data-ttu-id="cd101-102">Filtrar para agregar o quitar imágenes del componente ImageList mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="cd101-102">How to: Add or Remove ImageList Images with the Designer</span></span>
<span data-ttu-id="cd101-103">Puede agregar imágenes a un <xref:System.Windows.Forms.ImageList> componente de varias maneras diferentes.</span><span class="sxs-lookup"><span data-stu-id="cd101-103">You can add images to an <xref:System.Windows.Forms.ImageList> component several different ways.</span></span> <span data-ttu-id="cd101-104">Puede agregar imágenes muy rápidamente mediante el uso de la etiqueta inteligente asociada a la <xref:System.Windows.Forms.ImageList>, o si va a establecer otras propiedades en el <xref:System.Windows.Forms.ImageList>, quizá le resulte más cómodo agregar imágenes con la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="cd101-104">You can add images very quickly by using the smart tag associated with the <xref:System.Windows.Forms.ImageList>, or if you are setting several other properties on the <xref:System.Windows.Forms.ImageList>, you may find it more convenient to add images with the Properties window.</span></span> <span data-ttu-id="cd101-105">También puede agregar imágenes mediante código.</span><span class="sxs-lookup"><span data-stu-id="cd101-105">You can also add images by using code.</span></span> <span data-ttu-id="cd101-106">Para obtener más información sobre cómo agregar imágenes con código, vea [Cómo: Agregar o quitar imágenes con el Windows Forms ImageList (componente)](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="cd101-106">For more information about how to add images with code, see [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span> <span data-ttu-id="cd101-107">Normalmente puede rellenar el <xref:System.Windows.Forms.ImageList> componente con imágenes antes de está asociado con un control, pero esto no es necesario.</span><span class="sxs-lookup"><span data-stu-id="cd101-107">Typically you populate the <xref:System.Windows.Forms.ImageList> component with images before it is associated with a control, but this is not required.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cd101-108">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="cd101-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="cd101-109">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="cd101-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="cd101-110">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="cd101-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-or-remove-images-by-using-the-properties-window"></a><span data-ttu-id="cd101-111">Para agregar o quitar imágenes mediante el uso de la ventana Propiedades</span><span class="sxs-lookup"><span data-stu-id="cd101-111">To add or remove images by using the Properties window</span></span>  
  
1. <span data-ttu-id="cd101-112">Seleccione el <xref:System.Windows.Forms.ImageList> componente, o agregue uno al formulario.</span><span class="sxs-lookup"><span data-stu-id="cd101-112">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>  
  
2. <span data-ttu-id="cd101-113">En la ventana Propiedades, haga clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) junto a la <xref:System.Windows.Forms.ImageList.Images%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="cd101-113">In the Properties window, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>  
  
3. <span data-ttu-id="cd101-114">En el **Editor de colección de imágenes**, haga clic en **agregar** o **quitar** para agregar o quitar imágenes de la lista.</span><span class="sxs-lookup"><span data-stu-id="cd101-114">In the **Image Collection Editor**, click **Add** or **Remove** to add or remove images from the list.</span></span>  
  
### <a name="to-add-or-remove-images-using-the-smart-tag"></a><span data-ttu-id="cd101-115">Para agregar o quitar imágenes con la etiqueta inteligente</span><span class="sxs-lookup"><span data-stu-id="cd101-115">To add or remove images using the smart tag</span></span>  
  
1. <span data-ttu-id="cd101-116">Seleccione el <xref:System.Windows.Forms.ImageList> componente, o agregue uno al formulario.</span><span class="sxs-lookup"><span data-stu-id="cd101-116">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>  
  
2. <span data-ttu-id="cd101-117">Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span><span class="sxs-lookup"><span data-stu-id="cd101-117">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span></span>  
  
3. <span data-ttu-id="cd101-118">En el **ImageList tareas** cuadro de diálogo, seleccione **elegir imágenes**.</span><span class="sxs-lookup"><span data-stu-id="cd101-118">In the **ImageList Tasks** dialog box, select **Choose Images**.</span></span>  
  
4. <span data-ttu-id="cd101-119">En el **Editor Kolekce Images** haga clic en **agregar** o **quitar** para agregar o quitar imágenes de la lista.</span><span class="sxs-lookup"><span data-stu-id="cd101-119">In the **Images Collection Editor** click **Add** or **Remove** to add or remove images from the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd101-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd101-120">See also</span></span>

- [<span data-ttu-id="cd101-121">Imágenes, mapas de bits y metarchivos</span><span class="sxs-lookup"><span data-stu-id="cd101-121">Images, Bitmaps, and Metafiles</span></span>](../advanced/images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="cd101-122">Tutorial: Realizar tareas comunes con etiquetas inteligentes en controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cd101-122">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](performing-common-tasks-using-smart-tags-on-wf-controls.md)
- [<span data-ttu-id="cd101-123">Componente ImageList</span><span class="sxs-lookup"><span data-stu-id="cd101-123">ImageList Component</span></span>](imagelist-component-windows-forms.md)

---
title: Procedimiento para agregar o quitar imágenes del componente ImageList mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
ms.openlocfilehash: 63692a797ad49f0adc3a0c5b0bfff1aebbc65257
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038268"
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a><span data-ttu-id="338d8-102">Procedimiento para agregar o quitar imágenes del componente ImageList mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="338d8-102">How to: Add or Remove ImageList Images with the Designer</span></span>

<span data-ttu-id="338d8-103">Puede Agregar imágenes a un <xref:System.Windows.Forms.ImageList> componente de varias maneras diferentes.</span><span class="sxs-lookup"><span data-stu-id="338d8-103">You can add images to an <xref:System.Windows.Forms.ImageList> component several different ways.</span></span> <span data-ttu-id="338d8-104">Puede Agregar imágenes muy rápidamente mediante la etiqueta inteligente asociada a <xref:System.Windows.Forms.ImageList>, o si está estableciendo otras propiedades en el <xref:System.Windows.Forms.ImageList>, puede que le resulte más conveniente agregar imágenes con el ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="338d8-104">You can add images very quickly by using the smart tag associated with the <xref:System.Windows.Forms.ImageList>, or if you are setting several other properties on the <xref:System.Windows.Forms.ImageList>, you may find it more convenient to add images with the Properties window.</span></span> <span data-ttu-id="338d8-105">También puede Agregar imágenes mediante código.</span><span class="sxs-lookup"><span data-stu-id="338d8-105">You can also add images by using code.</span></span> <span data-ttu-id="338d8-106">Para obtener más información sobre cómo agregar imágenes con código, consulte [cómo: Agregue o quite imágenes con el componente](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)ImageList de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="338d8-106">For more information about how to add images with code, see [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span> <span data-ttu-id="338d8-107">Normalmente, el <xref:System.Windows.Forms.ImageList> componente se rellena con imágenes antes de asociarlo a un control, pero esto no es necesario.</span><span class="sxs-lookup"><span data-stu-id="338d8-107">Typically you populate the <xref:System.Windows.Forms.ImageList> component with images before it is associated with a control, but this is not required.</span></span>


### <a name="to-add-or-remove-images-by-using-the-properties-window"></a><span data-ttu-id="338d8-108">Para agregar o quitar imágenes mediante el ventana Propiedades</span><span class="sxs-lookup"><span data-stu-id="338d8-108">To add or remove images by using the Properties window</span></span>

1. <span data-ttu-id="338d8-109">Seleccione el <xref:System.Windows.Forms.ImageList> componente o agregue uno al formulario.</span><span class="sxs-lookup"><span data-stu-id="338d8-109">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>

2. <span data-ttu-id="338d8-110">En el ventana Propiedades, haga clic en el botón![de puntos suspensivos (el botón de puntos suspensivos (...) en](./media/visual-studio-ellipsis-button.png)el ventana Propiedades de Visual <xref:System.Windows.Forms.ImageList.Images%2A> Studio.) situado junto a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="338d8-110">In the Properties window, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>

3. <span data-ttu-id="338d8-111">En el **Editor**de la colección de imágenes, haga clic en **Agregar** o **quitar** para agregar o quitar imágenes de la lista.</span><span class="sxs-lookup"><span data-stu-id="338d8-111">In the **Image Collection Editor**, click **Add** or **Remove** to add or remove images from the list.</span></span>

### <a name="to-add-or-remove-images-using-the-smart-tag"></a><span data-ttu-id="338d8-112">Para agregar o quitar imágenes mediante la etiqueta inteligente</span><span class="sxs-lookup"><span data-stu-id="338d8-112">To add or remove images using the smart tag</span></span>

1. <span data-ttu-id="338d8-113">Seleccione el <xref:System.Windows.Forms.ImageList> componente o agregue uno al formulario.</span><span class="sxs-lookup"><span data-stu-id="338d8-113">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>

2. <span data-ttu-id="338d8-114">Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span><span class="sxs-lookup"><span data-stu-id="338d8-114">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span></span>

3. <span data-ttu-id="338d8-115">En el cuadro de diálogo **tareas de ImageList** , seleccione **elegir imágenes**.</span><span class="sxs-lookup"><span data-stu-id="338d8-115">In the **ImageList Tasks** dialog box, select **Choose Images**.</span></span>

4. <span data-ttu-id="338d8-116">En el **Editor de la colección imágenes** , haga clic en **Agregar** o **quitar** para agregar o quitar imágenes de la lista.</span><span class="sxs-lookup"><span data-stu-id="338d8-116">In the **Images Collection Editor** click **Add** or **Remove** to add or remove images from the list.</span></span>

## <a name="see-also"></a><span data-ttu-id="338d8-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="338d8-117">See also</span></span>

- [<span data-ttu-id="338d8-118">Imágenes, mapas de bits y metarchivos</span><span class="sxs-lookup"><span data-stu-id="338d8-118">Images, Bitmaps, and Metafiles</span></span>](../advanced/images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="338d8-119">Tutorial: Realizar tareas comunes utilizando etiquetas inteligentes en controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="338d8-119">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](performing-common-tasks-using-smart-tags-on-wf-controls.md)
- [<span data-ttu-id="338d8-120">ImageList (componente)</span><span class="sxs-lookup"><span data-stu-id="338d8-120">ImageList Component</span></span>](imagelist-component-windows-forms.md)

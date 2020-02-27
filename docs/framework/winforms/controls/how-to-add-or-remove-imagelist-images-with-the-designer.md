---
title: 'Cómo: Agregar o quitar imágenes del componente ImageList mediante el Diseñador'
ms.date: 03/30/2017
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
ms.openlocfilehash: cdc7b563a0ee4f8779b99b4e9a6786e78f8d500f
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628727"
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a><span data-ttu-id="de03c-102">Cómo: Agregar o quitar imágenes del componente ImageList mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="de03c-102">How to: Add or Remove ImageList Images with the Designer</span></span>

<span data-ttu-id="de03c-103">Puede Agregar imágenes a un componente <xref:System.Windows.Forms.ImageList> de varias maneras diferentes.</span><span class="sxs-lookup"><span data-stu-id="de03c-103">You can add images to an <xref:System.Windows.Forms.ImageList> component several different ways.</span></span> <span data-ttu-id="de03c-104">Puede Agregar imágenes muy rápidamente mediante la etiqueta inteligente asociada a la <xref:System.Windows.Forms.ImageList>, o si está configurando otras propiedades en el <xref:System.Windows.Forms.ImageList>, puede que le resulte más conveniente agregar imágenes con el ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="de03c-104">You can add images very quickly by using the smart tag associated with the <xref:System.Windows.Forms.ImageList>, or if you are setting several other properties on the <xref:System.Windows.Forms.ImageList>, you may find it more convenient to add images with the Properties window.</span></span> <span data-ttu-id="de03c-105">También puede Agregar imágenes mediante código.</span><span class="sxs-lookup"><span data-stu-id="de03c-105">You can also add images by using code.</span></span> <span data-ttu-id="de03c-106">Para obtener más información sobre cómo agregar imágenes con código, consulte [Cómo: agregar o quitar imágenes con el componente ImageList de Windows Forms](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="de03c-106">For more information about how to add images with code, see [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span> <span data-ttu-id="de03c-107">Normalmente, rellenar el componente de <xref:System.Windows.Forms.ImageList> con imágenes antes de asociarlo a un control, pero esto no es necesario.</span><span class="sxs-lookup"><span data-stu-id="de03c-107">Typically you populate the <xref:System.Windows.Forms.ImageList> component with images before it is associated with a control, but this is not required.</span></span>

### <a name="to-add-or-remove-images-by-using-the-properties-window"></a><span data-ttu-id="de03c-108">Para agregar o quitar imágenes mediante el ventana Propiedades</span><span class="sxs-lookup"><span data-stu-id="de03c-108">To add or remove images by using the Properties window</span></span>

1. <span data-ttu-id="de03c-109">Seleccione el componente de <xref:System.Windows.Forms.ImageList> o agregue uno al formulario.</span><span class="sxs-lookup"><span data-stu-id="de03c-109">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>

2. <span data-ttu-id="de03c-110">En el ventana Propiedades, haga clic en el botón de puntos suspensivos (![el botón de puntos suspensivos (...) en el ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)) junto a la propiedad <xref:System.Windows.Forms.ImageList.Images%2A>.</span><span class="sxs-lookup"><span data-stu-id="de03c-110">In the Properties window, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>

3. <span data-ttu-id="de03c-111">En el **Editor**de la colección de imágenes, haga clic en **Agregar** o **quitar** para agregar o quitar imágenes de la lista.</span><span class="sxs-lookup"><span data-stu-id="de03c-111">In the **Image Collection Editor**, click **Add** or **Remove** to add or remove images from the list.</span></span>

### <a name="to-add-or-remove-images-using-the-smart-tag"></a><span data-ttu-id="de03c-112">Para agregar o quitar imágenes mediante la etiqueta inteligente</span><span class="sxs-lookup"><span data-stu-id="de03c-112">To add or remove images using the smart tag</span></span>

1. <span data-ttu-id="de03c-113">Seleccione el componente de <xref:System.Windows.Forms.ImageList> o agregue uno al formulario.</span><span class="sxs-lookup"><span data-stu-id="de03c-113">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>

2. <span data-ttu-id="de03c-114">Haga clic en el glifo de acciones del diseñador (</span><span class="sxs-lookup"><span data-stu-id="de03c-114">Click the designer actions glyph (</span></span>![Flecha negra pequeña](./media/designer-actions-glyph.gif)<span data-ttu-id="de03c-116">)</span><span class="sxs-lookup"><span data-stu-id="de03c-116">)</span></span>

3. <span data-ttu-id="de03c-117">En el cuadro de diálogo **tareas de ImageList** , seleccione **elegir imágenes**.</span><span class="sxs-lookup"><span data-stu-id="de03c-117">In the **ImageList Tasks** dialog box, select **Choose Images**.</span></span>

4. <span data-ttu-id="de03c-118">En el **Editor de la colección imágenes** , haga clic en **Agregar** o **quitar** para agregar o quitar imágenes de la lista.</span><span class="sxs-lookup"><span data-stu-id="de03c-118">In the **Images Collection Editor** click **Add** or **Remove** to add or remove images from the list.</span></span>

## <a name="see-also"></a><span data-ttu-id="de03c-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="de03c-119">See also</span></span>

- [<span data-ttu-id="de03c-120">Imágenes, mapas de bits y metarchivos</span><span class="sxs-lookup"><span data-stu-id="de03c-120">Images, Bitmaps, and Metafiles</span></span>](../advanced/images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="de03c-121">Tutorial: realizar tareas comunes con las acciones del diseñador</span><span class="sxs-lookup"><span data-stu-id="de03c-121">Walkthrough: Perform common tasks using designer actions</span></span>](perform-common-tasks-design-actions.md)
- [<span data-ttu-id="de03c-122">ImageList (componente)</span><span class="sxs-lookup"><span data-stu-id="de03c-122">ImageList Component</span></span>](imagelist-component-windows-forms.md)

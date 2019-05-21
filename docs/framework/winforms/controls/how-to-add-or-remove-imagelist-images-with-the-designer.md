---
title: Procedimiento para agregar o quitar imágenes del componente ImageList mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
ms.openlocfilehash: 57c124f19d208192cb2d4500274f7f897948252a
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2019
ms.locfileid: "65960158"
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a>Procedimiento para agregar o quitar imágenes del componente ImageList mediante el diseñador

Puede agregar imágenes a un <xref:System.Windows.Forms.ImageList> componente de varias maneras diferentes. Puede agregar imágenes muy rápidamente mediante el uso de la etiqueta inteligente asociada a la <xref:System.Windows.Forms.ImageList>, o si va a establecer otras propiedades en el <xref:System.Windows.Forms.ImageList>, quizá le resulte más cómodo agregar imágenes con la ventana Propiedades. También puede agregar imágenes mediante código. Para obtener más información sobre cómo agregar imágenes con código, vea [Cómo: Agregar o quitar imágenes con el Windows Forms ImageList (componente)](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md). Normalmente puede rellenar el <xref:System.Windows.Forms.ImageList> componente con imágenes antes de está asociado con un control, pero esto no es necesario.

> [!NOTE]
> Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).

### <a name="to-add-or-remove-images-by-using-the-properties-window"></a>Para agregar o quitar imágenes mediante el uso de la ventana Propiedades

1. Seleccione el <xref:System.Windows.Forms.ImageList> componente, o agregue uno al formulario.

2. En la ventana Propiedades, haga clic en el botón de puntos suspensivos (![los puntos suspensivos (...) en la ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)) junto a la <xref:System.Windows.Forms.ImageList.Images%2A> propiedad.

3. En el **Editor de colección de imágenes**, haga clic en **agregar** o **quitar** para agregar o quitar imágenes de la lista.

### <a name="to-add-or-remove-images-using-the-smart-tag"></a>Para agregar o quitar imágenes con la etiqueta inteligente

1. Seleccione el <xref:System.Windows.Forms.ImageList> componente, o agregue uno al formulario.

2. Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))

3. En el **ImageList tareas** cuadro de diálogo, seleccione **elegir imágenes**.

4. En el **Editor Kolekce Images** haga clic en **agregar** o **quitar** para agregar o quitar imágenes de la lista.

## <a name="see-also"></a>Vea también

- [Imágenes, mapas de bits y metarchivos](../advanced/images-bitmaps-and-metafiles.md)
- [Tutorial: Realizar tareas comunes mediante Smart etiquetas en Windows Forms controles](performing-common-tasks-using-smart-tags-on-wf-controls.md)
- [ImageList (componente)](imagelist-component-windows-forms.md)

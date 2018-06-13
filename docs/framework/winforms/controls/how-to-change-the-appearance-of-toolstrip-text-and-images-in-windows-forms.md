---
title: 'Cómo: Cambiar la apariencia del texto y las imágenes de ToolStrip en formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], appearance
- toolbars [Windows Forms], images
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], appearance
- ToolStrip control [Windows Forms], images
- ToolStrip control [Windows Forms], text
- toolbars [Windows Forms], text
ms.assetid: d62dc9d1-2edd-4dfa-aed7-1335d6e13d86
ms.openlocfilehash: d3f53291e24d6a57e798725b716a7fd56eb661b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530535"
---
# <a name="how-to-change-the-appearance-of-toolstrip-text-and-images-in-windows-forms"></a>Cómo: Cambiar la apariencia del texto y las imágenes de ToolStrip en formularios Windows Forms
Puede controlar si el texto y las imágenes se muestran en un <xref:System.Windows.Forms.ToolStripItem> y cómo se alinean entre sí y la <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="to-define-what-is-displayed-on-a-toolstripitem"></a>Para definir lo que se muestra en un elemento ToolStripItem  
  
-   Establecer el <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> en el valor deseado. Las posibilidades son `Image`, `ImageAndText`, `None`, y `Text`. De manera predeterminada, es `ImageAndText`.  
  
    ```vb  
    ToolStripButton2.DisplayStyle = _  
        System.Windows.Forms.ToolStripItemDisplayStyle.Image  
    ```  
  
    ```csharp  
    toolStripButton2.DisplayStyle = System.Windows.Forms.ToolStripItemDisplayStyle.Image;  
    ```  
  
### <a name="to-align-text-on-a-toolstripitem"></a>Para alinear el texto en un elemento ToolStripItem  
  
-   Establecer el <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> en el valor deseado. Las posibilidades son cualquier combinación de parte superior, medio e inferior con izquierda, centro y derecha. De manera predeterminada, es `MiddleCenter`.  
  
    ```vb  
    ToolStripSplitButton1.TextAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.TextAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-align-an-image-on-a-toolstripitem"></a>Para alinear una imagen en un elemento ToolStripItem  
  
-   Establecer el <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> en el valor deseado. Las posibilidades son cualquier combinación de parte superior, medio e inferior con izquierda, centro y derecha. De manera predeterminada, es `MiddleLeft`.  
  
    ```vb  
    ToolStripSplitButton1.ImageAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.ImageAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-define-how-toolstripitem-text-and-images-are-displayed-relative-to-each-other"></a>Para definir cómo se muestran imágenes y texto de ToolStripItem relacionados entre sí  
  
-   Establecer el <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> en el valor deseado. Las posibilidades son `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage`, y `TextBeforeImage`. De manera predeterminada, es `ImageBeforeText`.  
  
    ```vb  
    ToolStripButton1.TextImageRelation = _  
        System.Windows.Forms.TextImageRelation.ImageAboveText  
    ```  
  
    ```csharp  
    toolStripButton1.TextImageRelation = System.Windows.Forms.TextImageRelation.ImageAboveText;  
    ```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ToolStrip>  
 [Información sobre el control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [Arquitectura del control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [Resumen de la tecnología ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)

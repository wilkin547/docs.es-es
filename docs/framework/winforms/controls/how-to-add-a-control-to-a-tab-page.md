---
title: 'Cómo: Agregar un control a una página de fichas'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TabPage control
- tab controls [Windows Forms], tab order
- tab pages [Windows Forms], adding controls
ms.assetid: b092532e-7346-469f-b9a1-897f9bea4fb7
ms.openlocfilehash: 1bb2233cf9e288ae89ebb8cab3df4f6451dc8eed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-a-control-to-a-tab-page"></a>Cómo: Agregar un control a una página de fichas
Puede utilizar los formularios de Windows <xref:System.Windows.Forms.TabControl> para mostrar otros controles de un modo organizado. El siguiente procedimiento muestra cómo agregar un botón a la primera pestaña. Para obtener información sobre cómo agregar un icono a la parte de la etiqueta de una página de fichas, vea [Cómo: cambiar la apariencia del control TabControl de formularios de Windows](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).  
  
### <a name="to-add-a-control-programmatically"></a>Para agregar un control mediante programación  
  
1.  Use la <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> método de la colección devuelta por la <xref:System.Windows.Forms.Control.Controls%2A> propiedad de <xref:System.Windows.Forms.TabPage>:  
  
     [!code-cpp[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cpp/add.cpp#1)]
     [!code-csharp[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cs/add.cs#1)]
     [!code-vb[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/vb/add.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 [TabControl (control)](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)  
 [Información general del control TabControl](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [Cambiar la apariencia del control TabControl de Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)  
 [Deshabilitar páginas de ficha](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [Agregar y quitar fichas con el control TabControl de Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)

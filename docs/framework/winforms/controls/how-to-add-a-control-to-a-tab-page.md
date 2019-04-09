---
title: Filtrar para agregar un control a una ficha
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
ms.openlocfilehash: b42845ab996c0985fe6a48ac588e6d706905faac
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195857"
---
# <a name="how-to-add-a-control-to-a-tab-page"></a>Filtrar para agregar un control a una ficha
Puede usar los formularios de Windows <xref:System.Windows.Forms.TabControl> para mostrar otros controles de forma organizada. El procedimiento siguiente muestra cómo agregar un botón a la primera pestaña. Para obtener información sobre cómo agregar un icono a la parte de la etiqueta de una página de ficha, vea [Cómo: Cambiar la apariencia del control TabControl de formularios de Windows](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).  
  
### <a name="to-add-a-control-programmatically"></a>Para agregar un control mediante programación  
  
1.  Use la <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> método de la colección devuelta por la <xref:System.Windows.Forms.Control.Controls%2A> propiedad de <xref:System.Windows.Forms.TabPage>:  
  
     [!code-cpp[TabPageControlCollectionHowToAdd#1](~/samples/snippets/cpp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cpp/add.cpp#1)]
     [!code-csharp[TabPageControlCollectionHowToAdd#1](~/samples/snippets/csharp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cs/add.cs#1)]
     [!code-vb[TabPageControlCollectionHowToAdd#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/vb/add.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [TabControl (Control)](tabcontrol-control-windows-forms.md)
- [Información general sobre el control TabControl](tabcontrol-control-overview-windows-forms.md)
- [Filtrar para cambiar el aspecto apariencia del control TabControl de formularios Windows Forms](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
- [Filtrar para deshabilitar fichas](how-to-disable-tab-pages.md)
- [Filtrar para agregar y quitar fichas con el control TabControl de formularios Windows Forms](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)

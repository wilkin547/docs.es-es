---
title: Procedimiento Seleccione un elemento en el Control ListView de formularios de Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lists [Windows Forms], selecting items
- ListView control [Windows Forms], selecting items
- selection [Windows Forms], in list views
- list views [Windows Forms], selecting items
ms.assetid: ddea918e-1ddf-47f4-bd09-1e9b4c9d0c39
ms.openlocfilehash: ed3e68fbe77f194ed04d15f99a48657a32a13b50
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54644721"
---
# <a name="how-to-select-an-item-in-the-windows-forms-listview-control"></a>Procedimiento Seleccione un elemento en el Control ListView de formularios de Windows
En este ejemplo se muestra cómo seleccionar mediante programación un elemento en un formulario Windows Forms <xref:System.Windows.Forms.ListView> control. Seleccionar un elemento mediante programación no cambia automáticamente el foco a la <xref:System.Windows.Forms.ListView> control. Por este motivo, normalmente, también debe establecer el elemento como centrado al seleccionar un elemento.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un <xref:System.Windows.Forms.ListView> control denominado `listView1` que contiene al menos un elemento.  
  
-   Referencias a los espacios de nombres <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=nameWithType>

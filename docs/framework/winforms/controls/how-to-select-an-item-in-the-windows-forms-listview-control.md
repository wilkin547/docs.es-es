---
title: 'Cómo: Seleccionar un elemento del control ListView de formularios Windows Forms'
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
ms.openlocfilehash: 8256eaeddf98c5a0dd80357bcd562e8f66db85b3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532826"
---
# <a name="how-to-select-an-item-in-the-windows-forms-listview-control"></a>Cómo: Seleccionar un elemento del control ListView de formularios Windows Forms
Este ejemplo muestra cómo seleccionar mediante programación un elemento en un formulario Windows Forms <xref:System.Windows.Forms.ListView> control. Seleccionar un elemento mediante programación no cambia automáticamente el foco a la <xref:System.Windows.Forms.ListView> control. Por esta razón, normalmente también deberá establecer el elemento como enfocado al seleccionar un elemento.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   A <xref:System.Windows.Forms.ListView> control denominado `listView1` que contiene al menos un elemento.  
  
-   Referencias a los espacios de nombres <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=nameWithType>

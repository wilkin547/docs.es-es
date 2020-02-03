---
title: Seleccionar un elemento en el control ListView
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
ms.openlocfilehash: 57e985af9d0347510d7d7782f68d5b414d36e077
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743230"
---
# <a name="how-to-select-an-item-in-the-windows-forms-listview-control"></a>Cómo: Seleccionar un elemento del control ListView de formularios Windows Forms
En este ejemplo se muestra cómo seleccionar un elemento de un control de Windows Forms <xref:System.Windows.Forms.ListView> mediante programación. Al seleccionar un elemento mediante programación, no se cambia automáticamente el foco al control <xref:System.Windows.Forms.ListView>. Por esta razón, normalmente también querrá establecer el elemento como enfocado al seleccionar un elemento.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Un control de <xref:System.Windows.Forms.ListView> denominado `listView1` que contiene al menos un elemento.  
  
- Referencias a los espacios de nombres <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=nameWithType>

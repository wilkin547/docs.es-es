---
title: Agregar y quitar elementos con el control ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], populating
- list views [Windows Forms], adding list items
- ListView control [Windows Forms], adding list items
ms.assetid: 1b35a80a-edd8-495f-a807-a28c4aae52c6
ms.openlocfilehash: bbfe99db857ebe3a80bf99926f3ce0bec38a1f3f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743141"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control"></a>Cómo: Agregar y quitar elementos con el control ListView de Windows Forms
El proceso de agregar un elemento a un Windows Forms control <xref:System.Windows.Forms.ListView> consiste principalmente en especificar el elemento y asignarle propiedades. La adición o eliminación de elementos de lista se puede realizar en cualquier momento.  
  
### <a name="to-add-items-programmatically"></a>Para agregar elementos mediante programación  
  
1. Use el método <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> de la propiedad <xref:System.Windows.Forms.ListView.Items%2A>.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#11)]  
  
### <a name="to-remove-items-programmatically"></a>Para quitar elementos mediante programación  
  
1. Use el método <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> o <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> de la propiedad <xref:System.Windows.Forms.ListView.Items%2A>. El método <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> quita un solo elemento; el método <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> quita todos los elementos de la lista.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ListView>
- [ListView (control)](listview-control-windows-forms.md)
- [Información general del control ListView](listview-control-overview-windows-forms.md)

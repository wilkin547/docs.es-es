---
title: Filtrar para agregar y quitar elementos con el control ListView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], populating
- list views [Windows Forms], adding list items
- ListView control [Windows Forms], adding list items
ms.assetid: 1b35a80a-edd8-495f-a807-a28c4aae52c6
ms.openlocfilehash: ef0275b3cbc79f22b4fa573f41e4cbdbc3d58990
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104655"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control"></a>Filtrar para agregar y quitar elementos con el control ListView de formularios Windows Forms
El proceso de agregar un elemento a un formulario Windows Forms <xref:System.Windows.Forms.ListView> control consta principalmente de especificar el elemento y asignarle propiedades. Agregar o quitar elementos de lista puede realizarse en cualquier momento.  
  
### <a name="to-add-items-programmatically"></a>Para agregar elementos mediante programación  
  
1.  Use la <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> método de la <xref:System.Windows.Forms.ListView.Items%2A> propiedad.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#11)]  
  
### <a name="to-remove-items-programmatically"></a>Para quitar elementos mediante programación  
  
1.  Use la <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> o <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> método de la <xref:System.Windows.Forms.ListView.Items%2A> propiedad. El <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> método quita un elemento único; el <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> método quita todos los elementos de la lista.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ListView>
- [Control ListView](listview-control-windows-forms.md)
- [Información general sobre el control ListView](listview-control-overview-windows-forms.md)

---
title: Agregar y quitar elementos con el control ListView
description: Obtenga información sobre cómo agregar y quitar un elemento con el control Windows Forms ListView especificando el elemento y asignándoles propiedades.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], populating
- list views [Windows Forms], adding list items
- ListView control [Windows Forms], adding list items
ms.assetid: 1b35a80a-edd8-495f-a807-a28c4aae52c6
ms.openlocfilehash: db374ded69bcbd93527381d75a8ff751a1c9abe6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618095"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control"></a>Procedimiento para agregar y quitar elementos con el control ListView de formularios Windows Forms
El proceso de agregar un elemento a un control de Windows Forms <xref:System.Windows.Forms.ListView> consiste principalmente en especificar el elemento y asignarle propiedades. La adición o eliminación de elementos de lista se puede realizar en cualquier momento.  
  
### <a name="to-add-items-programmatically"></a>Para agregar elementos mediante programación  
  
1. Use el <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> método de la <xref:System.Windows.Forms.ListView.Items%2A> propiedad.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#11)]  
  
### <a name="to-remove-items-programmatically"></a>Para quitar elementos mediante programación  
  
1. Use el <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> método o de la <xref:System.Windows.Forms.ListView.Items%2A> propiedad. El <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> método quita un solo elemento; el <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> método quita todos los elementos de la lista.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ListView>
- [Control ListView](listview-control-windows-forms.md)
- [Información general sobre el control ListView](listview-control-overview-windows-forms.md)

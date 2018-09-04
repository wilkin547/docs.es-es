---
title: 'Cómo: Crear un enlace en código'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
ms.openlocfilehash: 2d13650cb3e9a4e97a6642992b7211f323b9ea96
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43502263"
---
# <a name="how-to-create-a-binding-in-code"></a>Cómo: Crear un enlace en código
En este ejemplo se muestra cómo crear y establecer un <xref:System.Windows.Data.Binding> en el código.  
  
## <a name="example"></a>Ejemplo  
 El <xref:System.Windows.FrameworkElement> clase y el <xref:System.Windows.FrameworkContentElement> clase ambas exponer un `SetBinding` método. Si va a enlazar un elemento que hereda de cualquiera de estas clases, puede llamar a la <xref:System.Windows.FrameworkElement.SetBinding%2A> método directamente.  
  
 En el ejemplo siguiente se crea una clase denominada, `MyData`, que contiene una propiedad denominada `MyDataProperty`.  
  
 [!code-csharp[CodeOnlyBinding#DataObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 El ejemplo siguiente muestra cómo crear un objeto de enlace para establecer el origen del enlace.  El ejemplo se utiliza <xref:System.Windows.FrameworkElement.SetBinding%2A> para enlazar el <xref:System.Windows.Controls.TextBlock.Text%2A> propiedad de `myText`, que es un <xref:System.Windows.Controls.TextBlock> controlar, `MyDataProperty`.  
  
 [!code-csharp[CodeOnlyBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 El ejemplo de código completo, vea [solo código de ejemplo de enlace](https://msdn.microsoft.com/library/764aaf0b-2216-4941-9548-9c98da18d1a6).  
  
 En lugar de llamar <xref:System.Windows.FrameworkElement.SetBinding%2A>, puede usar el <xref:System.Windows.Data.BindingOperations.SetBinding%2A> método estático de la <xref:System.Windows.Data.BindingOperations> clase. El siguiente ejemplo, las llamadas <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> en lugar de <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> para enlazar `myText` a `myDataProperty`.  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)

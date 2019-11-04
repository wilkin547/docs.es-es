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
ms.openlocfilehash: 616487a16ebbe6e23fe067fb7ce72644aa3f919f
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458851"
---
# <a name="how-to-create-a-binding-in-code"></a>Cómo: Crear un enlace en código
En este ejemplo se muestra cómo crear y establecer un <xref:System.Windows.Data.Binding> en el código.  
  
## <a name="example"></a>Ejemplo  
 La clase <xref:System.Windows.FrameworkElement> y la clase <xref:System.Windows.FrameworkContentElement> exponen un método `SetBinding`. Si enlaza un elemento que hereda cualquiera de estas clases, puede llamar al método <xref:System.Windows.FrameworkElement.SetBinding%2A> directamente.  
  
 En el ejemplo siguiente se crea una clase denominada, `MyData`, que contiene una propiedad denominada `MyDataProperty`.  
  
 [!code-csharp[CodeOnlyBinding#DataObject](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 En el ejemplo siguiente se muestra cómo crear un objeto de enlace para establecer el origen del enlace.  En el ejemplo se usa <xref:System.Windows.FrameworkElement.SetBinding%2A> para enlazar la propiedad <xref:System.Windows.Controls.TextBlock.Text%2A> de `myText`, que es un control <xref:System.Windows.Controls.TextBlock>, a `MyDataProperty`.  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 Para obtener el ejemplo de código completo, vea [ejemplo de enlace de solo código](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90)).  
  
 En lugar de llamar a <xref:System.Windows.FrameworkElement.SetBinding%2A>, puede utilizar el método estático <xref:System.Windows.Data.BindingOperations.SetBinding%2A> de la clase <xref:System.Windows.Data.BindingOperations>. En el ejemplo siguiente, se llama a <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> en lugar de <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> para enlazar `myText` a `myDataProperty`.  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)

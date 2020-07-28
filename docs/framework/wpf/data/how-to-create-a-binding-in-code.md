---
title: 'Cómo: Crear un enlace en código'
description: Aprenda a crear un enlace en el código en una aplicación Windows Presentation Foundation llamando directamente al método SetBinding.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
ms.openlocfilehash: aa2a29f4c1262d8ac54641b856c297b284b23a38
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165809"
---
# <a name="how-to-create-a-binding-in-code"></a>Cómo: Crear un enlace en código
En este ejemplo se muestra cómo crear y establecer <xref:System.Windows.Data.Binding> en código.  
  
## <a name="example"></a>Ejemplo  
 La <xref:System.Windows.FrameworkElement> clase y la <xref:System.Windows.FrameworkContentElement> clase exponen un `SetBinding` método. Si enlaza un elemento que hereda cualquiera de estas clases, puede llamar al <xref:System.Windows.FrameworkElement.SetBinding%2A> método directamente.  
  
 En el ejemplo siguiente se crea una clase denominada, `MyData` que contiene una propiedad denominada `MyDataProperty` .  
  
 [!code-csharp[CodeOnlyBinding#DataObject](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 En el ejemplo siguiente se muestra cómo crear un objeto de enlace para establecer el origen del enlace.  En el ejemplo <xref:System.Windows.FrameworkElement.SetBinding%2A> se utiliza para enlazar la <xref:System.Windows.Controls.TextBlock.Text%2A> propiedad de `myText` , que es un <xref:System.Windows.Controls.TextBlock> control, a `MyDataProperty` .  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 Para obtener el ejemplo de código completo, vea [ejemplo de enlace de solo código](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90)).  
  
 En lugar de llamar a <xref:System.Windows.FrameworkElement.SetBinding%2A> , puede utilizar el <xref:System.Windows.Data.BindingOperations.SetBinding%2A> método estático de la <xref:System.Windows.Data.BindingOperations> clase. En el ejemplo siguiente, se llama a en <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> lugar de <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> para enlazar `myText` a `myDataProperty` .  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)

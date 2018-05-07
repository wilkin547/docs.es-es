---
title: 'Cómo: Manipular columnas y filas mediante ColumnDefinitionsCollections y RowDefinitionsCollections'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Grid class
- Grid control [WPF], ColumnDefinitionCollection class
- Grid control [WPF], RowDefinitionCollection class
ms.assetid: bfc7160a-45f2-4e17-9961-df414dfb13c5
ms.openlocfilehash: 6ff5ad4825bd9f683d895341dd084c00f68aa27b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-manipulate-columns-and-rows-by-using-columndefinitionscollections-and-rowdefinitionscollections"></a>Cómo: Manipular columnas y filas mediante ColumnDefinitionsCollections y RowDefinitionsCollections
Este ejemplo muestra cómo utilizar los métodos de la <xref:System.Windows.Controls.ColumnDefinitionCollection> y <xref:System.Windows.Controls.RowDefinitionCollection> clases para realizar acciones como agregar, borrar o contar el contenido de filas o columnas. Por ejemplo, puede <xref:System.Windows.Controls.ColumnDefinitionCollection.Add%2A>, <xref:System.Windows.Controls.ColumnDefinitionCollection.Clear%2A>, o <xref:System.Windows.Controls.ColumnDefinitionCollection.Count%2A> los elementos que se incluyen en un <xref:System.Windows.Controls.ColumnDefinition> o <xref:System.Windows.Controls.RowDefinition>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un <xref:System.Windows.Controls.Grid> elemento con un <xref:System.Windows.FrameworkElement.Name%2A> de `grid1`. El <xref:System.Windows.Controls.Grid> contiene un <xref:System.Windows.Controls.StackPanel> que contiene <xref:System.Windows.Controls.Button> elementos, cada uno de ellos se controla mediante un método de recopilación diferente. Al hacer clic en un <xref:System.Windows.Controls.Button>, se activa una llamada al método en el archivo de código subyacente.  
  
 [!code-xaml[ColumnDefinitionsGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml#1)]  
  
 Este ejemplo define una serie de métodos personalizados, cada uno correspondiente a un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento en el [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo. Puede cambiar el número de columnas y filas en el <xref:System.Windows.Controls.Grid> de varias maneras, lo que incluye agregar o quitar filas y columnas; y contando el número total de filas y columnas. Para evitar que <xref:System.ArgumentOutOfRangeException> y <xref:System.ArgumentException> excepciones, puede usar la funcionalidad de comprobación de errores que el <xref:System.Windows.Controls.ColumnDefinitionCollection.RemoveRange%2A> proporciona el método.  
  
 [!code-csharp[ColumnDefinitionsGrid#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ColumnDefinitionsGrid#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ColumnDefinitionsGrid/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.Controls.ColumnDefinitionCollection>  
 <xref:System.Windows.Controls.RowDefinitionCollection>

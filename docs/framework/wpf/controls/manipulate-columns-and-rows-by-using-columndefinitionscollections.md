---
title: Procedimiento Manipular columnas y filas mediante ColumnDefinitionsCollections y RowDefinitionsCollections
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Grid class
- Grid control [WPF], ColumnDefinitionCollection class
- Grid control [WPF], RowDefinitionCollection class
ms.assetid: bfc7160a-45f2-4e17-9961-df414dfb13c5
ms.openlocfilehash: f316cced076223edba1d39c9cfb21b9a504b9eee
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "59978281"
---
# <a name="how-to-manipulate-columns-and-rows-by-using-columndefinitionscollections-and-rowdefinitionscollections"></a><span data-ttu-id="56995-102">Procedimiento Manipular columnas y filas mediante ColumnDefinitionsCollections y RowDefinitionsCollections</span><span class="sxs-lookup"><span data-stu-id="56995-102">How to: Manipulate Columns and Rows by Using ColumnDefinitionsCollections and RowDefinitionsCollections</span></span>
<span data-ttu-id="56995-103">En este ejemplo se muestra cómo usar los métodos en el <xref:System.Windows.Controls.ColumnDefinitionCollection> y <xref:System.Windows.Controls.RowDefinitionCollection> clases para realizar acciones como agregar, borrar o contar el contenido de filas o columnas.</span><span class="sxs-lookup"><span data-stu-id="56995-103">This example shows how to use the methods in the <xref:System.Windows.Controls.ColumnDefinitionCollection> and <xref:System.Windows.Controls.RowDefinitionCollection> classes to perform actions like adding, clearing, or counting the contents of rows or columns.</span></span> <span data-ttu-id="56995-104">Por ejemplo, puede <xref:System.Windows.Controls.ColumnDefinitionCollection.Add%2A>, <xref:System.Windows.Controls.ColumnDefinitionCollection.Clear%2A>, o <xref:System.Windows.Controls.ColumnDefinitionCollection.Count%2A> los elementos que se incluyen en un <xref:System.Windows.Controls.ColumnDefinition> o <xref:System.Windows.Controls.RowDefinition>.</span><span class="sxs-lookup"><span data-stu-id="56995-104">For example, you can <xref:System.Windows.Controls.ColumnDefinitionCollection.Add%2A>, <xref:System.Windows.Controls.ColumnDefinitionCollection.Clear%2A>, or <xref:System.Windows.Controls.ColumnDefinitionCollection.Count%2A> the items that are included in a <xref:System.Windows.Controls.ColumnDefinition> or <xref:System.Windows.Controls.RowDefinition>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56995-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="56995-105">Example</span></span>  
 <span data-ttu-id="56995-106">En el ejemplo siguiente se crea un <xref:System.Windows.Controls.Grid> elemento con un <xref:System.Windows.FrameworkElement.Name%2A> de `grid1`.</span><span class="sxs-lookup"><span data-stu-id="56995-106">The following example creates a <xref:System.Windows.Controls.Grid> element with a <xref:System.Windows.FrameworkElement.Name%2A> of `grid1`.</span></span> <span data-ttu-id="56995-107">El <xref:System.Windows.Controls.Grid> contiene un <xref:System.Windows.Controls.StackPanel> que contiene <xref:System.Windows.Controls.Button> elementos, cada uno se controla mediante un método de recopilación diferente.</span><span class="sxs-lookup"><span data-stu-id="56995-107">The <xref:System.Windows.Controls.Grid> contains a <xref:System.Windows.Controls.StackPanel> that holds <xref:System.Windows.Controls.Button> elements, each controlled by a different collection method.</span></span> <span data-ttu-id="56995-108">Al hacer clic en un <xref:System.Windows.Controls.Button>, se activa una llamada al método en el archivo de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="56995-108">When you click a <xref:System.Windows.Controls.Button>, it activates a method call in the code-behind file.</span></span>  
  
 [!code-xaml[ColumnDefinitionsGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="56995-109">Este ejemplo define una serie de métodos personalizados, cada uno correspondiente a un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos en el [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo.</span><span class="sxs-lookup"><span data-stu-id="56995-109">This example defines a series of custom methods, each corresponding to a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event in the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="56995-110">Puede cambiar el número de columnas y filas en el <xref:System.Windows.Controls.Grid> de varias maneras, que incluye agregar o quitar filas y columnas; y contando el número total de filas y columnas.</span><span class="sxs-lookup"><span data-stu-id="56995-110">You can change the number of columns and rows in the <xref:System.Windows.Controls.Grid> in several ways, which includes adding or removing rows and columns; and counting the total number of rows and columns.</span></span> <span data-ttu-id="56995-111">Para evitar <xref:System.ArgumentOutOfRangeException> y <xref:System.ArgumentException> excepciones, puede usar la funcionalidad de comprobación de errores que el <xref:System.Windows.Controls.ColumnDefinitionCollection.RemoveRange%2A> proporciona el método.</span><span class="sxs-lookup"><span data-stu-id="56995-111">To prevent <xref:System.ArgumentOutOfRangeException> and <xref:System.ArgumentException> exceptions, you can use the error-checking functionality that the <xref:System.Windows.Controls.ColumnDefinitionCollection.RemoveRange%2A> method provides.</span></span>  
  
 [!code-csharp[ColumnDefinitionsGrid#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ColumnDefinitionsGrid#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ColumnDefinitionsGrid/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="56995-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="56995-112">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.ColumnDefinitionCollection>
- <xref:System.Windows.Controls.RowDefinitionCollection>

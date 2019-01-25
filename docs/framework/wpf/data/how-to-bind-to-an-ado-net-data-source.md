---
title: Procedimiento Enlazar a un origen de datos ADO.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to ADO.NET data sources
- ADO.NET data sources [WPF], binding to
- binding [WPF], to ADO.NET data sources
ms.assetid: a70c6d7b-7b38-4fdf-b655-4804db7c8315
ms.openlocfilehash: 774262b33ceda3e8881fb92bcbc70a3dd5361f39
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746653"
---
# <a name="how-to-bind-to-an-adonet-data-source"></a><span data-ttu-id="0911b-102">Procedimiento Enlazar a un origen de datos ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0911b-102">How to: Bind to an ADO.NET Data Source</span></span>
<span data-ttu-id="0911b-103">En este ejemplo se muestra cómo enlazar un [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox> el control a un [!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)] `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="0911b-103">This example shows how to bind a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox> control to an [!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)] `DataSet`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0911b-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0911b-104">Example</span></span>  
 <span data-ttu-id="0911b-105">En este ejemplo, se utiliza un objeto `OleDbConnection` para conectar al origen de datos, que es un archivo `Access MDB` especificado en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="0911b-105">In this example, an `OleDbConnection` object is used to connect to the data source which is an `Access MDB` file that is specified in the connection string.</span></span> <span data-ttu-id="0911b-106">Una vez establecida la conexión, se crea un objeto `OleDbDataAdpater`.</span><span class="sxs-lookup"><span data-stu-id="0911b-106">After the connection is established, an `OleDbDataAdpater` object is created.</span></span> <span data-ttu-id="0911b-107">El objeto `OleDbDataAdpater` ejecuta una instrucción select de [!INCLUDE[TLA#tla_sql](../../../../includes/tlasharptla-sql-md.md)] para recuperar el conjunto de registros de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0911b-107">The `OleDbDataAdpater` object executes a select [!INCLUDE[TLA#tla_sql](../../../../includes/tlasharptla-sql-md.md)] statement to retrieve the recordset from the database.</span></span> <span data-ttu-id="0911b-108">Los resultados del comando de [!INCLUDE[TLA2#tla_sql](../../../../includes/tla2sharptla-sql-md.md)] se almacenan en una `DataTable` de `DataSet` mediante una llamada al método `Fill` de `OleDbDataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="0911b-108">The results from the [!INCLUDE[TLA2#tla_sql](../../../../includes/tla2sharptla-sql-md.md)] command are stored in a `DataTable` of the `DataSet` by calling the `Fill` method of the `OleDbDataAdapter`.</span></span> <span data-ttu-id="0911b-109">El elemento `DataTable` de este ejemplo se denomina `BookTable`.</span><span class="sxs-lookup"><span data-stu-id="0911b-109">The `DataTable` in this example is named `BookTable`.</span></span> <span data-ttu-id="0911b-110">En el ejemplo, a continuación, Establece el <xref:System.Windows.FrameworkElement.DataContext%2A> propiedad de la <xref:System.Windows.Controls.ListBox> a la `DataSet` objeto.</span><span class="sxs-lookup"><span data-stu-id="0911b-110">The example then sets the <xref:System.Windows.FrameworkElement.DataContext%2A> property of the <xref:System.Windows.Controls.ListBox> to the `DataSet` object.</span></span>  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <span data-ttu-id="0911b-111">A continuación, podemos enlazar el <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> propiedad de la <xref:System.Windows.Controls.ListBox> a `BookTable` de la `DataSet`:</span><span class="sxs-lookup"><span data-stu-id="0911b-111">We can then bind the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to `BookTable` of the `DataSet`:</span></span>  
  
 [!code-xaml[ADODataSet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="0911b-112">`BookItemTemplate` es el <xref:System.Windows.DataTemplate> que define cómo aparecen los datos:</span><span class="sxs-lookup"><span data-stu-id="0911b-112">`BookItemTemplate` is the <xref:System.Windows.DataTemplate> that defines how the data appears:</span></span>  
  
 [!code-xaml[ADODataSet#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#3)]  
  
 <span data-ttu-id="0911b-113">`IntColorConverter` convierte un valor `int` en un color.</span><span class="sxs-lookup"><span data-stu-id="0911b-113">The `IntColorConverter` converts an `int` to a color.</span></span> <span data-ttu-id="0911b-114">Con el uso de este convertidor, el <xref:System.Windows.Controls.TextBlock.Background%2A> color del tercer <xref:System.Windows.Controls.TextBlock> debe aparecer en verde si el valor de `NumPages` es inferior a 350 y rojo, en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="0911b-114">With the use of this converter, the <xref:System.Windows.Controls.TextBlock.Background%2A> color of the third <xref:System.Windows.Controls.TextBlock> appears green if the value of `NumPages` is less than 350 and red otherwise.</span></span> <span data-ttu-id="0911b-115">La implementación del convertidor no se muestra aquí.</span><span class="sxs-lookup"><span data-stu-id="0911b-115">The implementation of the converter is not shown here.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0911b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="0911b-116">See also</span></span>
- <xref:System.Windows.Data.BindingListCollectionView>
- [<span data-ttu-id="0911b-117">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="0911b-117">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [<span data-ttu-id="0911b-118">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="0911b-118">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)

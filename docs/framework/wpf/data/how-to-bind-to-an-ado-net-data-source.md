---
title: 'Cómo: Enlazar a un origen de datos ADO.NET'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to ADO.NET data sources
- ADO.NET data sources [WPF], binding to
- binding [WPF], to ADO.NET data sources
ms.assetid: a70c6d7b-7b38-4fdf-b655-4804db7c8315
ms.openlocfilehash: 0b3d7147f45bee5e8abd95bdc51c5f5f695cf830
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458409"
---
# <a name="how-to-bind-to-an-adonet-data-source"></a>Cómo: Enlazar a un origen de datos ADO.NET

En este ejemplo se muestra cómo enlazar un control de <xref:System.Windows.Controls.ListBox> de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] a un `DataSet`de ADO.NET.

## <a name="example"></a>Ejemplo

En este ejemplo, se utiliza un objeto `OleDbConnection` para conectar al origen de datos, que es un archivo `Access MDB` especificado en la cadena de conexión. Una vez establecida la conexión, se crea un objeto `OleDbDataAdapter`. El objeto `OleDbDataAdapter` ejecuta una instrucción SELECT Lenguaje de consulta estructurado (SQL) para recuperar el conjunto de registros de la base de datos. Los resultados del comando SQL se almacenan en un `DataTable` del `DataSet` llamando al método `Fill` del `OleDbDataAdapter`. El elemento `DataTable` de este ejemplo se denomina `BookTable`. A continuación, en el ejemplo se establece la propiedad <xref:System.Windows.FrameworkElement.DataContext%2A> del <xref:System.Windows.Controls.ListBox> en el objeto `DataSet`.

[!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
[!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]

A continuación, podemos enlazar la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> del <xref:System.Windows.Controls.ListBox> a `BookTable` del `DataSet`:

[!code-xaml[ADODataSet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#2)]

`BookItemTemplate` es el <xref:System.Windows.DataTemplate> que define cómo aparecen los datos:

[!code-xaml[ADODataSet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#3)]

`IntColorConverter` convierte un valor `int` en un color. Con el uso de este convertidor, el color <xref:System.Windows.Controls.TextBlock.Background%2A> del tercer <xref:System.Windows.Controls.TextBlock> aparece en verde si el valor de `NumPages` es menor que 350 y rojo en caso contrario. La implementación del convertidor no se muestra aquí.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Data.BindingListCollectionView>
- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)

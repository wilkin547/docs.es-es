---
title: 'Cómo: Crear un elemento Grid'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], grid instance
ms.assetid: b2f07626-9df8-43b8-8d36-492f3cb42837
ms.openlocfilehash: b93bb859c4a0df50da2fa00587a28fda3776fd09
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185789"
---
# <a name="how-to-create-a-grid-element"></a>Cómo: Crear un elemento Grid
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo crear y usar una instancia de <xref:System.Windows.Controls.Grid> utilizando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] o código. En este ejemplo usa tres <xref:System.Windows.Controls.ColumnDefinition> objetos y tres <xref:System.Windows.Controls.RowDefinition> objetos crear una cuadrícula que tiene nueve celdas, como se muestra en una hoja de cálculo. Cada celda contiene un <xref:System.Windows.Controls.TextBlock> elemento que representa los datos y la fila superior contiene un <xref:System.Windows.Controls.TextBlock> con el <xref:System.Windows.Controls.Grid.ColumnSpan%2A> propiedad aplicada. Para mostrar los límites de cada celda, el <xref:System.Windows.Controls.Grid.ShowGridLines%2A> propiedad está habilitada.  
  
 [!code-csharp[Grid#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Grid/CSharp/Grid_Code.cs#3)]
 [!code-vb[Grid#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Grid/VisualBasic/grid_vb.vb#3)]
 [!code-xaml[Grid#3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Grid/XAML/default.xaml#3)]  
  
  Cualquier enfoque generará una interfaz de usuario que se asemeja en gran medida la misma, como la siguiente:.

  ![una captura de pantalla muestra una interfaz de usuario WPF que contiene una cuadrícula dividida en tres columnas.  Lleve el encabezado '2018 productos enviados' que abarca todas las columnas de la fila superior y tiene tres columnas con las cifras de ventas para un determinado trimestre.  La fila inferior contiene el texto que abarca dos columnas con el mensaje "Total de unidades: 300.000'](./media/how-to-create-a-grid-element/how-to-create-a-grid-element.png)
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.Grid>  
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)

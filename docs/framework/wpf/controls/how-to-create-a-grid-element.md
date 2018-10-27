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
# <a name="how-to-create-a-grid-element"></a><span data-ttu-id="30e6b-102">Cómo: Crear un elemento Grid</span><span class="sxs-lookup"><span data-stu-id="30e6b-102">How to: Create a Grid Element</span></span>
## <a name="example"></a><span data-ttu-id="30e6b-103">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="30e6b-103">Example</span></span>  
 <span data-ttu-id="30e6b-104">El ejemplo siguiente muestra cómo crear y usar una instancia de <xref:System.Windows.Controls.Grid> utilizando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] o código.</span><span class="sxs-lookup"><span data-stu-id="30e6b-104">The following example shows how to create and use an instance of <xref:System.Windows.Controls.Grid> by using either [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] or code.</span></span> <span data-ttu-id="30e6b-105">En este ejemplo usa tres <xref:System.Windows.Controls.ColumnDefinition> objetos y tres <xref:System.Windows.Controls.RowDefinition> objetos crear una cuadrícula que tiene nueve celdas, como se muestra en una hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="30e6b-105">This example uses three <xref:System.Windows.Controls.ColumnDefinition> objects and three <xref:System.Windows.Controls.RowDefinition> objects to create a grid that has nine cells, such as in a worksheet.</span></span> <span data-ttu-id="30e6b-106">Cada celda contiene un <xref:System.Windows.Controls.TextBlock> elemento que representa los datos y la fila superior contiene un <xref:System.Windows.Controls.TextBlock> con el <xref:System.Windows.Controls.Grid.ColumnSpan%2A> propiedad aplicada.</span><span class="sxs-lookup"><span data-stu-id="30e6b-106">Each cell contains a <xref:System.Windows.Controls.TextBlock> element that represents data, and the top row contains a <xref:System.Windows.Controls.TextBlock> with the <xref:System.Windows.Controls.Grid.ColumnSpan%2A> property applied.</span></span> <span data-ttu-id="30e6b-107">Para mostrar los límites de cada celda, el <xref:System.Windows.Controls.Grid.ShowGridLines%2A> propiedad está habilitada.</span><span class="sxs-lookup"><span data-stu-id="30e6b-107">To show the boundaries of each cell, the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property is enabled.</span></span>  
  
 [!code-csharp[Grid#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Grid/CSharp/Grid_Code.cs#3)]
 [!code-vb[Grid#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Grid/VisualBasic/grid_vb.vb#3)]
 [!code-xaml[Grid#3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Grid/XAML/default.xaml#3)]  
  
  <span data-ttu-id="30e6b-108">Cualquier enfoque generará una interfaz de usuario que se asemeja en gran medida la misma, como la siguiente:.</span><span class="sxs-lookup"><span data-stu-id="30e6b-108">Either approach will generate a user interface that looks much the same, like the one below.</span></span>

  ![una captura de pantalla muestra una interfaz de usuario WPF que contiene una cuadrícula dividida en tres columnas.](./media/how-to-create-a-grid-element/how-to-create-a-grid-element.png)
## <a name="see-also"></a><span data-ttu-id="30e6b-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="30e6b-112">See Also</span></span>  
 <xref:System.Windows.Controls.Grid>  
 [<span data-ttu-id="30e6b-113">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="30e6b-113">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)

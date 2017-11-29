---
title: "Cómo: Crear un cuadro de diálogo estándar de interfaz de usuario mediante Grid"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 641e74d8c9f8db1afde19c008de08f0029b0bf90
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a><span data-ttu-id="83eaa-102">Cómo: Crear un cuadro de diálogo estándar de interfaz de usuario mediante Grid</span><span class="sxs-lookup"><span data-stu-id="83eaa-102">How to: Build a Standard UI Dialog Box by Using Grid</span></span>
<span data-ttu-id="83eaa-103">Este ejemplo muestra cómo crear un estándar [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] cuadro de diálogo mediante el uso de la <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="83eaa-103">This example shows how to create a standard [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dialog box by using the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83eaa-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="83eaa-104">Example</span></span>  
 <span data-ttu-id="83eaa-105">En el ejemplo siguiente se crea un cuadro de diálogo como el **ejecutar** cuadro de diálogo en el [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="83eaa-105">The following example creates a dialog box like the **Run** dialog box in the [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] operating system.</span></span>  
  
 <span data-ttu-id="83eaa-106">El ejemplo se crea un <xref:System.Windows.Controls.Grid> y usa el <xref:System.Windows.Controls.ColumnDefinition> y <xref:System.Windows.Controls.RowDefinition> las clases para definir cinco columnas y cuatro filas.</span><span class="sxs-lookup"><span data-stu-id="83eaa-106">The example creates a <xref:System.Windows.Controls.Grid> and uses the <xref:System.Windows.Controls.ColumnDefinition> and <xref:System.Windows.Controls.RowDefinition> classes to define five columns and four rows.</span></span>  
  
 <span data-ttu-id="83eaa-107">En el ejemplo, a continuación, agrega y coloca un <xref:System.Windows.Controls.Image>, `RunIcon.png`, para representar la imagen que se encuentra en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="83eaa-107">The example then adds and positions an <xref:System.Windows.Controls.Image>, `RunIcon.png`, to represent the image that is found in the dialog box.</span></span> <span data-ttu-id="83eaa-108">La imagen se coloca en la primera columna y fila de la <xref:System.Windows.Controls.Grid> (la esquina superior izquierda).</span><span class="sxs-lookup"><span data-stu-id="83eaa-108">The image is placed in the first column and row of the <xref:System.Windows.Controls.Grid> (the upper-left corner).</span></span>  
  
 <span data-ttu-id="83eaa-109">A continuación, en el ejemplo se agrega un <xref:System.Windows.Controls.TextBlock> elemento a la primera columna, que abarca las columnas restantes de la primera fila.</span><span class="sxs-lookup"><span data-stu-id="83eaa-109">Next, the example adds a <xref:System.Windows.Controls.TextBlock> element to the first column, which spans the remaining columns of the first row.</span></span> <span data-ttu-id="83eaa-110">Agrega otro <xref:System.Windows.Controls.TextBlock> elemento a la segunda fila de la primera columna, para representar la **abiertos** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="83eaa-110">It adds another <xref:System.Windows.Controls.TextBlock> element to the second row in the first column, to represent the **Open** text box.</span></span> <span data-ttu-id="83eaa-111">Un <xref:System.Windows.Controls.TextBlock> se indica a continuación, que representa el área de entrada de datos.</span><span class="sxs-lookup"><span data-stu-id="83eaa-111">A <xref:System.Windows.Controls.TextBlock> follows, which represents the data entry area.</span></span>  
  
 <span data-ttu-id="83eaa-112">Por último, el ejemplo agrega tres <xref:System.Windows.Controls.Button> elementos a la fila final, que representan el **Aceptar**, **cancelar**, y **examinar** eventos.</span><span class="sxs-lookup"><span data-stu-id="83eaa-112">Finally, the example adds three <xref:System.Windows.Controls.Button> elements to the final row, which represent the **OK**, **Cancel**, and **Browse** events.</span></span>  
  
 [!code-csharp[GridRunDialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="83eaa-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="83eaa-113">See Also</span></span>  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.GridUnitType>  
 [<span data-ttu-id="83eaa-114">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="83eaa-114">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="83eaa-115">Temas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="83eaa-115">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/grid-how-to-topics.md)

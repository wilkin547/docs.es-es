---
title: Funcionalidad predeterminada en el control DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
ms.openlocfilehash: b695883ac7ec3fb0c459adb66214b0eceab3a128
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746134"
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="2ce1a-102">Funcionalidad predeterminada en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2ce1a-102">Default Functionality in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2ce1a-103">El control Windows Forms <xref:System.Windows.Forms.DataGridView> proporciona a los usuarios una cantidad significativa de funcionalidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2ce1a-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control provides users with a significant amount of default functionality.</span></span>  
  
## <a name="default-functionality"></a><span data-ttu-id="2ce1a-104">Funcionalidad predeterminada</span><span class="sxs-lookup"><span data-stu-id="2ce1a-104">Default Functionality</span></span>  
 <span data-ttu-id="2ce1a-105">De forma predeterminada, un control <xref:System.Windows.Forms.DataGridView>:</span><span class="sxs-lookup"><span data-stu-id="2ce1a-105">By default, a <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
- <span data-ttu-id="2ce1a-106">Muestra automáticamente los encabezados de columna y los encabezados de fila que permanecen visibles cuando la tabla se desplaza verticalmente.</span><span class="sxs-lookup"><span data-stu-id="2ce1a-106">Automatically displays column headers and row headers that remain visible as the table scrolls vertically.</span></span>  
  
- <span data-ttu-id="2ce1a-107">Tiene un encabezado de fila que contiene un indicador de selección para la fila actual.</span><span class="sxs-lookup"><span data-stu-id="2ce1a-107">Has a row header that contains a selection indicator for the current row.</span></span>  
  
- <span data-ttu-id="2ce1a-108">Tiene un rectángulo de selección en la primera celda.</span><span class="sxs-lookup"><span data-stu-id="2ce1a-108">Has a selection rectangle in the first cell.</span></span>  
  
- <span data-ttu-id="2ce1a-109">Tiene columnas a las que se puede cambiar el tamaño automáticamente cuando el usuario hace doble clic en los divisores de columna.</span><span class="sxs-lookup"><span data-stu-id="2ce1a-109">Has columns that can be automatically resized when the user double-clicks the column dividers.</span></span>  
  
- <span data-ttu-id="2ce1a-110">Admite automáticamente los estilos visuales en Windows XP y la familia de Windows Server 2003 cuando se llama al método <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> desde el método de `Main` de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2ce1a-110">Automatically supports visual styles on Windows XP and the Windows Server 2003 family when the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method is called from the application's `Main` method.</span></span>  
  
 <span data-ttu-id="2ce1a-111">Además, el contenido de un control <xref:System.Windows.Forms.DataGridView> se puede editar de forma predeterminada:</span><span class="sxs-lookup"><span data-stu-id="2ce1a-111">Additionally, the contents of a <xref:System.Windows.Forms.DataGridView> control can be edited by default:</span></span>  
  
- <span data-ttu-id="2ce1a-112">Si el usuario hace doble clic o presiona F2 en una celda, el control coloca automáticamente la celda en modo de edición y actualiza el contenido de la celda a medida que el usuario escribe.</span><span class="sxs-lookup"><span data-stu-id="2ce1a-112">If the user double-clicks or presses F2 in a cell, the control automatically puts the cell into edit mode and updates the contents of the cell as the user types.</span></span>  
  
- <span data-ttu-id="2ce1a-113">Si el usuario se desplaza hasta el final de la cuadrícula, el usuario verá que hay una fila para agregar nuevos registros.</span><span class="sxs-lookup"><span data-stu-id="2ce1a-113">If the user scrolls to the end of the grid, the user will see that a row for adding new records is present.</span></span> <span data-ttu-id="2ce1a-114">Cuando el usuario hace clic en esta fila, se agrega una nueva fila al control <xref:System.Windows.Forms.DataGridView>, con los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="2ce1a-114">When the user clicks this row, a new row is added to the <xref:System.Windows.Forms.DataGridView> control, with default values.</span></span> <span data-ttu-id="2ce1a-115">Cuando el usuario presiona ESC, esta nueva fila desaparece.</span><span class="sxs-lookup"><span data-stu-id="2ce1a-115">When the user presses ESC, this new row disappears.</span></span>  
  
- <span data-ttu-id="2ce1a-116">Si el usuario hace clic en un encabezado de fila, se selecciona toda la fila.</span><span class="sxs-lookup"><span data-stu-id="2ce1a-116">If the user clicks a row header, the whole row is selected.</span></span>  
  
 <span data-ttu-id="2ce1a-117">Al enlazar un control de <xref:System.Windows.Forms.DataGridView> a un origen de datos estableciendo su propiedad <xref:System.Windows.Forms.DataGridView.DataSource%2A>, el control:</span><span class="sxs-lookup"><span data-stu-id="2ce1a-117">When you bind a <xref:System.Windows.Forms.DataGridView> control to a data source by setting its <xref:System.Windows.Forms.DataGridView.DataSource%2A> property, the control:</span></span>  
  
- <span data-ttu-id="2ce1a-118">Usa automáticamente los nombres de las columnas del origen de datos como texto de encabezado de columna.</span><span class="sxs-lookup"><span data-stu-id="2ce1a-118">Automatically uses the names of the data source's columns as the column header text.</span></span>  
  
- <span data-ttu-id="2ce1a-119">Se rellena con el contenido del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="2ce1a-119">Is populated with the contents of the data source.</span></span> <span data-ttu-id="2ce1a-120"><xref:System.Windows.Forms.DataGridView> columnas se crean automáticamente para cada columna del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="2ce1a-120"><xref:System.Windows.Forms.DataGridView> columns are automatically created for each column in the data source.</span></span>  
  
- <span data-ttu-id="2ce1a-121">Crea una fila para cada fila visible de la tabla.</span><span class="sxs-lookup"><span data-stu-id="2ce1a-121">Creates a row for each visible row in the table.</span></span>  
  
- <span data-ttu-id="2ce1a-122">Ordena automáticamente las filas basándose en los datos subyacentes cuando el usuario hace clic en un encabezado de columna.</span><span class="sxs-lookup"><span data-stu-id="2ce1a-122">Automatically sorts the rows based on the underlying data when the user clicks a column header.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ce1a-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2ce1a-123">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="2ce1a-124">DataGridView (control)</span><span class="sxs-lookup"><span data-stu-id="2ce1a-124">DataGridView Control</span></span>](datagridview-control-windows-forms.md)

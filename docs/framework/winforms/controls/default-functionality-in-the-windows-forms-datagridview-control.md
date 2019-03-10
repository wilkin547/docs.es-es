---
title: Funcionalidad predeterminada en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
ms.openlocfilehash: 0c0d24111a2fdf856ff1f4ce154ec85afbbd61ee
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57719668"
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="93461-102">Funcionalidad predeterminada en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="93461-102">Default Functionality in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="93461-103">Los formularios de Windows <xref:System.Windows.Forms.DataGridView> control proporciona a los usuarios con una cantidad considerable de funcionalidad de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="93461-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control provides users with a significant amount of default functionality.</span></span>  
  
## <a name="default-functionality"></a><span data-ttu-id="93461-104">Funcionalidad predeterminada</span><span class="sxs-lookup"><span data-stu-id="93461-104">Default Functionality</span></span>  
 <span data-ttu-id="93461-105">De forma predeterminada, un <xref:System.Windows.Forms.DataGridView> control:</span><span class="sxs-lookup"><span data-stu-id="93461-105">By default, a <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
-   <span data-ttu-id="93461-106">Muestra automáticamente los encabezados de columna y encabezados de fila que permanecen visibles cuando la tabla se desplaza verticalmente.</span><span class="sxs-lookup"><span data-stu-id="93461-106">Automatically displays column headers and row headers that remain visible as the table scrolls vertically.</span></span>  
  
-   <span data-ttu-id="93461-107">Tiene un encabezado de fila que contiene un indicador de selección de la fila actual.</span><span class="sxs-lookup"><span data-stu-id="93461-107">Has a row header that contains a selection indicator for the current row.</span></span>  
  
-   <span data-ttu-id="93461-108">Tiene un rectángulo de selección en la primera celda.</span><span class="sxs-lookup"><span data-stu-id="93461-108">Has a selection rectangle in the first cell.</span></span>  
  
-   <span data-ttu-id="93461-109">Tiene columnas que pueden ser de tamaño automáticamente cuando el usuario hace doble clic en los divisores de columna.</span><span class="sxs-lookup"><span data-stu-id="93461-109">Has columns that can be automatically resized when the user double-clicks the column dividers.</span></span>  
  
-   <span data-ttu-id="93461-110">Admite automáticamente los estilos visuales en Windows XP y la familia Windows Server 2003 cuando los <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> se llama al método de la aplicación `Main` método.</span><span class="sxs-lookup"><span data-stu-id="93461-110">Automatically supports visual styles on Windows XP and the Windows Server 2003 family when the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method is called from the application's `Main` method.</span></span>  
  
 <span data-ttu-id="93461-111">Además, el contenido de un <xref:System.Windows.Forms.DataGridView> control puede modificarse de forma predeterminada:</span><span class="sxs-lookup"><span data-stu-id="93461-111">Additionally, the contents of a <xref:System.Windows.Forms.DataGridView> control can be edited by default:</span></span>  
  
-   <span data-ttu-id="93461-112">Si el usuario hace doble clic o presiona F2 en una celda, el control automáticamente coloca la celda en modo de edición y actualiza el contenido de la celda cuando el usuario escribe.</span><span class="sxs-lookup"><span data-stu-id="93461-112">If the user double-clicks or presses F2 in a cell, the control automatically puts the cell into edit mode and updates the contents of the cell as the user types.</span></span>  
  
-   <span data-ttu-id="93461-113">Si el usuario se desplaza hasta el final de la cuadrícula, el usuario verá que una fila para agregar nuevos registros está presente.</span><span class="sxs-lookup"><span data-stu-id="93461-113">If the user scrolls to the end of the grid, the user will see that a row for adding new records is present.</span></span> <span data-ttu-id="93461-114">Cuando el usuario hace clic en esta fila, se agrega una nueva fila a la <xref:System.Windows.Forms.DataGridView> control con los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="93461-114">When the user clicks this row, a new row is added to the <xref:System.Windows.Forms.DataGridView> control, with default values.</span></span> <span data-ttu-id="93461-115">Cuando el usuario presiona ESC, esta nueva fila desaparece.</span><span class="sxs-lookup"><span data-stu-id="93461-115">When the user presses ESC, this new row disappears.</span></span>  
  
-   <span data-ttu-id="93461-116">Si el usuario hace clic en un encabezado de fila, se selecciona la fila completa.</span><span class="sxs-lookup"><span data-stu-id="93461-116">If the user clicks a row header, the whole row is selected.</span></span>  
  
 <span data-ttu-id="93461-117">Al enlazar un <xref:System.Windows.Forms.DataGridView> control a un origen de datos estableciendo su <xref:System.Windows.Forms.DataGridView.DataSource%2A> propiedad, el control:</span><span class="sxs-lookup"><span data-stu-id="93461-117">When you bind a <xref:System.Windows.Forms.DataGridView> control to a data source by setting its <xref:System.Windows.Forms.DataGridView.DataSource%2A> property, the control:</span></span>  
  
-   <span data-ttu-id="93461-118">Usa automáticamente los nombres de columnas del origen de datos como el texto del encabezado de columna.</span><span class="sxs-lookup"><span data-stu-id="93461-118">Automatically uses the names of the data source's columns as the column header text.</span></span>  
  
-   <span data-ttu-id="93461-119">Se rellena con el contenido del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="93461-119">Is populated with the contents of the data source.</span></span> <span data-ttu-id="93461-120"><xref:System.Windows.Forms.DataGridView> las columnas se crean automáticamente para cada columna del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="93461-120"><xref:System.Windows.Forms.DataGridView> columns are automatically created for each column in the data source.</span></span>  
  
-   <span data-ttu-id="93461-121">Crea una fila para cada fila visible en la tabla.</span><span class="sxs-lookup"><span data-stu-id="93461-121">Creates a row for each visible row in the table.</span></span>  
  
-   <span data-ttu-id="93461-122">Se ordena automáticamente las filas basándose en los datos subyacentes cuando el usuario hace clic en un encabezado de columna.</span><span class="sxs-lookup"><span data-stu-id="93461-122">Automatically sorts the rows based on the underlying data when the user clicks a column header.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93461-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="93461-123">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="93461-124">DataGridView (control)</span><span class="sxs-lookup"><span data-stu-id="93461-124">DataGridView Control</span></span>](datagridview-control-windows-forms.md)

---
title: Cambiar el orden de las columnas en el control DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], changing order
- DataGridView control [Windows Forms], column order
- data grids [Windows Forms], changing column order
ms.assetid: 5e9ac3bc-b0f0-48cb-a3d5-b005af905395
ms.openlocfilehash: 2aef196e9544a81f42a563783ce6c357869aa247
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746548"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="bc9df-102">Cómo: Cambiar el orden de las columnas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bc9df-102">How to: Change the Order of Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="bc9df-103">Cuando se usa un control <xref:System.Windows.Forms.DataGridView> para mostrar datos desde un origen de datos, a veces las columnas del esquema del origen de datos no aparecen en el orden que quiere que se muestren.</span><span class="sxs-lookup"><span data-stu-id="bc9df-103">When you use a <xref:System.Windows.Forms.DataGridView> to display data from a data source, the columns in the data source's schema sometimes do not appear in the order you would like to display them.</span></span> <span data-ttu-id="bc9df-104">Puede cambiar el orden de visualización de las columnas mediante la propiedad <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A> de la clase <xref:System.Windows.Forms.DataGridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="bc9df-104">You can change the displayed order of the columns by using the <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A> property of the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>  
  
 <span data-ttu-id="bc9df-105">En el ejemplo de código siguiente, se cambia de posición de algunas de las columnas generadas automáticamente cuando se enlaza a la tabla Customers de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="bc9df-105">The following code example repositions some of the columns automatically generated when binding to the Customers table in the Northwind sample database.</span></span> <span data-ttu-id="bc9df-106">Para obtener más información sobre cómo enlazar el control <xref:System.Windows.Forms.DataGridView> a una tabla de base de datos, vea [Cómo: enlazar datos al control DataGridView Windows Forms](how-to-bind-data-to-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="bc9df-106">For more information about how to bind the <xref:System.Windows.Forms.DataGridView> control to a database table, see [How to: Bind Data to the Windows Forms DataGridView Control](how-to-bind-data-to-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="bc9df-107">Visual Studio es compatible con esta tarea.</span><span class="sxs-lookup"><span data-stu-id="bc9df-107">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="bc9df-108">Consulte también [Cómo: cambiar el orden de las columnas en el control DataGridView Windows Forms mediante el diseñador](change-the-order-of-columns-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="bc9df-108">Also see [How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer](change-the-order-of-columns-in-the-datagrid-using-the-designer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc9df-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bc9df-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#040](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#040)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#040](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#040)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bc9df-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="bc9df-110">Compiling the Code</span></span>  
 <span data-ttu-id="bc9df-111">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="bc9df-111">This example requires:</span></span>  
  
- <span data-ttu-id="bc9df-112">Un control <xref:System.Windows.Forms.DataGridView> denominado `customersDataGridView` que está enlazado a una tabla con los nombres de columna indicados, como la tabla `Customers` en la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="bc9df-112">A <xref:System.Windows.Forms.DataGridView> control named `customersDataGridView` that is bound to a table with the indicated column names, such as the `Customers` table in the Northwind sample database.</span></span>  
  
- <span data-ttu-id="bc9df-113">Referencias a los ensamblados <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType> y <xref:System.Xml?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bc9df-113">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType>, and <xref:System.Xml?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc9df-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc9df-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [<span data-ttu-id="bc9df-115">Mostrar datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bc9df-115">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="bc9df-116">Enlazar datos al control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bc9df-116">How to: Bind Data to the Windows Forms DataGridView Control</span></span>](how-to-bind-data-to-the-windows-forms-datagridview-control.md)

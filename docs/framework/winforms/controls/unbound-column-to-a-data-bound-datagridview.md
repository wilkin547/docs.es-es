---
title: Agregar una columna independiente a un control DataGridView enlazado a datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], unbound data
- data grids [Windows Forms], adding unbound columns
- DataGridView control [Windows Forms], unbound data
ms.assetid: f7bdc4d8-ba8e-421b-ad62-82d936f01372
ms.openlocfilehash: 807bbc121f33c35d70068571e76637c078ecb3da
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747066"
---
# <a name="how-to-add-an-unbound-column-to-a-data-bound-windows-forms-datagridview-control"></a><span data-ttu-id="71da5-102">Cómo: Agregar una columna independiente a un control DataGridView de formularios Windows Forms enlazado a datos</span><span class="sxs-lookup"><span data-stu-id="71da5-102">How to: Add an Unbound Column to a Data-Bound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="71da5-103">Los datos que muestra en el control <xref:System.Windows.Forms.DataGridView> proceden por lo general de un origen de datos, pero es posible que desee mostrar una columna de datos que no proceda de dicho origen de datos.</span><span class="sxs-lookup"><span data-stu-id="71da5-103">The data you display in the <xref:System.Windows.Forms.DataGridView> control will normally come from a data source of some kind, but you might want to display a column of data that does not come from the data source.</span></span> <span data-ttu-id="71da5-104">Este tipo de columna se denomina columna independiente.</span><span class="sxs-lookup"><span data-stu-id="71da5-104">This kind of column is called an unbound column.</span></span> <span data-ttu-id="71da5-105">Las columnas independientes pueden adoptar muchas formas.</span><span class="sxs-lookup"><span data-stu-id="71da5-105">Unbound columns can take many forms.</span></span> <span data-ttu-id="71da5-106">Con frecuencia, se utilizan para permitir acceder a los detalles de una fila de datos.</span><span class="sxs-lookup"><span data-stu-id="71da5-106">Frequently, they are used to provide access to the details of a data row.</span></span>  
  
 <span data-ttu-id="71da5-107">En el ejemplo de código siguiente se muestra cómo crear una columna sin enlazar botones de **detalles** para mostrar una tabla secundaria relacionada con una fila concreta de una tabla primaria al implementar un escenario principal/detalle.</span><span class="sxs-lookup"><span data-stu-id="71da5-107">The following code example demonstrates how to create an unbound column of **Details** buttons to display a child table related to a particular row in a parent table when you implement a master/detail scenario.</span></span> <span data-ttu-id="71da5-108">Para responder a los clics en los botones, implemente un controlador de eventos <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> que muestra un formulario que contiene la tabla secundaria.</span><span class="sxs-lookup"><span data-stu-id="71da5-108">To respond to button clicks, implement a <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> event handler that displays a form containing the child table.</span></span>  
  
 <span data-ttu-id="71da5-109">Visual Studio es compatible con esta tarea.</span><span class="sxs-lookup"><span data-stu-id="71da5-109">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="71da5-110">Consulte también [Cómo: agregar y quitar columnas en el control DataGridView Windows Forms mediante el diseñador](add-and-remove-columns-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="71da5-110">Also see [How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer](add-and-remove-columns-in-the-datagrid-using-the-designer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="71da5-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="71da5-111">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#010](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#010)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#010](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#010)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="71da5-112">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="71da5-112">Compiling the Code</span></span>  
 <span data-ttu-id="71da5-113">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="71da5-113">This example requires:</span></span>  
  
- <span data-ttu-id="71da5-114">Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="71da5-114">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="71da5-115">Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="71da5-115">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71da5-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="71da5-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="71da5-117">Mostrar datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="71da5-117">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="71da5-118">Modos de presentación de datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="71da5-118">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)

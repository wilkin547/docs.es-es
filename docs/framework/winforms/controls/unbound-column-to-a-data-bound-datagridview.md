---
title: Filtrar Agregar una columna independiente a un Control DataGridView de formularios de Windows enlazados a datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], unbound data
- data grids [Windows Forms], adding unbound columns
- DataGridView control [Windows Forms], unbound data
ms.assetid: f7bdc4d8-ba8e-421b-ad62-82d936f01372
ms.openlocfilehash: d7f96aa8d11cee9427a9e51f8e79fc55adc79355
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57712022"
---
# <a name="how-to-add-an-unbound-column-to-a-data-bound-windows-forms-datagridview-control"></a><span data-ttu-id="b89ea-102">Filtrar Agregar una columna independiente a un Control DataGridView de formularios de Windows enlazados a datos</span><span class="sxs-lookup"><span data-stu-id="b89ea-102">How to: Add an Unbound Column to a Data-Bound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="b89ea-103">Los datos que muestra en el control <xref:System.Windows.Forms.DataGridView> proceden por lo general de un origen de datos, pero es posible que desee mostrar una columna de datos que no proceda de dicho origen de datos.</span><span class="sxs-lookup"><span data-stu-id="b89ea-103">The data you display in the <xref:System.Windows.Forms.DataGridView> control will normally come from a data source of some kind, but you might want to display a column of data that does not come from the data source.</span></span> <span data-ttu-id="b89ea-104">Este tipo de columna se denomina columna independiente.</span><span class="sxs-lookup"><span data-stu-id="b89ea-104">This kind of column is called an unbound column.</span></span> <span data-ttu-id="b89ea-105">Las columnas independientes pueden adoptar muchas formas.</span><span class="sxs-lookup"><span data-stu-id="b89ea-105">Unbound columns can take many forms.</span></span> <span data-ttu-id="b89ea-106">Con frecuencia, se utilizan para permitir acceder a los detalles de una fila de datos.</span><span class="sxs-lookup"><span data-stu-id="b89ea-106">Frequently, they are used to provide access to the details of a data row.</span></span>  
  
 <span data-ttu-id="b89ea-107">En el ejemplo de código siguiente se muestra cómo crear una columna independiente de **detalles** botones para mostrar una tabla secundaria relacionada con una fila determinada en una tabla primaria al implementar un escenario principal-detalle.</span><span class="sxs-lookup"><span data-stu-id="b89ea-107">The following code example demonstrates how to create an unbound column of **Details** buttons to display a child table related to a particular row in a parent table when you implement a master/detail scenario.</span></span> <span data-ttu-id="b89ea-108">Para responder a los clics en los botones, implemente un controlador de eventos <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> que muestra un formulario que contiene la tabla secundaria. </span><span class="sxs-lookup"><span data-stu-id="b89ea-108">To respond to button clicks, implement a <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> event handler that displays a form containing the child table.</span></span>  
  
 <span data-ttu-id="b89ea-109">Visual Studio es compatible con esta tarea.</span><span class="sxs-lookup"><span data-stu-id="b89ea-109">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="b89ea-110">Consulte también [Cómo: Agregar y quitar columnas en la Windows Forms mediante el Diseñador de Control de DataGridView](add-and-remove-columns-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="b89ea-110">Also see [How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer](add-and-remove-columns-in-the-datagrid-using-the-designer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b89ea-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b89ea-111">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#010](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#010)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#010](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#010)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b89ea-112">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="b89ea-112">Compiling the Code</span></span>  
 <span data-ttu-id="b89ea-113">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="b89ea-113">This example requires:</span></span>  
  
-   <span data-ttu-id="b89ea-114">Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="b89ea-114">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="b89ea-115">Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b89ea-115">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b89ea-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b89ea-116">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="b89ea-117">Mostrar datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b89ea-117">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="b89ea-118">Modos de presentación de datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b89ea-118">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)

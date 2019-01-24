---
title: Procedimiento Especificar valores predeterminados para nuevas filas en el Control DataGridView de formularios de Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], default values for new rows
- DataGridView control [Windows Forms], data entry
- rows [Windows Forms], specifying default values
- DataGridView control [Windows Forms], default values for new rows
ms.assetid: 8d127963-d9f8-4e4e-9f7f-beb66688f1f2
ms.openlocfilehash: dab9ba7ca16cf0c886601e3c8fea579e70b2f30d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596779"
---
# <a name="how-to-specify-default-values-for-new-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="2f4c1-102">Procedimiento Especificar valores predeterminados para nuevas filas en el Control DataGridView de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="2f4c1-102">How to: Specify Default Values for New Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2f4c1-103">Puede hacer que la entrada de datos más conveniente cuando la aplicación rellena los valores predeterminados para las filas recién agregadas.</span><span class="sxs-lookup"><span data-stu-id="2f4c1-103">You can make data entry more convenient when the application fills in default values for newly added rows.</span></span> <span data-ttu-id="2f4c1-104">Con el <xref:System.Windows.Forms.DataGridView> (clase), se pueden rellenar los valores predeterminados con la <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> eventos.</span><span class="sxs-lookup"><span data-stu-id="2f4c1-104">With the <xref:System.Windows.Forms.DataGridView> class, you can fill in default values with the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span> <span data-ttu-id="2f4c1-105">Este evento se desencadena cuando el usuario entra en la fila para los nuevos registros.</span><span class="sxs-lookup"><span data-stu-id="2f4c1-105">This event is raised when the user enters the row for new records.</span></span> <span data-ttu-id="2f4c1-106">Cuando el código controla este evento, puede rellenar deseadas celdas con valores de su elección.</span><span class="sxs-lookup"><span data-stu-id="2f4c1-106">When your code handles this event, you can populate desired cells with values of your choosing.</span></span>  
  
 <span data-ttu-id="2f4c1-107">En el ejemplo de código siguiente se muestra cómo especificar valores predeterminados para nuevas filas mediante el <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> eventos.</span><span class="sxs-lookup"><span data-stu-id="2f4c1-107">The following code example demonstrates how to specify default values for new rows using the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f4c1-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2f4c1-108">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#120)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#120)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2f4c1-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="2f4c1-109">Compiling the Code</span></span>  
 <span data-ttu-id="2f4c1-110">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="2f4c1-110">This example requires:</span></span>  
  
-   <span data-ttu-id="2f4c1-111">Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="2f4c1-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="2f4c1-112">Un `NewCustomerId` función para generar un único `CustomerID` valores.</span><span class="sxs-lookup"><span data-stu-id="2f4c1-112">A `NewCustomerId` function for generating unique `CustomerID` values.</span></span>  
  
-   <span data-ttu-id="2f4c1-113">Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2f4c1-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f4c1-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f4c1-114">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>
- [<span data-ttu-id="2f4c1-115">Entrada de datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2f4c1-115">Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="2f4c1-116">Utilizar la fila de nuevos registros en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2f4c1-116">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)

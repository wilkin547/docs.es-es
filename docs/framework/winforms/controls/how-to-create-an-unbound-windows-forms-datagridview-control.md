---
title: Crear un control DataGridView sin enlazar
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], unbound data
- DataGridView control [Windows Forms], displaying data without binding to a data source
- data [Windows Forms], unbound
ms.assetid: b5d4b47d-9a28-4d88-9dba-0a3c90fba71d
ms.openlocfilehash: 0b477eba6d8455554d72dc7ec8cfce68a91add38
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76730997"
---
# <a name="how-to-create-an-unbound-windows-forms-datagridview-control"></a><span data-ttu-id="29bf4-102">Cómo: Crear un control DataGridView no enlazado en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="29bf4-102">How to: Create an Unbound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="29bf4-103">En el ejemplo de código siguiente se muestra cómo rellenar un control <xref:System.Windows.Forms.DataGridView> mediante programación sin enlazarlo a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="29bf4-103">The following code example demonstrates how to populate a <xref:System.Windows.Forms.DataGridView> control programmatically without binding it to a data source.</span></span> <span data-ttu-id="29bf4-104">Resulta de utilidad cuando tiene una pequeña cantidad de datos que quiere que se muestren en un formato de tabla.</span><span class="sxs-lookup"><span data-stu-id="29bf4-104">This is useful when you have a small amount of data that you want to display in a table format.</span></span>  
  
 <span data-ttu-id="29bf4-105">Para una explicación más completa de este ejemplo de código, vea [Tutorial: Crear un control DataGridView sin enlazar en Windows Forms](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="29bf4-105">For a complete explanation of this code example, see [Walkthrough: Creating an Unbound Windows Forms DataGridView Control](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="29bf4-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="29bf4-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="29bf4-107">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="29bf4-107">Compiling the Code</span></span>  
 <span data-ttu-id="29bf4-108">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="29bf4-108">This example requires:</span></span>  
  
- <span data-ttu-id="29bf4-109">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="29bf4-109">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29bf4-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="29bf4-110">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="29bf4-111">Tutorial: Crear un control DataGridView sin enlazar en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="29bf4-111">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)
- [<span data-ttu-id="29bf4-112">Mostrar datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="29bf4-112">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="29bf4-113">Modos de presentación de datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="29bf4-113">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)

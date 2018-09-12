---
title: 'Cómo: Impedir la adición y eliminación de filas en el control DataGridView de formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], disabling data entry
- data entry [Windows Forms], disabling in grids
- data grids [Windows Forms], disabling data entry
ms.assetid: ef9539ce-539b-404e-84b6-ac282b64b88c
ms.openlocfilehash: 6263c92e6a981983c19e9d7f2357c581bee5ec07
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2018
ms.locfileid: "44508717"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="bccbc-102">Cómo: Impedir la adición y eliminación de filas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bccbc-102">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="bccbc-103">En algunos casos, querrá impedir que los usuarios incluyan nuevas filas de datos o eliminen las filas existentes en el control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="bccbc-103">Sometimes you will want to prevent users from entering new rows of data or deleting existing rows in your <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="bccbc-104">La propiedad <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> indica si la fila para nuevos registros está presente en la parte inferior del control, mientras que la propiedad <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> indica si las filas se pueden quitar.</span><span class="sxs-lookup"><span data-stu-id="bccbc-104">The <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property indicates whether the row for new records is present at the bottom of the control, while the <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> property indicates whether rows can be removed.</span></span> <span data-ttu-id="bccbc-105">El ejemplo de código siguiente utiliza estas propiedades y también establece la propiedad <xref:System.Windows.Forms.DataGridView.ReadOnly%2A> para que el control sea únicamente de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="bccbc-105">The following code example uses these properties and also sets the <xref:System.Windows.Forms.DataGridView.ReadOnly%2A> property to make the control entirely read-only.</span></span>  
  
 <span data-ttu-id="bccbc-106">Visual Studio es compatible con esta tarea.</span><span class="sxs-lookup"><span data-stu-id="bccbc-106">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="bccbc-107">Consulte también [Cómo: impedir la adición de fila y la eliminación de la Windows Forms DataGridView Control mediante el diseñador](https://msdn.microsoft.com/library/k5c88sw3\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="bccbc-107">Also see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer](https://msdn.microsoft.com/library/k5c88sw3\(v=vs.110\)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bccbc-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bccbc-108">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#090](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#090)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#090](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#090)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bccbc-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="bccbc-109">Compiling the Code</span></span>  
 <span data-ttu-id="bccbc-110">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="bccbc-110">This example requires:</span></span>  
  
-   <span data-ttu-id="bccbc-111">Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="bccbc-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="bccbc-112">Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bccbc-112">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bccbc-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="bccbc-113">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.ReadOnly%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="bccbc-114">Características básicas de columnas, filas y celdas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bccbc-114">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)

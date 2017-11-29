---
title: "Cómo: Generar columnas automáticamente en un control DataGridView de formularios Windows Forms enlazado a datos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], autogenerating columns
- columns [Windows Forms], autogenerating
- DataGridView control [Windows Forms], data-bound columns
ms.assetid: 699f6f9e-6aa5-4811-902b-6a2c57dec7d6
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e1d6a790f8a43f4ea2f9d3ad2cdb282186554da6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-autogenerate-columns-in-a-data-bound-windows-forms-datagridview-control"></a><span data-ttu-id="267f1-102">Cómo: Generar columnas automáticamente en un control DataGridView de formularios Windows Forms enlazado a datos</span><span class="sxs-lookup"><span data-stu-id="267f1-102">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="267f1-103">En el ejemplo de código siguiente se muestra cómo mostrar las columnas de un origen de datos enlazados en un <xref:System.Windows.Forms.DataGridView> control.</span><span class="sxs-lookup"><span data-stu-id="267f1-103">The following code example demonstrates how to display columns from a bound data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="267f1-104">Cuando el <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> es el valor de la propiedad `true` (valor predeterminado), un <xref:System.Windows.Forms.DataGridViewColumn> se crea para cada columna de la tabla de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="267f1-104">When the <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> property value is `true` (the default), a <xref:System.Windows.Forms.DataGridViewColumn> is created for each column in the data source table.</span></span>  
  
 <span data-ttu-id="267f1-105">Si el <xref:System.Windows.Forms.DataGridView> control ya tiene columnas cuando se establece la <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> propiedad, el límite existente columnas se comparan con las columnas del origen de datos y conserva cada vez que se encuentra una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="267f1-105">If the <xref:System.Windows.Forms.DataGridView> control already has columns when you set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> property, the existing bound columns are compared to the columns in the data source and preserved whenever there is a match.</span></span> <span data-ttu-id="267f1-106">Columnas sin enlazar siempre se conservan.</span><span class="sxs-lookup"><span data-stu-id="267f1-106">Unbound columns are always preserved.</span></span> <span data-ttu-id="267f1-107">Se quitan las columnas enlazadas para el que no hay ninguna coincidencia en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="267f1-107">Bound columns for which there is no match in the data source are removed.</span></span> <span data-ttu-id="267f1-108">Las columnas del origen de datos para el que no hay ninguna coincidencia en el control generan nuevos <xref:System.Windows.Forms.DataGridViewColumn> objetos, que se agregan al final de la <xref:System.Windows.Forms.DataGridView.Columns%2A> colección.</span><span class="sxs-lookup"><span data-stu-id="267f1-108">Columns in the data source for which there is no match in the control generate new <xref:System.Windows.Forms.DataGridViewColumn> objects, which are added to the end of the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="267f1-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="267f1-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#020](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#020)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#020](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#020)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="267f1-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="267f1-110">Compiling the Code</span></span>  
 <span data-ttu-id="267f1-111">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="267f1-111">This example requires:</span></span>  
  
-   <span data-ttu-id="267f1-112">Un control <xref:System.Windows.Forms.DataGridView> llamado `customersDataGridView`.</span><span class="sxs-lookup"><span data-stu-id="267f1-112">A <xref:System.Windows.Forms.DataGridView> control named `customersDataGridView`.</span></span>  
  
-   <span data-ttu-id="267f1-113">A <xref:System.Data.DataSet> objeto denominado `customersDataSet` que tiene una tabla denominada `Customers`.</span><span class="sxs-lookup"><span data-stu-id="267f1-113">A <xref:System.Data.DataSet> object named `customersDataSet` that has a table named `Customers`.</span></span>  
  
-   <span data-ttu-id="267f1-114">Referencias a los ensamblados <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType> y <xref:System.Xml?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="267f1-114">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType>, and <xref:System.Xml?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="267f1-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="267f1-115">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="267f1-116">Mostrar datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="267f1-116">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="267f1-117">Quitar columnas generadas automáticamente desde un control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="267f1-117">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/remove-autogenerated-columns-from-a-wf-datagridview-control.md)

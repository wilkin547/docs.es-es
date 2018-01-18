---
title: "Cómo: Enlazar un objeto DataView a un control DataGridView de Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 2b73d60a-6049-446a-85a7-3e5a68b183e2
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 70a3004bb074c453ae1ef3aff32df0f657d6531e
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-bind-a-dataview-object-to-a-windows-forms-datagridview-control"></a><span data-ttu-id="95fa4-102">Cómo: Enlazar un objeto DataView a un control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="95fa4-102">How to: Bind a DataView Object to a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="95fa4-103">El control <xref:System.Windows.Forms.DataGridView> proporciona una forma eficaz y flexible de mostrar datos en formato de tabla.</span><span class="sxs-lookup"><span data-stu-id="95fa4-103">The <xref:System.Windows.Forms.DataGridView> control provides a powerful and flexible way to display data in a tabular format.</span></span> <span data-ttu-id="95fa4-104">El control <xref:System.Windows.Forms.DataGridView> admite el modelo de enlace de datos de Windows Forms estándar, por lo que se enlazará a <xref:System.Data.DataView> y a otros orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="95fa4-104">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it will bind to <xref:System.Data.DataView> and a variety of other data sources.</span></span> <span data-ttu-id="95fa4-105">Sin embargo, en la mayoría de las situaciones se enlazará a un componente <xref:System.Windows.Forms.BindingSource> que administrará los detalles de la interacción con el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="95fa4-105">In most situations, however, you will bind to a <xref:System.Windows.Forms.BindingSource> component that will manage the details of interacting with the data source.</span></span>  
  
 <span data-ttu-id="95fa4-106">Para obtener más información sobre la <xref:System.Windows.Forms.DataGridView> control, vea [información general del Control DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="95fa4-106">For more information about the <xref:System.Windows.Forms.DataGridView> control, see [DataGridView Control Overview](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md).</span></span>  
  
### <a name="to-connect-a-datagridview-control-to-a-dataview"></a><span data-ttu-id="95fa4-107">Para conectar un control DataGridView a DataView</span><span class="sxs-lookup"><span data-stu-id="95fa4-107">To connect a DataGridView control to a DataView</span></span>  
  
1.  <span data-ttu-id="95fa4-108">Implemente un método que controle los detalles de recuperación de datos desde una base de datos.</span><span class="sxs-lookup"><span data-stu-id="95fa4-108">Implement a method to handle the details of retrieving data from a database.</span></span> <span data-ttu-id="95fa4-109">En el ejemplo de código siguiente se implementa un método `GetData` que inicializa un componente <xref:System.Data.SqlClient.SqlDataAdapter> y lo utiliza para rellenar un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="95fa4-109">The following code example implements a `GetData` method that initializes a <xref:System.Data.SqlClient.SqlDataAdapter> component and uses it to fill a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="95fa4-110">Asegúrese de establecer la variable `connectionString` en un valor que sea adecuado para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="95fa4-110">Be sure to set the `connectionString` variable to a value that is appropriate for your database.</span></span> <span data-ttu-id="95fa4-111">Necesitará tener acceso a un servidor que tenga la base de datos de ejemplo AdventureWorks de SQL Server instalada.</span><span class="sxs-lookup"><span data-stu-id="95fa4-111">You will need access to a server with the AdventureWorks SQL Server sample database installed.</span></span>  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1getdata)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1getdata)]  
  
2.  <span data-ttu-id="95fa4-112">En el controlador de eventos <xref:System.Windows.Forms.Form.Load> del formulario, enlace el control <xref:System.Windows.Forms.DataGridView> al componente <xref:System.Windows.Forms.BindingSource> y llame al método `GetData` para recuperar los datos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="95fa4-112">In the <xref:System.Windows.Forms.Form.Load> event handler of your form, bind the <xref:System.Windows.Forms.DataGridView> control to the <xref:System.Windows.Forms.BindingSource> component and call the `GetData` method to retrieve the data from the database.</span></span> <span data-ttu-id="95fa4-113"><xref:System.Data.DataView> se crea a partir de una consulta [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] en <xref:System.Data.DataTable> Contact y luego se enlaza al componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="95fa4-113">The <xref:System.Data.DataView> is created from a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query over the Contact <xref:System.Data.DataTable> and is then bound to the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1formload)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1formload)]  
  
## <a name="see-also"></a><span data-ttu-id="95fa4-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="95fa4-114">See Also</span></span>  
 [<span data-ttu-id="95fa4-115">Enlace de datos y LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="95fa4-115">Data Binding and LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)

---
description: 'Más información acerca de cómo: enlazar un objeto DataView a un control DataGridView Windows Forms'
title: Procedimiento para enlazar un objeto DataView a un control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2b73d60a-6049-446a-85a7-3e5a68b183e2
ms.openlocfilehash: 59bc1a0f6b7b2b0d6da4fa6d88e06922d95c9f46
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723912"
---
# <a name="how-to-bind-a-dataview-object-to-a-windows-forms-datagridview-control"></a><span data-ttu-id="e5d94-103">Procedimiento para enlazar un objeto DataView a un control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e5d94-103">How to: Bind a DataView Object to a Windows Forms DataGridView Control</span></span>

<span data-ttu-id="e5d94-104">El control <xref:System.Windows.Forms.DataGridView> proporciona una forma eficaz y flexible de mostrar datos en formato de tabla.</span><span class="sxs-lookup"><span data-stu-id="e5d94-104">The <xref:System.Windows.Forms.DataGridView> control provides a powerful and flexible way to display data in a tabular format.</span></span> <span data-ttu-id="e5d94-105">El control <xref:System.Windows.Forms.DataGridView> admite el modelo de enlace de datos de Windows Forms estándar, por lo que se enlazará a <xref:System.Data.DataView> y a otros orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="e5d94-105">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it will bind to <xref:System.Data.DataView> and a variety of other data sources.</span></span> <span data-ttu-id="e5d94-106">Sin embargo, en la mayoría de las situaciones se enlazará a un componente <xref:System.Windows.Forms.BindingSource> que administrará los detalles de la interacción con el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e5d94-106">In most situations, however, you will bind to a <xref:System.Windows.Forms.BindingSource> component that will manage the details of interacting with the data source.</span></span>  
  
 <span data-ttu-id="e5d94-107">Para obtener más información sobre el <xref:System.Windows.Forms.DataGridView> control, vea [información general sobre el control DataGridView](/dotnet/desktop/winforms/controls/datagridview-control-overview-windows-forms).</span><span class="sxs-lookup"><span data-stu-id="e5d94-107">For more information about the <xref:System.Windows.Forms.DataGridView> control, see [DataGridView Control Overview](/dotnet/desktop/winforms/controls/datagridview-control-overview-windows-forms).</span></span>  
  
### <a name="to-connect-a-datagridview-control-to-a-dataview"></a><span data-ttu-id="e5d94-108">Para conectar un control DataGridView a DataView</span><span class="sxs-lookup"><span data-stu-id="e5d94-108">To connect a DataGridView control to a DataView</span></span>  
  
1. <span data-ttu-id="e5d94-109">Implemente un método que controle los detalles de recuperación de datos desde una base de datos.</span><span class="sxs-lookup"><span data-stu-id="e5d94-109">Implement a method to handle the details of retrieving data from a database.</span></span> <span data-ttu-id="e5d94-110">En el ejemplo de código siguiente se implementa un método `GetData` que inicializa un componente <xref:System.Data.SqlClient.SqlDataAdapter> y lo utiliza para rellenar un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="e5d94-110">The following code example implements a `GetData` method that initializes a <xref:System.Data.SqlClient.SqlDataAdapter> component and uses it to fill a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="e5d94-111">Asegúrese de establecer la variable `connectionString` en un valor que sea adecuado para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e5d94-111">Be sure to set the `connectionString` variable to a value that is appropriate for your database.</span></span> <span data-ttu-id="e5d94-112">Necesitará tener acceso a un servidor que tenga la base de datos de ejemplo AdventureWorks de SQL Server instalada.</span><span class="sxs-lookup"><span data-stu-id="e5d94-112">You will need access to a server with the AdventureWorks SQL Server sample database installed.</span></span>  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1getdata)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1getdata)]  
  
2. <span data-ttu-id="e5d94-113">En el controlador de eventos <xref:System.Windows.Forms.Form.Load> del formulario, enlace el control <xref:System.Windows.Forms.DataGridView> al componente <xref:System.Windows.Forms.BindingSource> y llame al método `GetData` para recuperar los datos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e5d94-113">In the <xref:System.Windows.Forms.Form.Load> event handler of your form, bind the <xref:System.Windows.Forms.DataGridView> control to the <xref:System.Windows.Forms.BindingSource> component and call the `GetData` method to retrieve the data from the database.</span></span> <span data-ttu-id="e5d94-114"><xref:System.Data.DataView>Se crea a partir de una consulta de LINQ to DataSet sobre el contacto <xref:System.Data.DataTable> y, a continuación, se enlaza al <xref:System.Windows.Forms.BindingSource> componente.</span><span class="sxs-lookup"><span data-stu-id="e5d94-114">The <xref:System.Data.DataView> is created from a LINQ to DataSet query over the Contact <xref:System.Data.DataTable> and is then bound to the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1formload)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1formload)]  
  
## <a name="see-also"></a><span data-ttu-id="e5d94-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5d94-115">See also</span></span>

- [<span data-ttu-id="e5d94-116">Enlace de datos y LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="e5d94-116">Data Binding and LINQ to DataSet</span></span>](data-binding-and-linq-to-dataset.md)

---
title: Enlazar datos al control DataGridView
ms.date: 02/08/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
ms.openlocfilehash: e2762bf363a469abf8c1e57b851d351c1cb41b62
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745074"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a><span data-ttu-id="34e8a-102">Cómo: enlazar datos al control DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="34e8a-102">How to: Bind data to the Windows Forms DataGridView control</span></span>

<span data-ttu-id="34e8a-103">El control <xref:System.Windows.Forms.DataGridView> admite el modelo de enlace de datos Windows Forms estándar, por lo que se puede enlazar a una variedad de orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="34e8a-103">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it can bind to a variety of data sources.</span></span> <span data-ttu-id="34e8a-104">Normalmente, se enlaza a un <xref:System.Windows.Forms.BindingSource> que administra la interacción con el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="34e8a-104">Usually, you bind to a <xref:System.Windows.Forms.BindingSource> that manages the interaction with the data source.</span></span> <span data-ttu-id="34e8a-105">El <xref:System.Windows.Forms.BindingSource> puede ser cualquier origen de datos Windows Forms, lo que proporciona una gran flexibilidad a la hora de elegir o modificar la ubicación de los datos.</span><span class="sxs-lookup"><span data-stu-id="34e8a-105">The <xref:System.Windows.Forms.BindingSource> can be any Windows Forms data source, which gives you great flexibility when choosing or modifying your data's location.</span></span> <span data-ttu-id="34e8a-106">Para obtener más información sobre los orígenes de datos que admite el control <xref:System.Windows.Forms.DataGridView>, vea la [información general sobre el control DataGridView](datagridview-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="34e8a-106">For more information about data sources the <xref:System.Windows.Forms.DataGridView> control supports, see the [DataGridView control overview](datagridview-control-overview-windows-forms.md).</span></span>  

<span data-ttu-id="34e8a-107">Visual Studio ofrece una amplia compatibilidad para el enlace de datos al control DataGridView.</span><span class="sxs-lookup"><span data-stu-id="34e8a-107">Visual Studio has extensive support for data binding to the DataGridView control.</span></span> <span data-ttu-id="34e8a-108">Para obtener más información, vea [Cómo: enlazar datos al control DataGridView Windows Forms mediante el diseñador](bind-data-to-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="34e8a-108">For more information, see [How to: Bind data to the Windows Forms DataGridView control using the Designer](bind-data-to-the-datagrid-using-the-designer.md).</span></span>  

<span data-ttu-id="34e8a-109">Para conectar un control DataGridView a datos:</span><span class="sxs-lookup"><span data-stu-id="34e8a-109">To connect a DataGridView control to data:</span></span>

1. <span data-ttu-id="34e8a-110">Implemente un método para controlar los detalles de la recuperación de los datos.</span><span class="sxs-lookup"><span data-stu-id="34e8a-110">Implement a method to handle the details of retrieving the data.</span></span> <span data-ttu-id="34e8a-111">En el ejemplo de código siguiente se implementa un método `GetData` que inicializa un <xref:System.Data.SqlClient.SqlDataAdapter>y lo utiliza para rellenar una <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="34e8a-111">The following code example implements a `GetData` method that initializes a <xref:System.Data.SqlClient.SqlDataAdapter>, and uses it to populate a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="34e8a-112">A continuación, enlaza el <xref:System.Data.DataTable> al <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="34e8a-112">It then binds the <xref:System.Data.DataTable> to the <xref:System.Windows.Forms.BindingSource>.</span></span> 

2. <span data-ttu-id="34e8a-113">En el controlador de eventos <xref:System.Windows.Forms.Form.Load> del formulario, enlace el control <xref:System.Windows.Forms.DataGridView> al <xref:System.Windows.Forms.BindingSource>y llame al método `GetData` para recuperar los datos.</span><span class="sxs-lookup"><span data-stu-id="34e8a-113">In the form's <xref:System.Windows.Forms.Form.Load> event handler, bind the <xref:System.Windows.Forms.DataGridView> control to the <xref:System.Windows.Forms.BindingSource>, and call the `GetData` method to retrieve the data.</span></span>  

## <a name="example"></a><span data-ttu-id="34e8a-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="34e8a-114">Example</span></span>

<span data-ttu-id="34e8a-115">En este ejemplo de código completo se recuperan datos de una base de datos para rellenar un control DataGridView en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="34e8a-115">This complete code example retrieves data from a database to populate a DataGridView control in a Windows form.</span></span> <span data-ttu-id="34e8a-116">El formulario también tiene botones para volver a cargar los datos y enviar los cambios a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="34e8a-116">The form also has buttons to reload data and submit changes to the database.</span></span>  

<span data-ttu-id="34e8a-117">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="34e8a-117">This example requires:</span></span> 

- <span data-ttu-id="34e8a-118">Acceso a una base de datos de ejemplo Northwind SQL Server.</span><span class="sxs-lookup"><span data-stu-id="34e8a-118">Access to a Northwind SQL Server sample database.</span></span> <span data-ttu-id="34e8a-119">Para obtener más información sobre cómo instalar la base de datos de ejemplo Northwind, vea [obtener las bases de datos de ejemplo para ejemplos de código de ADO.net](../../data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="34e8a-119">For more information about installing the Northwind sample database, see [Get the sample databases for ADO.NET code samples](../../data/adonet/sql/linq/downloading-sample-databases.md).</span></span> 

- <span data-ttu-id="34e8a-120">Referencias a los ensamblados System, System. Windows. Forms, System. Data y System. Xml.</span><span class="sxs-lookup"><span data-stu-id="34e8a-120">References to the System, System.Windows.Forms, System.Data, and System.Xml assemblies.</span></span>  

<span data-ttu-id="34e8a-121">Para compilar y ejecutar este ejemplo, pegue el código en el archivo de código *Form1* en un nuevo proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="34e8a-121">To build and run this example, paste the code into the *Form1* code file in a new Windows Forms project.</span></span> <span data-ttu-id="34e8a-122">Para obtener información sobre cómo compilar desde la C# línea de comandos o Visual Basic, vea compilar desde la línea de [comandos con CSC. exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) o [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="34e8a-122">For information about building from the C# or Visual Basic command line, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>  
  
<span data-ttu-id="34e8a-123">Rellene la variable `connectionString` en el ejemplo con los valores de la conexión de base de datos de ejemplo Northwind SQL Server.</span><span class="sxs-lookup"><span data-stu-id="34e8a-123">Populate the `connectionString` variable in the example with the values for your Northwind SQL Server sample database connection.</span></span> <span data-ttu-id="34e8a-124">La autenticación de Windows, también denominada seguridad integrada, es una forma más segura de conectarse a la base de datos que almacenar una contraseña en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="34e8a-124">Windows Authentication, also called integrated security, is a more secure way to connect to the database than storing a password in the connection string.</span></span> <span data-ttu-id="34e8a-125">Para obtener más información sobre la seguridad de la conexión, consulte [proteger la información de conexión](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="34e8a-125">For more information about connection security, see [Protect connection information](../../data/adonet/protecting-connection-information.md).</span></span>  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="34e8a-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="34e8a-126">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="34e8a-127">Mostrar datos en el control DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="34e8a-127">Display data in the Windows Forms DataGridView control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="34e8a-128">Proteger la información de conexión</span><span class="sxs-lookup"><span data-stu-id="34e8a-128">Protect connection information</span></span>](../../data/adonet/protecting-connection-information.md)

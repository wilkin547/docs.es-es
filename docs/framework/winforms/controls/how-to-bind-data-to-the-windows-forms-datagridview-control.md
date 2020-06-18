---
title: Enlazar datos al control DataGridView
ms.date: 02/08/2019
description: Obtenga información sobre cómo el control DataGridView admite el modelo de enlace de datos de Windows Forms estándar para que se pueda enlazar a una variedad de orígenes de datos.
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
ms.openlocfilehash: 3c3502804d1bc4a5eeffc22b4ec5f2773411ef69
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904421"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a><span data-ttu-id="b0b16-103">Cómo: enlazar datos al control DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b0b16-103">How to: Bind data to the Windows Forms DataGridView control</span></span>

<span data-ttu-id="b0b16-104">El <xref:System.Windows.Forms.DataGridView> control admite el modelo de enlace de datos de Windows Forms estándar, por lo que se puede enlazar a una variedad de orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="b0b16-104">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it can bind to a variety of data sources.</span></span> <span data-ttu-id="b0b16-105">Normalmente, se enlaza a un <xref:System.Windows.Forms.BindingSource> que administra la interacción con el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="b0b16-105">Usually, you bind to a <xref:System.Windows.Forms.BindingSource> that manages the interaction with the data source.</span></span> <span data-ttu-id="b0b16-106"><xref:System.Windows.Forms.BindingSource>Puede ser cualquier origen de datos Windows Forms, lo que proporciona una gran flexibilidad a la hora de elegir o modificar la ubicación de los datos.</span><span class="sxs-lookup"><span data-stu-id="b0b16-106">The <xref:System.Windows.Forms.BindingSource> can be any Windows Forms data source, which gives you great flexibility when choosing or modifying your data's location.</span></span> <span data-ttu-id="b0b16-107">Para obtener más información sobre los orígenes de datos que <xref:System.Windows.Forms.DataGridView> admite el control, vea [información general sobre el control DataGridView](datagridview-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="b0b16-107">For more information about data sources the <xref:System.Windows.Forms.DataGridView> control supports, see the [DataGridView control overview](datagridview-control-overview-windows-forms.md).</span></span>  

<span data-ttu-id="b0b16-108">Visual Studio ofrece una amplia compatibilidad para el enlace de datos al control DataGridView.</span><span class="sxs-lookup"><span data-stu-id="b0b16-108">Visual Studio has extensive support for data binding to the DataGridView control.</span></span> <span data-ttu-id="b0b16-109">Para obtener más información, vea [Cómo: enlazar datos al control DataGridView Windows Forms mediante el diseñador](bind-data-to-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="b0b16-109">For more information, see [How to: Bind data to the Windows Forms DataGridView control using the Designer](bind-data-to-the-datagrid-using-the-designer.md).</span></span>  

<span data-ttu-id="b0b16-110">Para conectar un control DataGridView a datos:</span><span class="sxs-lookup"><span data-stu-id="b0b16-110">To connect a DataGridView control to data:</span></span>

1. <span data-ttu-id="b0b16-111">Implemente un método para controlar los detalles de la recuperación de los datos.</span><span class="sxs-lookup"><span data-stu-id="b0b16-111">Implement a method to handle the details of retrieving the data.</span></span> <span data-ttu-id="b0b16-112">En el ejemplo de código siguiente se implementa un `GetData` método que inicializa un <xref:System.Data.SqlClient.SqlDataAdapter> y lo utiliza para rellenar un <xref:System.Data.DataTable> .</span><span class="sxs-lookup"><span data-stu-id="b0b16-112">The following code example implements a `GetData` method that initializes a <xref:System.Data.SqlClient.SqlDataAdapter>, and uses it to populate a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="b0b16-113">A continuación, enlaza el <xref:System.Data.DataTable> a <xref:System.Windows.Forms.BindingSource> .</span><span class="sxs-lookup"><span data-stu-id="b0b16-113">It then binds the <xref:System.Data.DataTable> to the <xref:System.Windows.Forms.BindingSource>.</span></span>

2. <span data-ttu-id="b0b16-114">En el controlador de <xref:System.Windows.Forms.Form.Load> eventos del formulario, enlace el <xref:System.Windows.Forms.DataGridView> control al <xref:System.Windows.Forms.BindingSource> y llame al `GetData` método para recuperar los datos.</span><span class="sxs-lookup"><span data-stu-id="b0b16-114">In the form's <xref:System.Windows.Forms.Form.Load> event handler, bind the <xref:System.Windows.Forms.DataGridView> control to the <xref:System.Windows.Forms.BindingSource>, and call the `GetData` method to retrieve the data.</span></span>  

## <a name="example"></a><span data-ttu-id="b0b16-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b0b16-115">Example</span></span>

<span data-ttu-id="b0b16-116">En este ejemplo de código completo se recuperan datos de una base de datos para rellenar un control DataGridView en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b0b16-116">This complete code example retrieves data from a database to populate a DataGridView control in a Windows form.</span></span> <span data-ttu-id="b0b16-117">El formulario también tiene botones para volver a cargar los datos y enviar los cambios a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b0b16-117">The form also has buttons to reload data and submit changes to the database.</span></span>  

<span data-ttu-id="b0b16-118">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="b0b16-118">This example requires:</span></span>

- <span data-ttu-id="b0b16-119">Acceso a una base de datos de ejemplo Northwind SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b0b16-119">Access to a Northwind SQL Server sample database.</span></span> <span data-ttu-id="b0b16-120">Para obtener más información sobre cómo instalar la base de datos de ejemplo Northwind, vea [obtener las bases de datos de ejemplo para ejemplos de código de ADO.net](../../data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="b0b16-120">For more information about installing the Northwind sample database, see [Get the sample databases for ADO.NET code samples](../../data/adonet/sql/linq/downloading-sample-databases.md).</span></span>

- <span data-ttu-id="b0b16-121">Referencias a los ensamblados System, System. Windows. Forms, System. Data y System.Xml.</span><span class="sxs-lookup"><span data-stu-id="b0b16-121">References to the System, System.Windows.Forms, System.Data, and System.Xml assemblies.</span></span>  

<span data-ttu-id="b0b16-122">Para compilar y ejecutar este ejemplo, pegue el código en el archivo de código *Form1* en un nuevo proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b0b16-122">To build and run this example, paste the code into the *Form1* code file in a new Windows Forms project.</span></span> <span data-ttu-id="b0b16-123">Para obtener información sobre cómo compilar desde la línea de comandos de C# o Visual Basic, vea [compilar mediante línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) o [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="b0b16-123">For information about building from the C# or Visual Basic command line, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>  
  
<span data-ttu-id="b0b16-124">Rellene la `connectionString` variable en el ejemplo con los valores de la conexión de base de datos de ejemplo Northwind SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b0b16-124">Populate the `connectionString` variable in the example with the values for your Northwind SQL Server sample database connection.</span></span> <span data-ttu-id="b0b16-125">La autenticación de Windows, también denominada seguridad integrada, es una forma más segura de conectarse a la base de datos que almacenar una contraseña en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="b0b16-125">Windows Authentication, also called integrated security, is a more secure way to connect to the database than storing a password in the connection string.</span></span> <span data-ttu-id="b0b16-126">Para obtener más información sobre la seguridad de la conexión, consulte [proteger la información de conexión](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="b0b16-126">For more information about connection security, see [Protect connection information](../../data/adonet/protecting-connection-information.md).</span></span>  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b0b16-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b0b16-127">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="b0b16-128">Mostrar datos en el control DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b0b16-128">Display data in the Windows Forms DataGridView control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="b0b16-129">Proteger la información de conexión</span><span class="sxs-lookup"><span data-stu-id="b0b16-129">Protect connection information</span></span>](../../data/adonet/protecting-connection-information.md)

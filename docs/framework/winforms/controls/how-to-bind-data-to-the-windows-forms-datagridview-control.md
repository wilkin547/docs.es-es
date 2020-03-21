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
ms.openlocfilehash: 643dcd37cd1bb3f8b5938fedff66c67cd68278ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182274"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a><span data-ttu-id="77563-102">Cómo: enlazar datos al control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="77563-102">How to: Bind data to the Windows Forms DataGridView control</span></span>

<span data-ttu-id="77563-103">El <xref:System.Windows.Forms.DataGridView> control admite el modelo de enlace de datos estándar de formularios Windows Forms, por lo que puede enlazar a una variedad de orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="77563-103">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it can bind to a variety of data sources.</span></span> <span data-ttu-id="77563-104">Normalmente, se <xref:System.Windows.Forms.BindingSource> enlaza a un que administra la interacción con el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="77563-104">Usually, you bind to a <xref:System.Windows.Forms.BindingSource> that manages the interaction with the data source.</span></span> <span data-ttu-id="77563-105">Puede <xref:System.Windows.Forms.BindingSource> ser cualquier origen de datos de formularios Windows Forms, lo que le proporciona una gran flexibilidad al elegir o modificar la ubicación de los datos.</span><span class="sxs-lookup"><span data-stu-id="77563-105">The <xref:System.Windows.Forms.BindingSource> can be any Windows Forms data source, which gives you great flexibility when choosing or modifying your data's location.</span></span> <span data-ttu-id="77563-106">Para obtener más información <xref:System.Windows.Forms.DataGridView> acerca de los orígenes de datos que admite el control, vea información general del [control DataGridView](datagridview-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="77563-106">For more information about data sources the <xref:System.Windows.Forms.DataGridView> control supports, see the [DataGridView control overview](datagridview-control-overview-windows-forms.md).</span></span>  

<span data-ttu-id="77563-107">Visual Studio tiene una amplia compatibilidad para el enlace de datos a la DataGridView control.</span><span class="sxs-lookup"><span data-stu-id="77563-107">Visual Studio has extensive support for data binding to the DataGridView control.</span></span> <span data-ttu-id="77563-108">Para obtener más información, vea [Cómo: enlazar datos al control DataGridView](bind-data-to-the-datagrid-using-the-designer.md)de formularios Windows Forms mediante el Diseñador .</span><span class="sxs-lookup"><span data-stu-id="77563-108">For more information, see [How to: Bind data to the Windows Forms DataGridView control using the Designer](bind-data-to-the-datagrid-using-the-designer.md).</span></span>  

<span data-ttu-id="77563-109">Para conectar un control DataGridView a los datos:</span><span class="sxs-lookup"><span data-stu-id="77563-109">To connect a DataGridView control to data:</span></span>

1. <span data-ttu-id="77563-110">Implemente un método para controlar los detalles de la recuperación de los datos.</span><span class="sxs-lookup"><span data-stu-id="77563-110">Implement a method to handle the details of retrieving the data.</span></span> <span data-ttu-id="77563-111">En el ejemplo de `GetData` código siguiente <xref:System.Data.SqlClient.SqlDataAdapter>se implementa un método <xref:System.Data.DataTable>que inicializa un , y lo usa para rellenar un archivo .</span><span class="sxs-lookup"><span data-stu-id="77563-111">The following code example implements a `GetData` method that initializes a <xref:System.Data.SqlClient.SqlDataAdapter>, and uses it to populate a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="77563-112">A continuación, <xref:System.Data.DataTable> se <xref:System.Windows.Forms.BindingSource>une al archivo .</span><span class="sxs-lookup"><span data-stu-id="77563-112">It then binds the <xref:System.Data.DataTable> to the <xref:System.Windows.Forms.BindingSource>.</span></span>

2. <span data-ttu-id="77563-113">En el controlador <xref:System.Windows.Forms.Form.Load> de eventos <xref:System.Windows.Forms.DataGridView> del formulario, enlace el control a la <xref:System.Windows.Forms.BindingSource>, y llame al `GetData` método para recuperar los datos.</span><span class="sxs-lookup"><span data-stu-id="77563-113">In the form's <xref:System.Windows.Forms.Form.Load> event handler, bind the <xref:System.Windows.Forms.DataGridView> control to the <xref:System.Windows.Forms.BindingSource>, and call the `GetData` method to retrieve the data.</span></span>  

## <a name="example"></a><span data-ttu-id="77563-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="77563-114">Example</span></span>

<span data-ttu-id="77563-115">Este ejemplo de código completo recupera datos de una base de datos para rellenar un DataGridView control en un formulario Windows.</span><span class="sxs-lookup"><span data-stu-id="77563-115">This complete code example retrieves data from a database to populate a DataGridView control in a Windows form.</span></span> <span data-ttu-id="77563-116">El formulario también tiene botones para volver a cargar datos y enviar cambios a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="77563-116">The form also has buttons to reload data and submit changes to the database.</span></span>  

<span data-ttu-id="77563-117">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="77563-117">This example requires:</span></span>

- <span data-ttu-id="77563-118">Acceso a una base de datos de ejemplo de Northwind SQL Server.</span><span class="sxs-lookup"><span data-stu-id="77563-118">Access to a Northwind SQL Server sample database.</span></span> <span data-ttu-id="77563-119">Para obtener más información acerca de la instalación de la base de datos de ejemplo Northwind, vea Obtener las bases de datos de [ejemplo para ADO.NET ejemplos](../../data/adonet/sql/linq/downloading-sample-databases.md)de código.</span><span class="sxs-lookup"><span data-stu-id="77563-119">For more information about installing the Northwind sample database, see [Get the sample databases for ADO.NET code samples](../../data/adonet/sql/linq/downloading-sample-databases.md).</span></span>

- <span data-ttu-id="77563-120">Referencias a los ensamblados System, System.Windows.Forms, System.Data y System.Xml.</span><span class="sxs-lookup"><span data-stu-id="77563-120">References to the System, System.Windows.Forms, System.Data, and System.Xml assemblies.</span></span>  

<span data-ttu-id="77563-121">Para compilar y ejecutar este ejemplo, pegue el código en el archivo de código *Form1* en un nuevo proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="77563-121">To build and run this example, paste the code into the *Form1* code file in a new Windows Forms project.</span></span> <span data-ttu-id="77563-122">Para obtener información acerca de la creación desde la línea de comandos de C o Visual Basic, vea Creación de línea de [comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) o Compilación desde la línea de [comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="77563-122">For information about building from the C# or Visual Basic command line, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>  
  
<span data-ttu-id="77563-123">Rellene `connectionString` la variable en el ejemplo con los valores de la conexión de base de datos de ejemplo de Northwind SQL Server .</span><span class="sxs-lookup"><span data-stu-id="77563-123">Populate the `connectionString` variable in the example with the values for your Northwind SQL Server sample database connection.</span></span> <span data-ttu-id="77563-124">La autenticación de Windows, también denominada seguridad integrada, es una forma más segura de conectarse a la base de datos que almacenar una contraseña en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="77563-124">Windows Authentication, also called integrated security, is a more secure way to connect to the database than storing a password in the connection string.</span></span> <span data-ttu-id="77563-125">Para obtener más información acerca de la seguridad de la conexión, consulte [Proteger la información](../../data/adonet/protecting-connection-information.md)de conexión .</span><span class="sxs-lookup"><span data-stu-id="77563-125">For more information about connection security, see [Protect connection information](../../data/adonet/protecting-connection-information.md).</span></span>  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="77563-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="77563-126">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="77563-127">Mostrar datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="77563-127">Display data in the Windows Forms DataGridView control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="77563-128">Proteger la información de conexión</span><span class="sxs-lookup"><span data-stu-id="77563-128">Protect connection information</span></span>](../../data/adonet/protecting-connection-information.md)

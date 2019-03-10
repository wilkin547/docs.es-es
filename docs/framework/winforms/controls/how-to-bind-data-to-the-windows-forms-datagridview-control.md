---
title: Filtrar Enlazar datos al control DataGridView de formularios Windows Forms
ms.date: 02/08/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbcc04625a14ebc23cacfb567951bf8f76f14985
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57725108"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a><span data-ttu-id="1c406-102">Filtrar Enlazar datos al control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1c406-102">How to: Bind data to the Windows Forms DataGridView control</span></span>

<span data-ttu-id="1c406-103">El <xref:System.Windows.Forms.DataGridView> control admite el modelo de enlace de datos de Windows Forms estándar, por lo que se puede enlazar a una variedad de orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="1c406-103">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it can bind to a variety of data sources.</span></span> <span data-ttu-id="1c406-104">Por lo general, enlaza a un <xref:System.Windows.Forms.BindingSource> que administra la interacción con el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="1c406-104">Usually, you bind to a <xref:System.Windows.Forms.BindingSource> that manages the interaction with the data source.</span></span> <span data-ttu-id="1c406-105">El <xref:System.Windows.Forms.BindingSource> puede ser cualquier origen de datos de Windows Forms, que proporciona gran flexibilidad al elegir o modificar la ubicación de sus datos.</span><span class="sxs-lookup"><span data-stu-id="1c406-105">The <xref:System.Windows.Forms.BindingSource> can be any Windows Forms data source, which gives you great flexibility when choosing or modifying your data's location.</span></span> <span data-ttu-id="1c406-106">Para obtener más información acerca de los orígenes de datos la <xref:System.Windows.Forms.DataGridView> control admite, vea la [información general del control DataGridView](datagridview-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="1c406-106">For more information about data sources the <xref:System.Windows.Forms.DataGridView> control supports, see the [DataGridView control overview](datagridview-control-overview-windows-forms.md).</span></span>  

<span data-ttu-id="1c406-107">Visual Studio tiene una amplia compatibilidad para el enlace de datos para el control DataGridView de formularios.</span><span class="sxs-lookup"><span data-stu-id="1c406-107">Visual Studio has extensive support for data binding to the DataGridView control.</span></span> <span data-ttu-id="1c406-108">Para obtener más información, vea [Cómo: Enlazar datos al control DataGridView de formularios Windows Forms mediante el diseñador](bind-data-to-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="1c406-108">For more information, see [How to: Bind data to the Windows Forms DataGridView control using the Designer](bind-data-to-the-datagrid-using-the-designer.md).</span></span>  

<span data-ttu-id="1c406-109">Para conectar un control DataGridView a datos:</span><span class="sxs-lookup"><span data-stu-id="1c406-109">To connect a DataGridView control to data:</span></span>

1. <span data-ttu-id="1c406-110">Implementar un método para controlar los detalles de recuperación de los datos.</span><span class="sxs-lookup"><span data-stu-id="1c406-110">Implement a method to handle the details of retrieving the data.</span></span> <span data-ttu-id="1c406-111">El siguiente ejemplo de código implementa un `GetData` método que inicializa un <xref:System.Data.SqlClient.SqlDataAdapter>y lo usa para rellenar un <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="1c406-111">The following code example implements a `GetData` method that initializes a <xref:System.Data.SqlClient.SqlDataAdapter>, and uses it to populate a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="1c406-112">A continuación, enlaza la <xref:System.Data.DataTable> a la <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="1c406-112">It then binds the <xref:System.Data.DataTable> to the <xref:System.Windows.Forms.BindingSource>.</span></span> 

2. <span data-ttu-id="1c406-113">En el formulario <xref:System.Windows.Forms.Form.Load> controlador de eventos, enlace el <xref:System.Windows.Forms.DataGridView> el control a la <xref:System.Windows.Forms.BindingSource>y llamar a la `GetData` método para recuperar los datos.</span><span class="sxs-lookup"><span data-stu-id="1c406-113">In the form's <xref:System.Windows.Forms.Form.Load> event handler, bind the <xref:System.Windows.Forms.DataGridView> control to the <xref:System.Windows.Forms.BindingSource>, and call the `GetData` method to retrieve the data.</span></span>  

## <a name="example"></a><span data-ttu-id="1c406-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1c406-114">Example</span></span>

<span data-ttu-id="1c406-115">En este ejemplo de código completo se recupera datos de una base de datos para rellenar un control DataGridView en un formulario de Windows.</span><span class="sxs-lookup"><span data-stu-id="1c406-115">This complete code example retrieves data from a database to populate a DataGridView control in a Windows form.</span></span> <span data-ttu-id="1c406-116">El formulario también tiene botones para volver a cargar datos y enviar cambios a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1c406-116">The form also has buttons to reload data and submit changes to the database.</span></span>  

<span data-ttu-id="1c406-117">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="1c406-117">This example requires:</span></span> 

- <span data-ttu-id="1c406-118">Acceso a una base de datos de ejemplo Northwind de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1c406-118">Access to a Northwind SQL Server sample database.</span></span> <span data-ttu-id="1c406-119">Para obtener más información acerca de cómo instalar la base de datos de ejemplo Northwind, vea [obtener las bases de datos de ejemplo para obtener ejemplos de código ADO.NET](../../data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="1c406-119">For more information about installing the Northwind sample database, see [Get the sample databases for ADO.NET code samples](../../data/adonet/sql/linq/downloading-sample-databases.md).</span></span> 

- <span data-ttu-id="1c406-120">Referencias a los ensamblados System, System.Windows.Forms, System.Data y System.Xml.</span><span class="sxs-lookup"><span data-stu-id="1c406-120">References to the System, System.Windows.Forms, System.Data, and System.Xml assemblies.</span></span>  

<span data-ttu-id="1c406-121">Para compilar y ejecutar este ejemplo, pegue el código en el *Form1* archivo de código en un nuevo proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="1c406-121">To build and run this example, paste the code into the *Form1* code file in a new Windows Forms project.</span></span> <span data-ttu-id="1c406-122">Para obtener información sobre la compilación desde el C# o línea de comandos de Visual Basic, vea [de línea de comandos para compilar con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) o [construido a partir de la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="1c406-122">For information about building from the C# or Visual Basic command line, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>  
  
<span data-ttu-id="1c406-123">Rellenar el `connectionString` variable en el ejemplo con los valores para la conexión de base de datos de ejemplo Northwind de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1c406-123">Populate the `connectionString` variable in the example with the values for your Northwind SQL Server sample database connection.</span></span> <span data-ttu-id="1c406-124">Autenticación de Windows, también denominada seguridad integrada, es una forma más segura para conectarse a la base de datos que el almacenamiento de una contraseña en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="1c406-124">Windows Authentication, also called integrated security, is a more secure way to connect to the database than storing a password in the connection string.</span></span> <span data-ttu-id="1c406-125">Para obtener más información acerca de la seguridad de conexión, consulte [proteger la información de conexión](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="1c406-125">For more information about connection security, see [Protect connection information](../../data/adonet/protecting-connection-information.md).</span></span>  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="1c406-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c406-126">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="1c406-127">Mostrar datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1c406-127">Display data in the Windows Forms DataGridView control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="1c406-128">Proteger la información de conexión</span><span class="sxs-lookup"><span data-stu-id="1c406-128">Protect connection information</span></span>](../../data/adonet/protecting-connection-information.md)

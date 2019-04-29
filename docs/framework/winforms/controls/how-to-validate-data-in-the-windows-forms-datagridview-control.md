---
title: Procedimiento para validar datos en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], validation
- DataGridView control [Windows Forms], data validation
- data grids [Windows Forms], validating data
- data validation [Windows Forms], Windows Forms
ms.assetid: d10aef35-701e-4a3c-a684-2a2ed1aeaca6
ms.openlocfilehash: dae254c14790841b37162fca9f998be429006125
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785741"
---
# <a name="how-to-validate-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="07800-102">Procedimiento para validar datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="07800-102">How to: Validate Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="07800-103">El ejemplo de código siguiente muestra cómo validar datos introducidos por un usuario en un control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="07800-103">The following code example demonstrates how to validate data entered by a user into a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="07800-104">En este ejemplo, <xref:System.Windows.Forms.DataGridView> se rellena con filas de la tabla `Customers` de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="07800-104">In this example, the <xref:System.Windows.Forms.DataGridView> is populated with rows from the `Customers` table of the Northwind sample database.</span></span> <span data-ttu-id="07800-105">Cuando el usuario edita una celda en la columna `CompanyName`, se comprueba la validez de su valor verificando que no está vacío.</span><span class="sxs-lookup"><span data-stu-id="07800-105">When the user edits a cell in the `CompanyName` column, its value is tested for validity by checking that it is not empty.</span></span> <span data-ttu-id="07800-106">Si el controlador de eventos del evento <xref:System.Windows.Forms.DataGridView.CellValidating> detecta que el valor es una cadena vacía, <xref:System.Windows.Forms.DataGridView> impide que el usuario salga de la celda hasta que se especifique una cadena que no esté vacía.</span><span class="sxs-lookup"><span data-stu-id="07800-106">If the event handler for the <xref:System.Windows.Forms.DataGridView.CellValidating> event finds that the value is an empty string, the <xref:System.Windows.Forms.DataGridView> prevents the user from exiting the cell until a non-empty string is entered.</span></span>  
  
 <span data-ttu-id="07800-107">Para obtener una explicación completa de este ejemplo de código, vea [Tutorial: Validar datos en el Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="07800-107">For a complete explanation of this code example, see [Walkthrough: Validating Data in the Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="07800-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="07800-108">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewDataValidation#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="07800-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="07800-109">Compiling the Code</span></span>  
 <span data-ttu-id="07800-110">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="07800-110">This example requires:</span></span>  
  
- <span data-ttu-id="07800-111">Referencias a los ensamblados System, System.Data, System.Windows.Forms y System.XML.</span><span class="sxs-lookup"><span data-stu-id="07800-111">References to the System, System.Data, System.Windows.Forms and System.XML assemblies.</span></span>  
  
 <span data-ttu-id="07800-112">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="07800-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="07800-113">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="07800-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="07800-114">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="07800-114">.NET Framework Security</span></span>  
 <span data-ttu-id="07800-115">Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="07800-115">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="07800-116">El uso de la autenticación de Windows (también conocida como seguridad integrada) es un modo más seguro de controlar el acceso a una base de datos.</span><span class="sxs-lookup"><span data-stu-id="07800-116">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="07800-117">Para más información, consulte [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="07800-117">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07800-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="07800-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="07800-119">Tutorial: Validar datos en el Control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="07800-119">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="07800-120">Entrada de datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="07800-120">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="07800-121">Tutorial: Controlar los errores que se producen durante la entrada de datos en el Control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="07800-121">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [<span data-ttu-id="07800-122">Proteger la información de conexión</span><span class="sxs-lookup"><span data-stu-id="07800-122">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)

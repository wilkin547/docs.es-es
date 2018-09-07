---
title: 'Cómo: Controlar los errores que se producen durante la entrada de datos en el control DataGridView de formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
ms.assetid: 9004e72f-fdec-4264-a37d-2c99764efc13
ms.openlocfilehash: 17aff7073af336c0f32effc663eae5f11c194df2
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44067505"
---
# <a name="how-to-handle-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="09099-102">Cómo: Controlar los errores que se producen durante la entrada de datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="09099-102">How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="09099-103">En el ejemplo de código siguiente, se muestra cómo utilizar el control <xref:System.Windows.Forms.DataGridView> para informar de errores de entrada de datos al usuario.</span><span class="sxs-lookup"><span data-stu-id="09099-103">The following code example demonstrates how to use the <xref:System.Windows.Forms.DataGridView> control to report data entry errors to the user.</span></span>  
  
 <span data-ttu-id="09099-104">Para obtener una explicación completa de este ejemplo de código, vea [Tutorial: controlar errores que se producen durante la entrada de datos en el DataGridView Control de Windows Forms](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="09099-104">For a complete explanation of this code example, see [Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="09099-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="09099-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView.DataError#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView.DataError#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="09099-106">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="09099-106">Compiling the Code</span></span>  
 <span data-ttu-id="09099-107">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="09099-107">This example requires:</span></span>  
  
-   <span data-ttu-id="09099-108">Referencias a los ensamblados System, System.Data, System.Windows.Forms y System.XML.</span><span class="sxs-lookup"><span data-stu-id="09099-108">References to the System, System.Data, System.Windows.Forms, and System.XML assemblies.</span></span>  
  
 <span data-ttu-id="09099-109">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="09099-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="09099-110">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="09099-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="09099-111">Vea también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="09099-111">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="09099-112">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="09099-112">.NET Framework Security</span></span>  
 <span data-ttu-id="09099-113">Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="09099-113">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="09099-114">El uso de la autenticación de Windows (también conocida como seguridad integrada) es un modo más seguro de controlar el acceso a una base de datos.</span><span class="sxs-lookup"><span data-stu-id="09099-114">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="09099-115">Para más información, consulte [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="09099-115">For more information, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09099-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="09099-116">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="09099-117">Tutorial: Controlar los errores que se producen durante la entrada de datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="09099-117">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md)  
 [<span data-ttu-id="09099-118">Entrada de datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="09099-118">Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="09099-119">Tutorial: Validar datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="09099-119">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="09099-120">Proteger la información de conexión</span><span class="sxs-lookup"><span data-stu-id="09099-120">Protecting Connection Information</span></span>](../../../../docs/framework/data/adonet/protecting-connection-information.md)

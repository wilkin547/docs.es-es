---
title: 'Cómo: Implementar el modo virtual con la carga de datos Just-In-Time en el control DataGridView de formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], just-in-time data loading
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- just-in-time data loading
- DataGridView control [Windows Forms], large data sets
- virtual mode [Windows Forms], just-in-time data loading
ms.assetid: 33825f92-7a22-40ee-86d9-9a2ed1ead7b7
ms.openlocfilehash: c5b218786d2b52037ec9009ac9fd68c089b1bb47
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44081153"
---
# <a name="how-to-implement-virtual-mode-with-just-in-time-data-loading-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="e03ee-102">Cómo: Implementar el modo virtual con la carga de datos Just-In-Time en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e03ee-102">How to: Implement Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="e03ee-103">En el ejemplo de código siguiente, se muestra cómo utilizar el modo virtual en el control <xref:System.Windows.Forms.DataGridView> con una caché de datos que carga datos de un servidor sólo cuando es necesario.</span><span class="sxs-lookup"><span data-stu-id="e03ee-103">The following code example shows how to use virtual mode in the <xref:System.Windows.Forms.DataGridView> control with a data cache that loads data from a server only when it is needed.</span></span> <span data-ttu-id="e03ee-104">En este ejemplo se describe en detalle en [implementar el modo Virtual con la carga de datos Just In Time en el DataGridView Control de formularios de Windows](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="e03ee-104">This example is described in detail in [Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e03ee-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e03ee-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e03ee-106">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="e03ee-106">Compiling the Code</span></span>  
 <span data-ttu-id="e03ee-107">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="e03ee-107">This example requires:</span></span>  
  
-   <span data-ttu-id="e03ee-108">Referencias a los ensamblados System, System.Data, System.Xml y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="e03ee-108">References to the System, System.Data, System.Xml, and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="e03ee-109">Acceso a un servidor que tenga la base de datos de ejemplo SQL Server Northwind instalada.</span><span class="sxs-lookup"><span data-stu-id="e03ee-109">Access to a server with the Northwind SQL Server sample database installed.</span></span>  
  
 <span data-ttu-id="e03ee-110">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="e03ee-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="e03ee-111">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="e03ee-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="e03ee-112">Vea también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="e03ee-112">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="e03ee-113">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e03ee-113">.NET Framework Security</span></span>  
 <span data-ttu-id="e03ee-114">Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e03ee-114">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="e03ee-115">El uso de la autenticación de Windows (también conocida como seguridad integrada) es un modo más seguro de controlar el acceso a una base de datos.</span><span class="sxs-lookup"><span data-stu-id="e03ee-115">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="e03ee-116">Para más información, consulte [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="e03ee-116">For more information, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e03ee-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e03ee-117">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 <xref:System.Windows.Forms.DataGridView.CellValueNeeded>  
 [<span data-ttu-id="e03ee-118">Implementar el modo virtual mediante la carga de datos Just-In-Time en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e03ee-118">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 [<span data-ttu-id="e03ee-119">Ajuste del rendimiento del control DataGridView en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e03ee-119">Performance Tuning in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="e03ee-120">Modo virtual del control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e03ee-120">Virtual Mode in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)

---
title: 'Cómo: Desplazarse por un conjunto de datos con el control BindingNavigator de formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- datasets [Windows Forms], moving through
- BindingNavigator control [Windows Forms], moving through datasets
- examples [Windows Forms], BindingNavigator control
ms.assetid: 146d97be-3d97-400e-accb-860bbf47729d
ms.openlocfilehash: 54cb04aefa8111873ca5c31ed94fe641437ae990
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537195"
---
# <a name="how-to-move-through-a-dataset-with-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="b8230-102">Cómo: Desplazarse por un conjunto de datos con el control BindingNavigator de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b8230-102">How to: Move Through a DataSet with the Windows Forms BindingNavigator Control</span></span>
<span data-ttu-id="b8230-103">Al crear aplicaciones controladas por datos, a menudo necesitará mostrar colecciones de datos a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b8230-103">As you build data-driven applications, you will often need to display collections of data to users.</span></span> <span data-ttu-id="b8230-104">El control <xref:System.Windows.Forms.BindingNavigator>, junto con el componente <xref:System.Windows.Forms.BindingSource>, proporciona una solución cómoda y extensible para desplazarse por una colección y mostrar sus elementos secuencialmente.</span><span class="sxs-lookup"><span data-stu-id="b8230-104">The <xref:System.Windows.Forms.BindingNavigator> control, in conjunction with the <xref:System.Windows.Forms.BindingSource> component, provides a convenient and extensible solution for moving through a collection and displaying items sequentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8230-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b8230-105">Example</span></span>  
 <span data-ttu-id="b8230-106">En el ejemplo de código siguiente, se muestra cómo usar el control <xref:System.Windows.Forms.BindingNavigator> para desplazarse por los datos.</span><span class="sxs-lookup"><span data-stu-id="b8230-106">The following code example demonstrates how to use a <xref:System.Windows.Forms.BindingNavigator> control to move through data.</span></span> <span data-ttu-id="b8230-107">El conjunto está contenido en un <xref:System.Data.DataView>, que enlaza a un control <xref:System.Windows.Forms.TextBox> con un componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="b8230-107">The set is contained in a <xref:System.Data.DataView>, which is bound to a <xref:System.Windows.Forms.TextBox> control with a <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8230-108">Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b8230-108">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="b8230-109">El uso de la autenticación de Windows (también conocida como seguridad integrada) es un modo más seguro de controlar el acceso a una base de datos.</span><span class="sxs-lookup"><span data-stu-id="b8230-109">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="b8230-110">Para más información, consulte [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="b8230-110">For more information, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataNavigator#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataNavigator#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b8230-111">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="b8230-111">Compiling the Code</span></span>  
 <span data-ttu-id="b8230-112">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="b8230-112">This example requires:</span></span>  
  
-   <span data-ttu-id="b8230-113">Referencias a los ensamblados System, System.Data, System.Drawing, System.Windows.Forms y System.Xml.</span><span class="sxs-lookup"><span data-stu-id="b8230-113">References to the System, System.Data, System.Drawing, System.Windows.Forms and System.Xml assemblies.</span></span>  
  
 <span data-ttu-id="b8230-114">Para obtener información acerca de cómo compilar este ejemplo desde la línea de comandos de Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Command-Line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="b8230-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="b8230-115">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="b8230-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="b8230-116">Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="b8230-116">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8230-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8230-117">See Also</span></span>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="b8230-118">BindingNavigator (control)</span><span class="sxs-lookup"><span data-stu-id="b8230-118">BindingNavigator Control</span></span>](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)  
 [<span data-ttu-id="b8230-119">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="b8230-119">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [<span data-ttu-id="b8230-120">Cómo: Enlazar un control de Windows Forms a un tipo</span><span class="sxs-lookup"><span data-stu-id="b8230-120">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)

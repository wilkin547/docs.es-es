---
title: 'Cómo: Personalizar la forma de agregar elementos con el control BindingSource de formularios Windows Forms'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], creating new items
- BindingSource component [Windows Forms], customizing item addition with
- examples [Windows Forms], BindingSource component
- BindingSource component [Windows Forms], examples
ms.assetid: 1aae11fc-6fb2-4cb9-b3d0-e0638fe77ef0
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 400562e49b9566769f42f140f56b733954e01a0d
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-customize-item-addition-with-the-windows-forms-bindingsource"></a><span data-ttu-id="a187c-102">Cómo: Personalizar la forma de agregar elementos con el control BindingSource de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a187c-102">How to: Customize Item Addition with the Windows Forms BindingSource</span></span>
<span data-ttu-id="a187c-103">Al usar un componente <xref:System.Windows.Forms.BindingSource> para enlazar un control de Windows Forms a un origen de datos, quizá necesite personalizar la creación de nuevos elementos.</span><span class="sxs-lookup"><span data-stu-id="a187c-103">When you use a <xref:System.Windows.Forms.BindingSource> component to bind a Windows Forms control to a data source, you may find it necessary to customize the creation of new items.</span></span> <span data-ttu-id="a187c-104">Para facilitar este proceso, el componente <xref:System.Windows.Forms.BindingSource> proporciona el evento <xref:System.Windows.Forms.BindingSource.AddingNew> , que normalmente se produce cuando el control enlazado necesita crear un nuevo elemento.</span><span class="sxs-lookup"><span data-stu-id="a187c-104">The <xref:System.Windows.Forms.BindingSource> component makes this straightforward by providing the <xref:System.Windows.Forms.BindingSource.AddingNew> event, which is typically raised when the bound control needs to create a new item.</span></span> <span data-ttu-id="a187c-105">El controlador de eventos puede proporcionar el comportamiento personalizado necesario (por ejemplo, llamar a un método en un servicio Web u obtener un nuevo objeto de un generador de clases).</span><span class="sxs-lookup"><span data-stu-id="a187c-105">Your event handler can provide whatever custom behavior is required (for example, calling a method on a Web service or getting a new object from a class factory).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a187c-106">Cuando se agrega un elemento controlando el evento <xref:System.Windows.Forms.BindingSource.AddingNew> , no se puede cancelar la adición.</span><span class="sxs-lookup"><span data-stu-id="a187c-106">When an item is added by handling the <xref:System.Windows.Forms.BindingSource.AddingNew> event, the addition cannot be canceled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a187c-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a187c-107">Example</span></span>  
 <span data-ttu-id="a187c-108">El ejemplo siguiente muestra cómo enlazar un control <xref:System.Windows.Forms.DataGridView> a un generador de clases mediante un componente <xref:System.Windows.Forms.BindingSource> .</span><span class="sxs-lookup"><span data-stu-id="a187c-108">The following example demonstrates how to bind a <xref:System.Windows.Forms.DataGridView> control to a class factory by using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="a187c-109">Cuando el usuario hace clic en la nueva fila del control <xref:System.Windows.Forms.DataGridView> , se produce el evento <xref:System.Windows.Forms.BindingSource.AddingNew> .</span><span class="sxs-lookup"><span data-stu-id="a187c-109">When the user clicks the <xref:System.Windows.Forms.DataGridView> control's new row, the <xref:System.Windows.Forms.BindingSource.AddingNew> event is raised.</span></span> <span data-ttu-id="a187c-110">El controlador de eventos crea un nuevo objeto `DemoCustomer`, que se asigna a la propiedad <xref:System.ComponentModel.AddingNewEventArgs.NewObject%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a187c-110">The event handler creates a new `DemoCustomer` object, which is assigned to the <xref:System.ComponentModel.AddingNewEventArgs.NewObject%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="a187c-111">Esto hace que el nuevo objeto se agregue `DemoCustomer` a la lista del componente <xref:System.Windows.Forms.BindingSource> y que se muestre en la nueva fila del control <xref:System.Windows.Forms.DataGridView> .</span><span class="sxs-lookup"><span data-stu-id="a187c-111">This causes the new `DemoCustomer` object to be added to the <xref:System.Windows.Forms.BindingSource> component's list and to be displayed in the new row of the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.AddingNew#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.AddingNew#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.AddingNew#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a187c-112">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="a187c-112">Compiling the Code</span></span>  
 <span data-ttu-id="a187c-113">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="a187c-113">This example requires:</span></span>  
  
-   <span data-ttu-id="a187c-114">Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="a187c-114">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="a187c-115">Para obtener información acerca de cómo compilar este ejemplo desde la línea de comandos de visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Command-Line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="a187c-115">For information about building this example from the command line for visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="a187c-116">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="a187c-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="a187c-117">Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="a187c-117">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a187c-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="a187c-118">See Also</span></span>  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="a187c-119">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="a187c-119">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [<span data-ttu-id="a187c-120">Cómo: Enlazar un control de Windows Forms a un tipo</span><span class="sxs-lookup"><span data-stu-id="a187c-120">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)

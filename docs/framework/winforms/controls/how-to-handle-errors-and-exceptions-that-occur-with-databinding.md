---
title: 'Cómo: Controlar errores y excepciones que se producen con el enlace de datos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- error handling [Windows Forms], examples
- data binding [Windows Forms], examples
- examples [Windows Forms], error handling
- error handling [Windows Forms], data binding
- data binding [Windows Forms], error handling
- BindingSource component [Windows Forms], handling errors and exceptions
ms.assetid: eddc5bad-9513-47df-ab28-f02d8dff7892
ms.openlocfilehash: d0bb41da69bf1cb87f052c11d3a7d1f1783320ad
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44080171"
---
# <a name="how-to-handle-errors-and-exceptions-that-occur-with-databinding"></a><span data-ttu-id="74ec8-102">Cómo: Controlar errores y excepciones que se producen con el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="74ec8-102">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>
<span data-ttu-id="74ec8-103">A menudo, las excepciones y los errores se producen en los objetos comerciales subyacentes cuando se enlazan a controles.</span><span class="sxs-lookup"><span data-stu-id="74ec8-103">Oftentimes exceptions and errors occur on the underlying business objects when you bind them to controls.</span></span> <span data-ttu-id="74ec8-104">Puede interceptar estos errores y excepciones y, después, recuperar o pasar la información de error al usuario controlando el evento <xref:System.Windows.Forms.Binding.BindingComplete> para un componente <xref:System.Windows.Forms.Binding>, <xref:System.Windows.Forms.BindingSource> o <xref:System.Windows.Forms.CurrencyManager> determinado.</span><span class="sxs-lookup"><span data-stu-id="74ec8-104">You can intercept these errors and exceptions and then either recover or pass the error information to the user by handling the <xref:System.Windows.Forms.Binding.BindingComplete> event for a particular <xref:System.Windows.Forms.Binding>, <xref:System.Windows.Forms.BindingSource>, or <xref:System.Windows.Forms.CurrencyManager> component.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74ec8-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="74ec8-105">Example</span></span>  
 <span data-ttu-id="74ec8-106">En este ejemplo de código se muestra cómo controlar errores y excepciones que se producen durante una operación de enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="74ec8-106">This code example demonstrates how to handle errors and exceptions that occur during a data-binding operation.</span></span> <span data-ttu-id="74ec8-107">Muestra cómo interceptar los errores controlando el evento <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> de los objetos <xref:System.Windows.Forms.Binding>.</span><span class="sxs-lookup"><span data-stu-id="74ec8-107">It demonstrates how to intercept errors by handling the <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> event of the <xref:System.Windows.Forms.Binding> objects.</span></span> <span data-ttu-id="74ec8-108">Para interceptar errores y excepciones controlando este evento, debe habilitar el formato del enlace.</span><span class="sxs-lookup"><span data-stu-id="74ec8-108">In order to intercept errors and exceptions by handling this event, you must enable formatting for the binding.</span></span> <span data-ttu-id="74ec8-109">Puede habilitar el formato al crear el enlace o al agregarlo a la colección de enlaces, o estableciendo la propiedad <xref:System.Windows.Forms.Binding.FormattingEnabled%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="74ec8-109">You can enable formatting when the binding is constructed or added to the binding collection, or by setting the <xref:System.Windows.Forms.Binding.FormattingEnabled%2A> property to `true`.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnectorBindingComplete#3](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CPP/form1.cpp#3)]
 [!code-csharp[System.Windows.Forms.DataConnectorBindingComplete#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CS/form1.cs#3)]
 [!code-vb[System.Windows.Forms.DataConnectorBindingComplete#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/VB/form1.vb#3)]  
  
 <span data-ttu-id="74ec8-110">Cuando se ejecuta el código y se especifica una cadena vacía como nombre de elemento o un valor inferior a 100 como número de elemento, aparece un cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="74ec8-110">When the code is running and an empty string is entered for the part name or a value less than 100 is entered for the part number, a message box appears.</span></span> <span data-ttu-id="74ec8-111">Este es el resultado de controlar el evento <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> para estos enlaces de cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="74ec8-111">This is a result of handling the <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> event for these textbox bindings.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="74ec8-112">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="74ec8-112">Compiling the Code</span></span>  
 <span data-ttu-id="74ec8-113">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="74ec8-113">This example requires:</span></span>  
  
-   <span data-ttu-id="74ec8-114">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="74ec8-114">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="74ec8-115">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="74ec8-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="74ec8-116">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="74ec8-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="74ec8-117">Vea también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="74ec8-117">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74ec8-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="74ec8-118">See Also</span></span>  
 <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.BindingSource.BindingComplete?displayProperty=nameWithType>  
 [<span data-ttu-id="74ec8-119">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="74ec8-119">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)

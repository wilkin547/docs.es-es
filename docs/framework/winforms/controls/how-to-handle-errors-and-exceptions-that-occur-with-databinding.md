---
title: Procedimiento para controlar errores y excepciones que se producen con el enlace de datos
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
ms.openlocfilehash: 709db2a98074e3322adad8b1275b3c4418c14636
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941276"
---
# <a name="how-to-handle-errors-and-exceptions-that-occur-with-databinding"></a><span data-ttu-id="f8587-102">Procedimiento para controlar errores y excepciones que se producen con el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="f8587-102">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>
<span data-ttu-id="f8587-103">A menudo, las excepciones y los errores se producen en los objetos comerciales subyacentes cuando se enlazan a controles.</span><span class="sxs-lookup"><span data-stu-id="f8587-103">Oftentimes exceptions and errors occur on the underlying business objects when you bind them to controls.</span></span> <span data-ttu-id="f8587-104">Puede interceptar estos errores y excepciones y, después, recuperar o pasar la información de error al usuario controlando el evento <xref:System.Windows.Forms.Binding.BindingComplete> para un componente <xref:System.Windows.Forms.Binding>, <xref:System.Windows.Forms.BindingSource> o <xref:System.Windows.Forms.CurrencyManager> determinado.</span><span class="sxs-lookup"><span data-stu-id="f8587-104">You can intercept these errors and exceptions and then either recover or pass the error information to the user by handling the <xref:System.Windows.Forms.Binding.BindingComplete> event for a particular <xref:System.Windows.Forms.Binding>, <xref:System.Windows.Forms.BindingSource>, or <xref:System.Windows.Forms.CurrencyManager> component.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8587-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f8587-105">Example</span></span>  
 <span data-ttu-id="f8587-106">En este ejemplo de código se muestra cómo controlar errores y excepciones que se producen durante una operación de enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="f8587-106">This code example demonstrates how to handle errors and exceptions that occur during a data-binding operation.</span></span> <span data-ttu-id="f8587-107">Muestra cómo interceptar los errores controlando el evento <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> de los objetos <xref:System.Windows.Forms.Binding>.</span><span class="sxs-lookup"><span data-stu-id="f8587-107">It demonstrates how to intercept errors by handling the <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> event of the <xref:System.Windows.Forms.Binding> objects.</span></span> <span data-ttu-id="f8587-108">Para interceptar errores y excepciones controlando este evento, debe habilitar el formato del enlace.</span><span class="sxs-lookup"><span data-stu-id="f8587-108">In order to intercept errors and exceptions by handling this event, you must enable formatting for the binding.</span></span> <span data-ttu-id="f8587-109">Puede habilitar el formato al crear el enlace o al agregarlo a la colección de enlaces, o estableciendo la propiedad <xref:System.Windows.Forms.Binding.FormattingEnabled%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="f8587-109">You can enable formatting when the binding is constructed or added to the binding collection, or by setting the <xref:System.Windows.Forms.Binding.FormattingEnabled%2A> property to `true`.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnectorBindingComplete#3](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CPP/form1.cpp#3)]
 [!code-csharp[System.Windows.Forms.DataConnectorBindingComplete#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CS/form1.cs#3)]
 [!code-vb[System.Windows.Forms.DataConnectorBindingComplete#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/VB/form1.vb#3)]  
  
 <span data-ttu-id="f8587-110">Cuando se ejecuta el código y se especifica una cadena vacía como nombre de elemento o un valor inferior a 100 como número de elemento, aparece un cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="f8587-110">When the code is running and an empty string is entered for the part name or a value less than 100 is entered for the part number, a message box appears.</span></span> <span data-ttu-id="f8587-111">Este es el resultado de controlar el evento <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> para estos enlaces de cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="f8587-111">This is a result of handling the <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> event for these textbox bindings.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f8587-112">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="f8587-112">Compiling the Code</span></span>  
 <span data-ttu-id="f8587-113">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="f8587-113">This example requires:</span></span>  
  
- <span data-ttu-id="f8587-114">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="f8587-114">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="f8587-115">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="f8587-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="f8587-116">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="f8587-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8587-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8587-117">See also</span></span>

- <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource.BindingComplete?displayProperty=nameWithType>
- [<span data-ttu-id="f8587-118">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="f8587-118">BindingSource Component</span></span>](bindingsource-component.md)

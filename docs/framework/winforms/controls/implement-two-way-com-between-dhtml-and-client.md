---
title: 'Cómo: Implementar la comunicación bidireccional entre código DHTML y código de la aplicación cliente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- WebBrowser.ObjectForScripting
- WebBrowser.Document
helpviewer_keywords:
- WebBrowser control [Windows Forms], examples
- communications [Windows Forms], DHTML and client applications
- examples [Windows Forms], WebBrowser control
- WebBrowser control [Windows Forms], communication between DHTML and client application
- DHTML [Windows Forms], embedding in Windows Forms
ms.assetid: 55353a32-b09e-4479-a521-ff3a5ff9a708
ms.openlocfilehash: 10b6bb3f55c8acd62101a48ea53b42e331e4210f
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2018
ms.locfileid: "45647754"
---
# <a name="how-to-implement-two-way-communication-between-dhtml-code-and-client-application-code"></a><span data-ttu-id="fcca9-102">Cómo: Implementar la comunicación bidireccional entre código DHTML y código de la aplicación cliente</span><span class="sxs-lookup"><span data-stu-id="fcca9-102">How to: Implement Two-Way Communication Between DHTML Code and Client Application Code</span></span>
<span data-ttu-id="fcca9-103">Puede usar el control <xref:System.Windows.Forms.WebBrowser> para agregar código de aplicación web de HTML dinámico (DHTML) existente a sus aplicaciones de cliente de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="fcca9-103">You can use the <xref:System.Windows.Forms.WebBrowser> control to add existing dynamic HTML (DHTML) Web application code to your Windows Forms client applications.</span></span> <span data-ttu-id="fcca9-104">Esto es útil cuando se ha invertido un tiempo de desarrollo importante para crear controles basados en DHTML y quiere aprovechar las funciones de la interfaz de usuario enriquecida de Windows Forms sin tener que volver a escribir el código existente.</span><span class="sxs-lookup"><span data-stu-id="fcca9-104">This is useful when you have invested significant development time in creating DHTML-based controls and you want to take advantage of the rich user interface capabilities of Windows Forms without having to rewrite existing code.</span></span>  
  
 <span data-ttu-id="fcca9-105">El control <xref:System.Windows.Forms.WebBrowser> permite implementar la comunicación bidireccional entre el código de la aplicación de cliente y el código de scripting de su página web mediante las propiedades <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> y <xref:System.Windows.Forms.WebBrowser.Document%2A>.</span><span class="sxs-lookup"><span data-stu-id="fcca9-105">The <xref:System.Windows.Forms.WebBrowser> control lets you implement two-way communication between your client application code and your Web page scripting code through the <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> and <xref:System.Windows.Forms.WebBrowser.Document%2A> properties.</span></span> <span data-ttu-id="fcca9-106">Además, puede configurar el control <xref:System.Windows.Forms.WebBrowser> para que los controles web se combinen fácilmente con otros controles del formulario de la aplicación, ocultando su implementación DHTML.</span><span class="sxs-lookup"><span data-stu-id="fcca9-106">Additionally, you can configure the <xref:System.Windows.Forms.WebBrowser> control so that your Web controls blend seamlessly with other controls on your application form, hiding their DHTML implementation.</span></span> <span data-ttu-id="fcca9-107">Para combinar los controles sin problemas, dé formato a la página mostrada para que el color de fondo y el estilo visual coincidan con el resto del formulario, y use las propiedades <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>, <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A>, y <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A> para deshabilitar las características de explorador estándar.</span><span class="sxs-lookup"><span data-stu-id="fcca9-107">To seamlessly blend the controls, format the page displayed so that its background color and visual style match the rest of the form, and use the <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>, <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A>, and <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A> properties to disable standard browser features.</span></span>  
  
### <a name="to-embed-dhtml-in-your-windows-forms-application"></a><span data-ttu-id="fcca9-108">Para incrustar DHTML en la aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fcca9-108">To embed DHTML in your Windows Forms application</span></span>  
  
1.  <span data-ttu-id="fcca9-109">Establezca la propiedad <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> del control <xref:System.Windows.Forms.WebBrowser> en `false` para evitar que el control <xref:System.Windows.Forms.WebBrowser> abra los archivos que se coloquen en él.</span><span class="sxs-lookup"><span data-stu-id="fcca9-109">Set the <xref:System.Windows.Forms.WebBrowser> control's <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> property to `false` to prevent the <xref:System.Windows.Forms.WebBrowser> control from opening files dropped onto it.</span></span>  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#1)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#1)]  
  
2.  <span data-ttu-id="fcca9-110">Establezca la propiedad <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A> del control en `false` para evitar que el control <xref:System.Windows.Forms.WebBrowser> muestre su menú contextual cuando el usuario haga clic en él con el botón secundario.</span><span class="sxs-lookup"><span data-stu-id="fcca9-110">Set the control's <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A> property to `false` to prevent the <xref:System.Windows.Forms.WebBrowser> control from displaying its shortcut menu when the user right-clicks it.</span></span>  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#2)]  
  
3.  <span data-ttu-id="fcca9-111">Establezca la propiedad <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A> del control en `false` para evitar que el control <xref:System.Windows.Forms.WebBrowser> responda a teclas de método abreviado.</span><span class="sxs-lookup"><span data-stu-id="fcca9-111">Set the control's <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A> property to `false` to prevent the <xref:System.Windows.Forms.WebBrowser> control from responding to shortcut keys.</span></span>  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#3)]  
  
4.  <span data-ttu-id="fcca9-112">Establezca la propiedad <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> en el constructor del formulario o en un controlador de eventos <xref:System.Windows.Forms.Form.Load>.</span><span class="sxs-lookup"><span data-stu-id="fcca9-112">Set the <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> property in the form's constructor or a <xref:System.Windows.Forms.Form.Load> event handler.</span></span>  
  
     <span data-ttu-id="fcca9-113">El código siguiente usa la propia clase de formulario para el objeto de scripting.</span><span class="sxs-lookup"><span data-stu-id="fcca9-113">The following code uses the form class itself for the scripting object.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fcca9-114">El modelo de objetos componentes (COM) debe poder tener acceso al objeto de scripting.</span><span class="sxs-lookup"><span data-stu-id="fcca9-114">Component Object Model (COM) must be able to access the scripting object.</span></span> <span data-ttu-id="fcca9-115">Para que el formulario sea visible para COM, agregue el atributo <xref:System.Runtime.InteropServices.ComVisibleAttribute> a la clase de formulario.</span><span class="sxs-lookup"><span data-stu-id="fcca9-115">To make your form visible to COM, add the <xref:System.Runtime.InteropServices.ComVisibleAttribute> attribute to your form class.</span></span>  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#4)]  
  
5.  <span data-ttu-id="fcca9-116">Implemente las propiedades o los métodos públicos en el código de la aplicación que el código de script usará.</span><span class="sxs-lookup"><span data-stu-id="fcca9-116">Implement public properties or methods in your application code that your script code will use.</span></span>  
  
     <span data-ttu-id="fcca9-117">Por ejemplo, si usa la clase de formulario para el objeto de scripting, agregue el código siguiente a la clase de formulario.</span><span class="sxs-lookup"><span data-stu-id="fcca9-117">For example, if you use the form class for the scripting object, add the following code to your form class.</span></span>  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#5)]  
  
6.  <span data-ttu-id="fcca9-118">Use el objeto `window.external` en el código de scripting para acceder a las propiedades y los métodos públicos del objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="fcca9-118">Use the `window.external` object in your scripting code to access public properties and methods of the specified object.</span></span>  
  
     <span data-ttu-id="fcca9-119">El código HTML siguiente muestra cómo llamar a un método en el objeto de scripting desde el evento de clic de un botón.</span><span class="sxs-lookup"><span data-stu-id="fcca9-119">The following HTML code demonstrates how to call a method on the scripting object from a button click.</span></span> <span data-ttu-id="fcca9-120">Copie este código en el elemento BODY de un documento HTML que cargue con el método <xref:System.Windows.Forms.WebBrowser.Navigate%2A> del control o que asigne a la propiedad <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> del control.</span><span class="sxs-lookup"><span data-stu-id="fcca9-120">Copy this code into the BODY element of an HTML document that you load using the control's <xref:System.Windows.Forms.WebBrowser.Navigate%2A> method or that you assign to the control's <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> property.</span></span>  
  
    ```  
    <button onclick="window.external.Test('called from script code')">  
        call client code from script code  
    </button>  
    ```  
  
7.  <span data-ttu-id="fcca9-121">Implemente funciones en el código de script que el código de la aplicación usará.</span><span class="sxs-lookup"><span data-stu-id="fcca9-121">Implement functions in your script code that your application code will use.</span></span>  
  
     <span data-ttu-id="fcca9-122">El elemento HTML SCRIPT siguiente proporciona una función de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fcca9-122">The following HTML SCRIPT element provides an example function.</span></span> <span data-ttu-id="fcca9-123">Copie este código en el elemento HEAD de un documento HTML que cargue con el método <xref:System.Windows.Forms.WebBrowser.Navigate%2A> del control o que asigne a la propiedad <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> del control.</span><span class="sxs-lookup"><span data-stu-id="fcca9-123">Copy this code into the HEAD element of an HTML document that you load using the control's <xref:System.Windows.Forms.WebBrowser.Navigate%2A> method or that you assign to the control's <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> property.</span></span>  
  
    ```  
    <script>  
    function test(message) {   
        alert(message);   
    }  
    </script>  
    ```  
  
8.  <span data-ttu-id="fcca9-124">Use la propiedad <xref:System.Windows.Forms.WebBrowser.Document%2A> para acceder al código de scripting desde el código de la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="fcca9-124">Use the <xref:System.Windows.Forms.WebBrowser.Document%2A> property to access the script code from your client application code.</span></span>  
  
     <span data-ttu-id="fcca9-125">Por ejemplo, agregue el código siguiente al controlador de eventos de un botón <xref:System.Windows.Forms.Control.Click>.</span><span class="sxs-lookup"><span data-stu-id="fcca9-125">For example, add the following code to a button <xref:System.Windows.Forms.Control.Click> event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#8)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#8)]  
  
9. <span data-ttu-id="fcca9-126">Cuando haya terminado la depuración del código DHTML, establezca la propiedad <xref:System.Windows.Forms.WebBrowser.ScriptErrorsSuppressed%2A> del control en `true` para evitar que el control <xref:System.Windows.Forms.WebBrowser> muestre mensajes de error para los problemas del código de script.</span><span class="sxs-lookup"><span data-stu-id="fcca9-126">When you are finished debugging your DHTML, set the control's <xref:System.Windows.Forms.WebBrowser.ScriptErrorsSuppressed%2A> property to `true` to prevent the <xref:System.Windows.Forms.WebBrowser> control from displaying error messages for script code problems.</span></span>  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#9)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="fcca9-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fcca9-127">Example</span></span>  
 <span data-ttu-id="fcca9-128">El siguiente ejemplo de código completo proporciona una aplicación de demostración que puede usar para comprender esta característica.</span><span class="sxs-lookup"><span data-stu-id="fcca9-128">The following complete code example provides a demonstration application that you can use to understand this feature.</span></span> <span data-ttu-id="fcca9-129">El código HTML se carga en el control <xref:System.Windows.Forms.WebBrowser> mediante la propiedad <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> en lugar de cargarse desde un archivo HTML independiente.</span><span class="sxs-lookup"><span data-stu-id="fcca9-129">The HTML code is loaded into the <xref:System.Windows.Forms.WebBrowser> control through the <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> property instead of being loaded from a separate HTML file.</span></span>  
  
 [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#0](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#0](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fcca9-130">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="fcca9-130">Compiling the Code</span></span>  
 <span data-ttu-id="fcca9-131">Este código requiere:</span><span class="sxs-lookup"><span data-stu-id="fcca9-131">This code requires:</span></span>  
  
-   <span data-ttu-id="fcca9-132">Referencias a los ensamblados System y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="fcca9-132">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="fcca9-133">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="fcca9-133">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="fcca9-134">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="fcca9-134">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="fcca9-135">Vea también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="fcca9-135">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcca9-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="fcca9-136">See Also</span></span>  
 <xref:System.Windows.Forms.WebBrowser>  
 <xref:System.Windows.Forms.WebBrowser.Document%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="fcca9-137">WebBrowser (control)</span><span class="sxs-lookup"><span data-stu-id="fcca9-137">WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-windows-forms.md)

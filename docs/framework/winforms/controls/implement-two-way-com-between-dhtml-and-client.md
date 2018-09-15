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
# <a name="how-to-implement-two-way-communication-between-dhtml-code-and-client-application-code"></a>Cómo: Implementar la comunicación bidireccional entre código DHTML y código de la aplicación cliente
Puede usar el control <xref:System.Windows.Forms.WebBrowser> para agregar código de aplicación web de HTML dinámico (DHTML) existente a sus aplicaciones de cliente de Windows Forms. Esto es útil cuando se ha invertido un tiempo de desarrollo importante para crear controles basados en DHTML y quiere aprovechar las funciones de la interfaz de usuario enriquecida de Windows Forms sin tener que volver a escribir el código existente.  
  
 El control <xref:System.Windows.Forms.WebBrowser> permite implementar la comunicación bidireccional entre el código de la aplicación de cliente y el código de scripting de su página web mediante las propiedades <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> y <xref:System.Windows.Forms.WebBrowser.Document%2A>. Además, puede configurar el control <xref:System.Windows.Forms.WebBrowser> para que los controles web se combinen fácilmente con otros controles del formulario de la aplicación, ocultando su implementación DHTML. Para combinar los controles sin problemas, dé formato a la página mostrada para que el color de fondo y el estilo visual coincidan con el resto del formulario, y use las propiedades <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>, <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A>, y <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A> para deshabilitar las características de explorador estándar.  
  
### <a name="to-embed-dhtml-in-your-windows-forms-application"></a>Para incrustar DHTML en la aplicación de Windows Forms  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> del control <xref:System.Windows.Forms.WebBrowser> en `false` para evitar que el control <xref:System.Windows.Forms.WebBrowser> abra los archivos que se coloquen en él.  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#1)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#1)]  
  
2.  Establezca la propiedad <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A> del control en `false` para evitar que el control <xref:System.Windows.Forms.WebBrowser> muestre su menú contextual cuando el usuario haga clic en él con el botón secundario.  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#2)]  
  
3.  Establezca la propiedad <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A> del control en `false` para evitar que el control <xref:System.Windows.Forms.WebBrowser> responda a teclas de método abreviado.  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#3)]  
  
4.  Establezca la propiedad <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> en el constructor del formulario o en un controlador de eventos <xref:System.Windows.Forms.Form.Load>.  
  
     El código siguiente usa la propia clase de formulario para el objeto de scripting.  
  
    > [!NOTE]
    >  El modelo de objetos componentes (COM) debe poder tener acceso al objeto de scripting. Para que el formulario sea visible para COM, agregue el atributo <xref:System.Runtime.InteropServices.ComVisibleAttribute> a la clase de formulario.  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#4)]  
  
5.  Implemente las propiedades o los métodos públicos en el código de la aplicación que el código de script usará.  
  
     Por ejemplo, si usa la clase de formulario para el objeto de scripting, agregue el código siguiente a la clase de formulario.  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#5)]  
  
6.  Use el objeto `window.external` en el código de scripting para acceder a las propiedades y los métodos públicos del objeto especificado.  
  
     El código HTML siguiente muestra cómo llamar a un método en el objeto de scripting desde el evento de clic de un botón. Copie este código en el elemento BODY de un documento HTML que cargue con el método <xref:System.Windows.Forms.WebBrowser.Navigate%2A> del control o que asigne a la propiedad <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> del control.  
  
    ```  
    <button onclick="window.external.Test('called from script code')">  
        call client code from script code  
    </button>  
    ```  
  
7.  Implemente funciones en el código de script que el código de la aplicación usará.  
  
     El elemento HTML SCRIPT siguiente proporciona una función de ejemplo. Copie este código en el elemento HEAD de un documento HTML que cargue con el método <xref:System.Windows.Forms.WebBrowser.Navigate%2A> del control o que asigne a la propiedad <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> del control.  
  
    ```  
    <script>  
    function test(message) {   
        alert(message);   
    }  
    </script>  
    ```  
  
8.  Use la propiedad <xref:System.Windows.Forms.WebBrowser.Document%2A> para acceder al código de scripting desde el código de la aplicación cliente.  
  
     Por ejemplo, agregue el código siguiente al controlador de eventos de un botón <xref:System.Windows.Forms.Control.Click>.  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#8)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#8)]  
  
9. Cuando haya terminado la depuración del código DHTML, establezca la propiedad <xref:System.Windows.Forms.WebBrowser.ScriptErrorsSuppressed%2A> del control en `true` para evitar que el control <xref:System.Windows.Forms.WebBrowser> muestre mensajes de error para los problemas del código de script.  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#9)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#9)]  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo de código completo proporciona una aplicación de demostración que puede usar para comprender esta característica. El código HTML se carga en el control <xref:System.Windows.Forms.WebBrowser> mediante la propiedad <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> en lugar de cargarse desde un archivo HTML independiente.  
  
 [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#0](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#0](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#0)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Este código requiere:  
  
-   Referencias a los ensamblados System y System.Windows.Forms.  
  
 Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.  Vea también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.WebBrowser>  
 <xref:System.Windows.Forms.WebBrowser.Document%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A?displayProperty=nameWithType>  
 [WebBrowser (control)](../../../../docs/framework/winforms/controls/webbrowser-control-windows-forms.md)

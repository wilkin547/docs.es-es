---
title: Procedimiento Realizar llamadas seguras para subprocesos a controles de formularios Windows Forms
ms.date: 02/19/2019
dev_langs:
- csharp
- vb
f1_keywords:
- EHInvalidOperation.WinForms.IllegalCrossThreadCall
helpviewer_keywords:
- thread safety [Windows Forms], calling controls [Windows Forms]
- calling controls [Windows Forms], thread safety [Windows Forms]
- CheckForIllegalCrossThreadCalls property [Windows Forms]
- Windows Forms controls [Windows Forms], multithreading
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], cross-thread calls
- controls [Windows Forms], multithreading
ms.assetid: 138f38b6-1099-4fd5-910c-390b41cbad35
ms.openlocfilehash: ef7836721df6c090a4d09c38c176641331c3e8a4
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362570"
---
# <a name="how-to-make-thread-safe-calls-to-windows-forms-controls"></a>Procedimiento Realizar llamadas seguras para subprocesos a controles de formularios Windows Forms

El multithreading puede mejorar el rendimiento de las aplicaciones de Windows Forms, pero el acceso a los controles de Windows Forms no es intrínsecamente seguro para subprocesos. El multithreading puede exponer el código de errores muy graves y complejos. Dos o más subprocesos para manipular un control pueden forzar el control a un estado incoherente y conducir a condiciones de carrera, interbloqueos y se inmoviliza o se bloquea. Si implementa multithreading en la aplicación, asegúrese de llamar a los controles entre subprocesos de forma segura para subprocesos. Para obtener más información, consulte [Managed threading best practices](../../../../docs/standard/threading/managed-threading-best-practices.md). 

Hay dos maneras de llamar con seguridad a un control de Windows Forms desde un subproceso que no ha creado ese control. Puede usar el <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> método para llamar a un delegado que se crea en el subproceso principal, que a su vez llama al control. O bien, puede implementar un <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>, que utiliza un modelo orientado a eventos para separar el trabajo realizado en el subproceso en segundo plano de los informes en los resultados. 

## <a name="unsafe-cross-thread-calls"></a>Llamadas entre subprocesos no seguras

No es seguro llamar a un control directamente desde un subproceso que no crearla. El fragmento de código siguiente muestra una llamada no segura para el <xref:System.Windows.Forms.TextBox?displayProperty=nameWithType> control. El `Button1_Click` crea un nuevo controlador de eventos `WriteTextUnsafe` subproceso, que establece el subproceso principal <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> propiedad directamente. 

```csharp
private void Button1_Click(object sender, EventArgs e)
{
    thread2 = new Thread(new ThreadStart(WriteTextUnsafe));
    thread2.Start();
}
private void WriteTextUnsafe()
{
    textBox1.Text = "This text was set unsafely.";
}
```

```vb
Private Sub Button1_Click(ByVal sender As Object, e As EventArgs) Handles Button1.Click
    Thread2 = New Thread(New ThreadStart(AddressOf WriteTextUnsafe))
    Thread2.Start()
End Sub

Private Sub WriteTextUnsafe()
    TextBox1.Text = "This text was set unsafely."
End Sub
```

El depurador de Visual Studio detecta estas llamadas no seguras de subproceso generando una <xref:System.InvalidOperationException> con el mensaje, **operación entre subprocesos no es válida. Control "" acceso desde un subproceso distinto del subproceso que lo creó.** El <xref:System.InvalidOperationException> siempre se produce para las llamadas entre subprocesos no seguras durante la depuración de Visual Studio y puede producirse en tiempo de ejecución de aplicación. Debe corregir el problema, pero se puede deshabilitar la excepción estableciendo la <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A?displayProperty=nameWithType> propiedad `false`.

## <a name="safe-cross-thread-calls"></a>Llamadas entre subprocesos seguras 

Los ejemplos de código siguiente muestran dos maneras de llamar con seguridad a un control de Windows Forms desde un subproceso que no crearla: 
1. El <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> método, que llama a un delegado desde el subproceso principal para el control de llamadas. 
2. Un <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> componente, que ofrece un modelo orientado a eventos. 

En ambos ejemplos, el subproceso de fondo se suspende durante un segundo simular el trabajo que se realiza en ese subproceso. 

Puede compilar y ejecutar estos ejemplos como aplicaciones de .NET Framework desde el C# o línea de comandos de Visual Basic. Para obtener más información, consulte [de línea de comandos para compilar con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) o [construido a partir de la línea de comandos (Visual Basic)](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md). 

A partir de .NET Core 3.0, también puede compilar y ejecutar los ejemplos como aplicaciones de .NET Core de Windows desde una carpeta que tenga un núcleo de .NET Windows Forms  *\<nombre de carpeta > .csproj* archivo de proyecto. 

## <a name="example-use-the-invoke-method-with-a-delegate"></a>Ejemplo: Utilice el método de invocación con un delegado

El ejemplo siguiente muestra un patrón para garantizar las llamadas de subprocesos a un control de Windows Forms. Consulta el <xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName> propiedad, que se compara el control de la creación de Id. de subproceso para el identificador del subproceso que realiza la llamada. Si los identificadores de subproceso son iguales, llama directamente al control. Si los identificadores de subproceso son diferentes, llama a la <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=nameWithType> método con un delegado a partir del subproceso principal, que realiza la llamada real al control.

El `SafeCallDelegate` habilita la configuración de la <xref:System.Windows.Forms.TextBox> del control <xref:System.Windows.Forms.TextBox.Text%2A> propiedad. El `WriteTextSafe` consultas de método <xref:System.Windows.Forms.Control.InvokeRequired%2A>. Si <xref:System.Windows.Forms.Control.InvokeRequired%2A> devuelve `true`, `WriteTextSafe` pasa el `SafeCallDelegate` a la <xref:System.Windows.Forms.Control.Invoke%2A> método para realizar la llamada real al control. Si <xref:System.Windows.Forms.Control.InvokeRequired%2A> devuelve `false`, `WriteTextSafe` establece el <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> directamente. El `Button1_Click` controlador de eventos crea el nuevo subproceso y ejecuta el `WriteTextSafe` método. 

 [!code-csharp[ThreadSafeCalls#1](../../../../samples/snippets/winforms/thread-safe/example1/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#1](../../../../samples/snippets/winforms/thread-safe/example1/vb/Form1.vb)]  

## <a name="example-use-a-backgroundworker-event-handler"></a>Ejemplo: Usar un controlador de eventos de BackgroundWorker

Una manera fácil es implementar el multithreading con el <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> componente, que utiliza un modelo orientado a eventos. El subproceso en segundo plano se ejecuta el <xref:System.ComponentModel.BackgroundWorker.DoWork?displayProperty=nameWithType> evento, que no interactúa con el subproceso principal. El subproceso principal se ejecuta el <xref:System.ComponentModel.BackgroundWorker.ProgressChanged?displayProperty=nameWithType> y <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted?displayProperty=nameWithType> controladores de eventos, que pueden llamar a los controles del subproceso principal.

Realizar una llamada segura para subprocesos mediante <xref:System.ComponentModel.BackgroundWorker>, cree un método en el subproceso en segundo plano para realizar el trabajo y enlazarlo a la <xref:System.ComponentModel.BackgroundWorker.DoWork> eventos. Cree otro método en el subproceso principal para notificar los resultados del trabajo en segundo plano y enlazarlo a la <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> o <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> eventos. Para iniciar el subproceso en segundo plano, llame a <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A?displayProperty=nameWithType>. 

El ejemplo se usa el <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> controlador de eventos para establecer el <xref:System.Windows.Forms.TextBox> del control <xref:System.Windows.Forms.TextBox.Text%2A> propiedad. Para obtener un ejemplo que usa el <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> eventos, consulte <xref:System.ComponentModel.BackgroundWorker>. 

 [!code-csharp[ThreadSafeCalls#2](../../../../samples/snippets/winforms/thread-safe/example2/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#2](../../../../samples/snippets/winforms/thread-safe/example2/vb/Form1.vb)]  

## <a name="see-also"></a>Vea también

- <xref:System.ComponentModel.BackgroundWorker>
- [Cómo: Ejecutar una operación en segundo plano](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)
- [Cómo: Implementar un formulario que utiliza una operación en segundo plano](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)
- [Desarrollar controles personalizados de Windows Forms con .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)

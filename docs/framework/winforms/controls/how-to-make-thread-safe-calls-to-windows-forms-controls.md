---
title: Realizar llamadas seguras para subprocesos a los controles
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
ms.openlocfilehash: 365b1acb693b9ff2be603a3e659ed8d846a7696a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142009"
---
# <a name="how-to-make-thread-safe-calls-to-windows-forms-controls"></a>Cómo: Realizar llamadas seguras para subprocesos a controles de formularios Windows Forms

Multithreading puede mejorar el rendimiento de las aplicaciones de Windows Forms, pero el acceso a los controles de formularios Windows Forms no es inherentemente seguro para subprocesos. Multithreading puede exponer el código a errores muy graves y complejos. Dos o más subprocesos que manipulan un control pueden forzar el control en un estado incoherente y conducir a condiciones de carrera, interbloqueos y bloqueos o bloqueos. Si implementa multithreading en la aplicación, asegúrese de llamar a controles entre subprocesos de una manera segura para subprocesos. Para obtener más información, consulte [Procedimientos recomendados de subprocesos administrados.](../../../standard/threading/managed-threading-best-practices.md)

Hay dos maneras de llamar de forma segura a un control de formularios Windows Forms desde un subproceso que no creó ese control. Puede usar <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> el método para llamar a un delegado creado en el subproceso principal, que a su vez llama al control. O bien, puede <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>implementar un , que usa un modelo controlado por eventos para separar el trabajo realizado en el subproceso en segundo plano de los informes sobre los resultados.

## <a name="unsafe-cross-thread-calls"></a>Llamadas entre hilos no seguras

No es seguro llamar a un control directamente desde un subproceso que no lo creó. En el siguiente fragmento de código <xref:System.Windows.Forms.TextBox?displayProperty=nameWithType> se muestra una llamada no segura al control. El `Button1_Click` controlador de `WriteTextUnsafe` eventos crea un nuevo subproceso, que establece la propiedad del <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> subproceso principal directamente.

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

El depurador de Visual Studio detecta estas <xref:System.InvalidOperationException> llamadas de subprocesos no seguros generando un mensaje, **operación entre subprocesos no válida. Control "" al que se tuvo acceso desde un subproceso distinto del subproceso en el que se creó.** Siempre <xref:System.InvalidOperationException> se produce para las llamadas entre subprocesos no seguras durante la depuración de Visual Studio y puede producirse en tiempo de ejecución de la aplicación. Debe corregir el problema, pero puede deshabilitar <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A?displayProperty=nameWithType> la `false`excepción estableciendo la propiedad en .

## <a name="safe-cross-thread-calls"></a>Llamadas seguras entre subprocesos

En los ejemplos de código siguientes se muestran dos formas de llamar de forma segura a un control de formularios Windows Forms desde un subproceso que no lo creó:

1. El <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> método, que llama a un delegado desde el subproceso principal para llamar al control.
2. Un <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> componente, que ofrece un modelo controlado por eventos.

En ambos ejemplos, el subproceso en segundo plano duerme durante un segundo para simular el trabajo que se realiza en ese subproceso.

Puede compilar y ejecutar estos ejemplos como aplicaciones de .NET Framework desde la línea de comandos de Visual Basic o de C. Para obtener más información, vea Creación de línea de [comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) o Compilación desde la línea de [comandos (Visual Basic).](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)

A partir de .NET Core 3.0, también puede compilar y ejecutar los ejemplos como aplicaciones de Windows .NET Core desde una carpeta que tiene un nombre de * \<carpeta* de formularios Windows Forms de .NET Core> archivo de proyecto.csproj.

## <a name="example-use-the-invoke-method-with-a-delegate"></a>Ejemplo: Utilice el método Invoke con un delegado

En el ejemplo siguiente se muestra un patrón para garantizar llamadas seguras para subprocesos a un control de formularios Windows Forms. Consulta la <xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName> propiedad, que compara el identificador de subproceso de creación del control con el identificador de subproceso que realiza la llamada. Si los iDE de subproceso son los mismos, llama al control directamente. Si los iDE de subproceso son <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=nameWithType> diferentes, llama al método con un delegado desde el subproceso principal, que realiza la llamada real al control.

El `SafeCallDelegate` permite <xref:System.Windows.Forms.TextBox> establecer la <xref:System.Windows.Forms.TextBox.Text%2A> propiedad del control. El `WriteTextSafe` método <xref:System.Windows.Forms.Control.InvokeRequired%2A>consulta . Si <xref:System.Windows.Forms.Control.InvokeRequired%2A> `true`devuelve `WriteTextSafe` , `SafeCallDelegate` pasa <xref:System.Windows.Forms.Control.Invoke%2A> el método para realizar la llamada real al control. Si <xref:System.Windows.Forms.Control.InvokeRequired%2A> `false`devuelve `WriteTextSafe` , <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> establece directamente. El `Button1_Click` controlador de eventos crea `WriteTextSafe` el nuevo subproceso y ejecuta el método.

 [!code-csharp[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/vb/Form1.vb)]  

## <a name="example-use-a-backgroundworker-event-handler"></a>Ejemplo: Use un controlador de eventos BackgroundWorker

Una manera fácil de implementar multithreading es con el <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> componente, que utiliza un modelo controlado por eventos. El subproceso en <xref:System.ComponentModel.BackgroundWorker.DoWork?displayProperty=nameWithType> segundo plano ejecuta el evento, que no interactúa con el subproceso principal. El subproceso principal <xref:System.ComponentModel.BackgroundWorker.ProgressChanged?displayProperty=nameWithType> <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted?displayProperty=nameWithType> ejecuta los controladores de eventos y, que pueden llamar a los controles del subproceso principal.

Para realizar una llamada segura <xref:System.ComponentModel.BackgroundWorker>para subprocesos mediante , cree un método en <xref:System.ComponentModel.BackgroundWorker.DoWork> el subproceso en segundo plano para realizar el trabajo y enlazarlo al evento. Cree otro método en el subproceso principal para informar de los <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> resultados del trabajo en segundo plano y enlazarlo al evento o. Para iniciar el subproceso <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A?displayProperty=nameWithType>en segundo plano, llame a .

En el <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> ejemplo se usa <xref:System.Windows.Forms.TextBox> el <xref:System.Windows.Forms.TextBox.Text%2A> controlador de eventos para establecer la propiedad del control. Para ver un <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> ejemplo <xref:System.ComponentModel.BackgroundWorker>con el evento, consulte .

 [!code-csharp[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/vb/Form1.vb)]  

## <a name="see-also"></a>Consulte también

- <xref:System.ComponentModel.BackgroundWorker>
- [Cómo: Ejecutar una operación en segundo plano](how-to-run-an-operation-in-the-background.md)
- [Cómo: Implementar un formulario que utilice una operación en segundo plano](how-to-implement-a-form-that-uses-a-background-operation.md)
- [Desarrollar controles personalizados de Formularios Windows Forms con .NET Framework](developing-custom-windows-forms-controls.md)

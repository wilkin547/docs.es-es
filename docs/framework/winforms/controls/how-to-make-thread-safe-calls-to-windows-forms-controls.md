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
ms.openlocfilehash: 101457ab2a02b8de49d06c354ca307e07b690ba2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736164"
---
# <a name="how-to-make-thread-safe-calls-to-windows-forms-controls"></a>Cómo: realizar llamadas seguras para subprocesos a controles Windows Forms

El multithreading puede mejorar el rendimiento de las aplicaciones Windows Forms, pero el acceso a los controles Windows Forms no es seguro para subprocesos de forma inherente. El multithreading puede exponer el código a errores muy graves y complejos. Dos o más subprocesos que manipulan un control pueden forzar el control en un estado incoherente y conducir a condiciones de carrera, interbloqueos e inmovilizaciones o bloqueos. Si implementa multithreading en la aplicación, asegúrese de llamar a los controles entre subprocesos de una manera segura para subprocesos. Para obtener más información, vea [procedimientos recomendados para el subprocesamiento administrado](../../../standard/threading/managed-threading-best-practices.md). 

Hay dos maneras de llamar a un control de Windows Forms de forma segura desde un subproceso que no creó ese control. Puede usar el método <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> para llamar a un delegado creado en el subproceso principal, que a su vez llama al control. O bien, puede implementar un <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>, que utiliza un modelo orientado a eventos para separar el trabajo realizado en el subproceso en segundo plano de los informes sobre los resultados. 

## <a name="unsafe-cross-thread-calls"></a>Llamadas no seguras entre subprocesos

No es seguro llamar a un control directamente desde un subproceso que no lo creó. En el fragmento de código siguiente se muestra una llamada no segura al control <xref:System.Windows.Forms.TextBox?displayProperty=nameWithType>. El controlador de eventos `Button1_Click` crea un nuevo subproceso `WriteTextUnsafe`, que establece directamente la propiedad <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> del subproceso principal. 

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

El depurador de Visual Studio detecta estas llamadas de subprocesos no seguras mediante la generación de una <xref:System.InvalidOperationException> con el mensaje, la **operación entre subprocesos no es válida. Control "" al que se tiene acceso desde un subproceso distinto del subproceso en el que se creó.** El <xref:System.InvalidOperationException> siempre se produce para llamadas no seguras entre subprocesos durante la depuración de Visual Studio y puede producirse en el tiempo de ejecución de la aplicación. Debe corregir el problema, pero puede deshabilitar la excepción estableciendo la propiedad <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A?displayProperty=nameWithType> en `false`.

## <a name="safe-cross-thread-calls"></a>Llamadas seguras entre subprocesos 

En los siguientes ejemplos de código se muestran dos maneras de llamar a un control de Windows Forms de forma segura desde un subproceso que no lo creó: 

1. El método <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName>, que llama a un delegado del subproceso principal para llamar al control. 
2. Un componente de <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>, que ofrece un modelo orientado a eventos. 

En ambos ejemplos, el subproceso en segundo plano se suspende durante un segundo para simular el trabajo que se realiza en ese subproceso. 

Puede compilar y ejecutar estos ejemplos como aplicaciones .NET Framework desde C# la línea de comandos de o Visual Basic. Para obtener más información, vea [compilar desde la línea de comandos con CSC. exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) o [compilar desde la línea de comandos (Visual Basic)](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md). 

A partir de .NET Core 3,0, también puede compilar y ejecutar los ejemplos como aplicaciones de Windows .NET Core desde una carpeta que tiene .NET Core Windows Forms *\<nombre de carpeta >* archivo de proyecto. csproj. 

## <a name="example-use-the-invoke-method-with-a-delegate"></a>Ejemplo: usar el método Invoke con un delegado

En el ejemplo siguiente se muestra un patrón para garantizar las llamadas seguras para subprocesos a un control de Windows Forms. Consulta la propiedad <xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName>, que compara el identificador del subproceso de creación del control con el identificador del subproceso que realiza la llamada. Si los identificadores de subproceso son iguales, llama directamente al control. Si los identificadores de subproceso son diferentes, llama al método <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=nameWithType> con un delegado del subproceso principal, que realiza la llamada real al control.

El `SafeCallDelegate` permite establecer la propiedad <xref:System.Windows.Forms.TextBox.Text%2A> del control de <xref:System.Windows.Forms.TextBox>. El método `WriteTextSafe` consulta <xref:System.Windows.Forms.Control.InvokeRequired%2A>. Si <xref:System.Windows.Forms.Control.InvokeRequired%2A> devuelve `true`, `WriteTextSafe` pasa el `SafeCallDelegate` al método <xref:System.Windows.Forms.Control.Invoke%2A> para hacer la llamada real al control. Si <xref:System.Windows.Forms.Control.InvokeRequired%2A> devuelve `false`, `WriteTextSafe` establece el <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> directamente. El controlador de eventos `Button1_Click` crea el nuevo subproceso y ejecuta el método `WriteTextSafe`. 

 [!code-csharp[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/vb/Form1.vb)]  

## <a name="example-use-a-backgroundworker-event-handler"></a>Ejemplo: usar un controlador de eventos BackgroundWorker

Una manera fácil de implementar el multithreading es con el <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> componente, que utiliza un modelo orientado a eventos. El subproceso en segundo plano ejecuta el evento <xref:System.ComponentModel.BackgroundWorker.DoWork?displayProperty=nameWithType>, que no interactúa con el subproceso principal. El subproceso principal ejecuta los controladores de eventos <xref:System.ComponentModel.BackgroundWorker.ProgressChanged?displayProperty=nameWithType> y <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted?displayProperty=nameWithType>, que pueden llamar a los controles del subproceso principal.

Para realizar una llamada segura para subprocesos mediante <xref:System.ComponentModel.BackgroundWorker>, cree un método en el subproceso en segundo plano para realizar el trabajo y enlácelo al evento <xref:System.ComponentModel.BackgroundWorker.DoWork>. Cree otro método en el subproceso principal para informar de los resultados del trabajo en segundo plano y enlácelo al <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> o <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> evento. Para iniciar el subproceso en segundo plano, llame a <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A?displayProperty=nameWithType>. 

En el ejemplo se utiliza el controlador de eventos <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> para establecer la propiedad <xref:System.Windows.Forms.TextBox.Text%2A> del control <xref:System.Windows.Forms.TextBox>. Para obtener un ejemplo del uso del evento <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>, vea <xref:System.ComponentModel.BackgroundWorker>. 

 [!code-csharp[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/vb/Form1.vb)]  

## <a name="see-also"></a>Vea también

- <xref:System.ComponentModel.BackgroundWorker>
- [Cómo: ejecutar una operación en segundo plano](how-to-run-an-operation-in-the-background.md)
- [Cómo: implementar un formulario que utiliza una operación en segundo plano](how-to-implement-a-form-that-uses-a-background-operation.md)
- [Desarrolle controles de Windows Forms personalizados con el .NET Framework](developing-custom-windows-forms-controls.md)

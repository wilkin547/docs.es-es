---
title: Realización de llamadas seguras para subprocesos a controles
ms.date: 02/19/2019
description: Obtenga información sobre cómo implementar el multithreading en la aplicación mediante una llamada a los controles entre subprocesos de una manera segura para subprocesos.
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
ms.openlocfilehash: b5f4de7bd3d8d89de98dbe27e2dbf360763670d0
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904187"
---
# <a name="how-to-make-thread-safe-calls-to-windows-forms-controls"></a>Cómo: realizar llamadas seguras para subprocesos a controles Windows Forms

El multithreading puede mejorar el rendimiento de las aplicaciones Windows Forms, pero el acceso a los controles Windows Forms no es seguro para subprocesos de forma inherente. El multithreading puede exponer el código a errores muy graves y complejos. Dos o más subprocesos que manipulan un control pueden forzar el control en un estado incoherente y conducir a condiciones de carrera, interbloqueos e inmovilizaciones o bloqueos. Si implementa multithreading en la aplicación, asegúrese de llamar a los controles entre subprocesos de una manera segura para subprocesos. Para obtener más información, vea [procedimientos recomendados para el subprocesamiento administrado](../../../standard/threading/managed-threading-best-practices.md).

Hay dos maneras de llamar a un control de Windows Forms de forma segura desde un subproceso que no creó ese control. Puede usar el <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> método para llamar a un delegado creado en el subproceso principal, que a su vez llama al control. O bien, puede implementar un <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> , que utiliza un modelo orientado a eventos para separar el trabajo realizado en el subproceso en segundo plano de los informes sobre los resultados.

## <a name="unsafe-cross-thread-calls"></a>Llamadas no seguras entre subprocesos

No es seguro llamar a un control directamente desde un subproceso que no lo creó. En el fragmento de código siguiente se muestra una llamada no segura al <xref:System.Windows.Forms.TextBox?displayProperty=nameWithType> control. El `Button1_Click` controlador de eventos crea un nuevo `WriteTextUnsafe` subproceso, que establece la propiedad del subproceso principal <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> directamente.

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

El depurador de Visual Studio detecta estas llamadas de subprocesos no seguras mediante <xref:System.InvalidOperationException> la generación de un con el mensaje, la **operación entre subprocesos no es válida. Control "" al que se tiene acceso desde un subproceso distinto del subproceso en el que se creó.** <xref:System.InvalidOperationException>Siempre se produce para llamadas no seguras entre subprocesos durante la depuración de Visual Studio y puede producirse en el tiempo de ejecución de la aplicación. Debe corregir el problema, pero puede deshabilitar la excepción estableciendo la <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A?displayProperty=nameWithType> propiedad en `false` .

## <a name="safe-cross-thread-calls"></a>Llamadas seguras entre subprocesos

En los siguientes ejemplos de código se muestran dos maneras de llamar a un control de Windows Forms de forma segura desde un subproceso que no lo creó:

1. El <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> método, que llama a un delegado del subproceso principal para llamar al control.
2. Un <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> componente, que ofrece un modelo orientado a eventos.

En ambos ejemplos, el subproceso en segundo plano se suspende durante un segundo para simular el trabajo que se realiza en ese subproceso.

Puede compilar y ejecutar estos ejemplos como aplicaciones .NET Framework desde la línea de comandos de C# o Visual Basic. Para obtener más información, vea [compilar mediante línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) o [compilar desde la línea de comandos (Visual Basic)](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).

A partir de .NET Core 3,0, también puede compilar y ejecutar los ejemplos como aplicaciones Windows .NET Core desde una carpeta que tiene un archivo de proyecto Windows Forms * \<folder name> . csproj* de .net Core.

## <a name="example-use-the-invoke-method-with-a-delegate"></a>Ejemplo: usar el método Invoke con un delegado

En el ejemplo siguiente se muestra un patrón para garantizar las llamadas seguras para subprocesos a un control de Windows Forms. Consulta la <xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName> propiedad, que compara el identificador del subproceso de creación del control con el identificador del subproceso que realiza la llamada. Si los identificadores de subproceso son iguales, llama directamente al control. Si los identificadores de subproceso son diferentes, llama al <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=nameWithType> método con un delegado del subproceso principal, que realiza la llamada real al control.

`SafeCallDelegate`Habilita el establecimiento de la <xref:System.Windows.Forms.TextBox> propiedad del control <xref:System.Windows.Forms.TextBox.Text%2A> . El `WriteTextSafe` método consulta <xref:System.Windows.Forms.Control.InvokeRequired%2A> . Si <xref:System.Windows.Forms.Control.InvokeRequired%2A> devuelve `true` , `WriteTextSafe` pasa al `SafeCallDelegate` <xref:System.Windows.Forms.Control.Invoke%2A> método para hacer la llamada real al control. Si <xref:System.Windows.Forms.Control.InvokeRequired%2A> devuelve `false` , `WriteTextSafe` establece <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> directamente. El `Button1_Click` controlador de eventos crea el nuevo subproceso y ejecuta el `WriteTextSafe` método.

 [!code-csharp[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/vb/Form1.vb)]  

## <a name="example-use-a-backgroundworker-event-handler"></a>Ejemplo: usar un controlador de eventos BackgroundWorker

Una manera fácil de implementar el multithreading es con el <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> componente, que utiliza un modelo orientado a eventos. El subproceso en segundo plano ejecuta el <xref:System.ComponentModel.BackgroundWorker.DoWork?displayProperty=nameWithType> evento, que no interactúa con el subproceso principal. El subproceso principal ejecuta <xref:System.ComponentModel.BackgroundWorker.ProgressChanged?displayProperty=nameWithType> los <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted?displayProperty=nameWithType> controladores de eventos y, que pueden llamar a los controles del subproceso principal.

Para realizar una llamada segura para subprocesos mediante <xref:System.ComponentModel.BackgroundWorker> , cree un método en el subproceso en segundo plano para realizar el trabajo y enlácelo al <xref:System.ComponentModel.BackgroundWorker.DoWork> evento. Cree otro método en el subproceso principal para informar de los resultados del trabajo en segundo plano y enlácelo al <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> evento o. Para iniciar el subproceso en segundo plano, llame a <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A?displayProperty=nameWithType> .

En el ejemplo se utiliza el <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> controlador de eventos para establecer la <xref:System.Windows.Forms.TextBox> propiedad del control <xref:System.Windows.Forms.TextBox.Text%2A> . Para obtener un ejemplo del uso del <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> evento, vea <xref:System.ComponentModel.BackgroundWorker> .

 [!code-csharp[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/vb/Form1.vb)]  

## <a name="see-also"></a>Consulte también

- <xref:System.ComponentModel.BackgroundWorker>
- [Cómo: ejecutar una operación en segundo plano](how-to-run-an-operation-in-the-background.md)
- [Cómo: implementar un formulario que utiliza una operación en segundo plano](how-to-implement-a-form-that-uses-a-background-operation.md)
- [Desarrolle controles de Windows Forms personalizados con el .NET Framework](developing-custom-windows-forms-controls.md)

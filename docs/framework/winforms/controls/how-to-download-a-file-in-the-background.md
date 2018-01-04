---
title: "Cómo: Descargar un archivo en segundo plano"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 9b7bc5ae-051c-4904-9720-18f6667388bd
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 875ad9a17078865c526770587d36b1db1adf378c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-download-a-file-in-the-background"></a>Cómo: Descargar un archivo en segundo plano
Descargar un archivo es una tarea común y, por lo general, resulta útil ejecutar esta operación que puede requerir mucho tiempo en un subproceso independiente. Use el componente <xref:System.ComponentModel.BackgroundWorker> para realizar esta tarea con muy poco código.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra cómo usar un componente <xref:System.ComponentModel.BackgroundWorker> para cargar un archivo XML desde una dirección URL. Cuando el usuario hace clic en el **descargar** botón, el <xref:System.Windows.Forms.Control.Click> llamadas del controlador de eventos el <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> método de una <xref:System.ComponentModel.BackgroundWorker> componente para iniciar la operación de descarga. El botón se deshabilita mientras dura la descarga y se vuelve a habilitar una vez completada la descarga. Un <xref:System.Windows.Forms.MessageBox> muestra el contenido del archivo.  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#1)]  
  
 **Descargar el archivo**  
  
 El archivo se descarga en el subproceso de trabajo del componente <xref:System.ComponentModel.BackgroundWorker>, que ejecuta el controlador de eventos <xref:System.ComponentModel.BackgroundWorker.DoWork>. Este subproceso se inicia cuando el código llama al método <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>.  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#3)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#3)]  
  
 **Esperar a que BackgroundWorker termine**  
  
 El controlador de eventos `downloadButton_Click` muestra cómo esperar a que un componente <xref:System.ComponentModel.BackgroundWorker> termine su tarea asincrónica.  
  
 Si solo quiere que la aplicación responda a los eventos y no quiere hacer ningún trabajo en el subproceso principal mientras espera a que termine el subproceso en segundo plano, simplemente salga del controlador.  
  
 Si quiere continuar trabajando en el subproceso principal, use la propiedad <xref:System.ComponentModel.BackgroundWorker.IsBusy%2A> para determinar si el subproceso <xref:System.ComponentModel.BackgroundWorker> todavía se está ejecutando. En el ejemplo, una barra de progreso se actualiza mientras la descarga se procesa. No olvide llamar al método <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> para mantener la capacidad de respuesta de la interfaz de usuario.  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#2)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#2)]  
  
 **Mostrar el resultado**  
  
 El método `backgroundWorker1_RunWorkerCompleted` controla el evento <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> y se le llama cuando se completa la operación en segundo plano. Este método comprueba primero la propiedad <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType>. Si <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> es `null`, este método muestra el contenido del archivo. Después, habilita el botón de descarga, que se deshabilitó cuando comenzó la descarga, y restablece la barra de progreso.  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#4)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#4)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System.Drawing, System.Windows.Forms y System.Xml.  
  
 Para información sobre cómo compilar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilación desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Compilar desde la línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Vea también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="robust-programming"></a>Programación sólida  
 Compruebe siempre la propiedad <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> en su controlador de eventos <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> antes de intentar acceder a la propiedad <xref:System.ComponentModel.RunWorkerCompletedEventArgs.Result%2A?displayProperty=nameWithType> o a cualquier otro objeto afectado por el controlador de eventos <xref:System.ComponentModel.BackgroundWorker.DoWork>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ComponentModel.BackgroundWorker>  
 [Ejecutar una operación en segundo plano](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [Cómo: Implementar un formulario que utiliza una operación en segundo plano](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)

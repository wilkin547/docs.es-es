---
title: Creación de una aplicación Windows Forms desde la línea de comandos
titleSuffix: ''
description: Obtenga información acerca de cómo completar los pasos básicos para crear y ejecutar una aplicación Windows Forms desde la línea de comandos.
ms.date: 03/14/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, application development from command line
- Windows Forms, getting started
- Windows Forms, creating basic form
ms.assetid: 45ad3f8b-1c26-4c9f-91a9-3bb0759a47a4
ms.openlocfilehash: b63bf884b9fd03a0510c7f240f19d7a14196971a
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903459"
---
# <a name="how-to-create-a-windows-forms-application-from-the-command-line"></a>Cómo: crear una aplicación de Windows Forms desde la línea de comandos

Los procedimientos siguientes describen los pasos básicos que debe seguir para crear y ejecutar una aplicación de Windows Forms desde la línea de comandos. Visual Studio es altamente compatible con estos procedimientos.  Vea también [Tutorial: hospedar un control de Windows Forms en WPF](../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).
  
## <a name="procedure"></a>Procedimiento  
  
#### <a name="to-create-the-form"></a>Para crear el formulario  
  
1. En un archivo de código vacío, escriba las `Imports` siguientes `using` instrucciones o:  
  
     [!code-csharp[System.Windows.Forms.BasicForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.BasicForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#2)]  
  
2. Declare una clase denominada `Form1` que herede de la clase de formulario:
  
     [!code-csharp[System.Windows.Forms.BasicForm#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.BasicForm#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#3)]  
  
3. Cree un constructor sin parámetros para `Form1` .
  
     Agregará más código al constructor en un procedimiento posterior.
  
     [!code-csharp[System.Windows.Forms.BasicForm#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.BasicForm#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#4)]  
  
4. Agregue un método `Main` a la clase.
  
    1. Aplique <xref:System.STAThreadAttribute> al método de C# `Main` para especificar que la aplicación Windows Forms es un contenedor uniproceso. (El atributo no es necesario en Visual Basic, ya que las aplicaciones de Windows Forms desarrolladas con Visual Basic usan de forma predeterminada un modelo de apartamento de un solo subproceso).  
  
    2. Llame <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> a para aplicar estilos de sistema operativo a la aplicación.  
  
    3. Cree una instancia del formulario y ejecútela.  
  
     [!code-csharp[System.Windows.Forms.BasicForm#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.BasicForm#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#5)]  
  
#### <a name="to-compile-and-run-the-application"></a>Para compilar y ejecutar la aplicación  
  
1. En el símbolo del sistema de .NET Framework, vaya al directorio donde creó la clase `Form1`.  
  
2. Compile el formulario.  
  
    - Si usa C#, escriba:`csc form1.cs`  
  
         `-or-`  
  
    - Si está utilizando Visual Basic, escriba:`vbc form1.vb`  
  
3. En el símbolo del sistema, escriba: `Form1.exe`  
  
## <a name="adding-a-control-and-handling-an-event"></a>Agregar un control y controlar un evento

Los pasos del procedimiento anterior muestran cómo crear un Windows Form básico que se compila y se ejecuta. El procedimiento siguiente mostrará cómo crear y agregar un control al formulario y cómo controlar un evento del control. Para obtener más información sobre los controles que se pueden agregar a Windows Forms, vea [controles de Windows Forms](./controls/index.md).
  
 Además de comprender cómo se crean las aplicaciones de Windows Forms, debe conocer la programación basada en eventos y cómo controlar la entrada de datos del usuario. Para obtener más información, vea [crear controladores de eventos en Windows Forms](creating-event-handlers-in-windows-forms.md)y [controlar los datos proporcionados](./controls/handling-user-input.md) por el usuario.  
  
#### <a name="to-declare-a-button-control-and-handle-its-click-event"></a>Para declarar un control de botón y controlar su evento de clic  
  
1. Declare un control de botón llamado `button1`.  
  
2. En el constructor, cree el botón y establezca sus propiedades <xref:System.Windows.Forms.Control.Size%2A>, <xref:System.Windows.Forms.Control.Location%2A> y <xref:System.Windows.Forms.Control.Text%2A>.  
  
3. Agregue el botón al formulario.  
  
     En el ejemplo de código siguiente se muestra cómo declarar el control de botón:
  
     [!code-csharp[System.Windows.Forms.FormWithButton#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.FormWithButton#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#2)]  
  
4. Cree un método para controlar los eventos <xref:System.Windows.Forms.Control.Click> del botón.  
  
5. En el controlador de eventos de clic, muestre un <xref:System.Windows.Forms.MessageBox> con el mensaje "Hello World".  
  
     En el ejemplo de código siguiente se muestra cómo controlar el evento click del control Button:
  
     [!code-csharp[System.Windows.Forms.FormWithButton#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.FormWithButton#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#3)]  
  
6. Asocie el evento <xref:System.Windows.Forms.Control.Click> con el método que se ha creado.  
  
     En el ejemplo de código siguiente se muestra cómo asociar el evento con el método.  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.FormWithButton#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#4)]  
  
7. Compile y ejecute la aplicación tal y como se describe en el procedimiento anterior.  
  
## <a name="example"></a>Ejemplo  

El ejemplo de código siguiente es el ejemplo completo de los procedimientos anteriores:
  
 [!code-csharp[System.Windows.Forms.FormWithButton#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.FormWithButton#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Control>
- [Cambiar la apariencia de formularios Windows Forms](changing-the-appearance-of-windows-forms.md)
- [Mejorar las aplicaciones de Windows Forms](./advanced/index.md)
- [Introducción con Windows Forms](getting-started-with-windows-forms.md)

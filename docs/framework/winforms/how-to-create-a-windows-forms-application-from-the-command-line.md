---
title: Crear una aplicación de formularios Windows Forms desde la línea de comandos
titleSuffix: ''
ms.date: 03/14/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, application development from command line
- Windows Forms, getting started
- Windows Forms, creating basic form
ms.assetid: 45ad3f8b-1c26-4c9f-91a9-3bb0759a47a4
ms.openlocfilehash: 7bd3add526a6b60d628b05d46eca22ce407c36b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181984"
---
# <a name="how-to-create-a-windows-forms-application-from-the-command-line"></a>Cómo: Crear una aplicación de Windows Forms desde la línea de comandos

Los procedimientos siguientes describen los pasos básicos que debe seguir para crear y ejecutar una aplicación de Windows Forms desde la línea de comandos. Visual Studio es altamente compatible con estos procedimientos.  Consulte también Tutorial: Hospedar un control de [formularios Windows Forms en WPFWPF](../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).
  
## <a name="procedure"></a>Procedimiento  
  
#### <a name="to-create-the-form"></a>Para crear el formulario  
  
1. En un archivo de código `Imports` `using` vacío, escriba lo siguiente o las instrucciones:  
  
     [!code-csharp[System.Windows.Forms.BasicForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.BasicForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#2)]  
  
2. Declare una `Form1` clase denominada que herede de la clase Form:
  
     [!code-csharp[System.Windows.Forms.BasicForm#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.BasicForm#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#3)]  
  
3. Cree un constructor `Form1`sin parámetros para .
  
     Agregará más código al constructor en un procedimiento posterior.
  
     [!code-csharp[System.Windows.Forms.BasicForm#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.BasicForm#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#4)]  
  
4. Agregue un método `Main` a la clase.
  
    1. Aplicar <xref:System.STAThreadAttribute> el método `Main` a la c- para especificar la aplicación de formularios Windows Forms es un apartamento de un solo subproceso. (El atributo no es necesario en Visual Basic, ya que las aplicaciones de formularios de Windows desarrolladas con Visual Basic usan un modelo de apartamento de un solo subproceso de forma predeterminada.)  
  
    2. Llame <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> para aplicar estilos de sistema operativo a la aplicación.  
  
    3. Cree una instancia del formulario y ejecútela.  
  
     [!code-csharp[System.Windows.Forms.BasicForm#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.BasicForm#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#5)]  
  
#### <a name="to-compile-and-run-the-application"></a>Para compilar y ejecutar la aplicación  
  
1. En el símbolo del sistema de .NET Framework, vaya al directorio donde creó la clase `Form1`.  
  
2. Compile el formulario.  
  
    - Si está utilizando C, escriba:`csc form1.cs`  
  
         `-or-`  
  
    - Si usa Visual Basic, escriba:`vbc form1.vb`  
  
3. En el símbolo del sistema, escriba: `Form1.exe`  
  
## <a name="adding-a-control-and-handling-an-event"></a>Agregar un control y controlar un evento

Los pasos del procedimiento anterior muestran cómo crear un Windows Form básico que se compila y se ejecuta. El procedimiento siguiente mostrará cómo crear y agregar un control al formulario y cómo controlar un evento del control. Para obtener más información acerca de los controles que puede agregar a formularios Windows Forms, vea Controles de [formularios Windows Forms](./controls/index.md).
  
 Además de comprender cómo se crean las aplicaciones de Windows Forms, debe conocer la programación basada en eventos y cómo controlar la entrada de datos del usuario. Para obtener más información, vea [Crear controladores](creating-event-handlers-in-windows-forms.md)de eventos en formularios Windows Forms y [Controlar la entrada](./controls/handling-user-input.md) de usuario  
  
#### <a name="to-declare-a-button-control-and-handle-its-click-event"></a>Para declarar un control de botón y controlar su evento de clic  
  
1. Declare un control de botón llamado `button1`.  
  
2. En el constructor, cree el botón y establezca sus propiedades <xref:System.Windows.Forms.Control.Size%2A>, <xref:System.Windows.Forms.Control.Location%2A> y <xref:System.Windows.Forms.Control.Text%2A>.  
  
3. Agregue el botón al formulario.  
  
     En el ejemplo de código siguiente se muestra cómo declarar el control button:
  
     [!code-csharp[System.Windows.Forms.FormWithButton#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.FormWithButton#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#2)]  
  
4. Cree un método para controlar los eventos <xref:System.Windows.Forms.Control.Click> del botón.  
  
5. En el controlador de eventos de clic, muestre un <xref:System.Windows.Forms.MessageBox> con el mensaje "Hello World".  
  
     En el ejemplo de código siguiente se muestra cómo controlar el evento click del control de botón:
  
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
- [Introducción a los formularios Windows Forms](getting-started-with-windows-forms.md)

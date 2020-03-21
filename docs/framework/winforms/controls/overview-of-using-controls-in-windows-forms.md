---
title: Descripción general del uso de controles
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, controls
- controls [Windows Forms]
- custom controls [Windows Forms]
ms.assetid: fddbe951-4485-459d-a5fd-665ea346dbc1
ms.openlocfilehash: bcd0e81b730c2fc7b741662ae803633de4f6199e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141736"
---
# <a name="overview-of-using-controls-in-windows-forms"></a><span data-ttu-id="b3f60-102">Información general sobre cómo utilizar controles en los formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b3f60-102">Overview of Using Controls in Windows Forms</span></span>
<span data-ttu-id="b3f60-103">En este tema se describen los elementos esenciales de una aplicación de formularios Windows Forms y se proporciona un ejemplo sencillo que usa controles y controla eventos en una aplicación de windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b3f60-103">This topic describes the essential elements of a Windows Forms application and provides a simple example that uses controls and handles events in a Windows Forms application.</span></span>  
  
## <a name="simple-windows-forms-applications"></a><span data-ttu-id="b3f60-104">Aplicaciones simples de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b3f60-104">Simple Windows Forms Applications</span></span>  
 <span data-ttu-id="b3f60-105">Como mínimo, una aplicación de formularios Windows Forms consta de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="b3f60-105">At a minimum, a Windows Forms application consists of the following elements:</span></span>  
  
- <span data-ttu-id="b3f60-106">Una o más clases que derivan de <xref:System.Windows.Forms.Form?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b3f60-106">One or more classes that derive from <xref:System.Windows.Forms.Form?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="b3f60-107">Método `Main` que invoca `static` el`shared` método ( <xref:System.Windows.Forms.Application.Run%2A> en Visual <xref:System.Windows.Forms.Form> Basic) y le pasa una instancia.</span><span class="sxs-lookup"><span data-stu-id="b3f60-107">A `Main` method that invokes the `static` (`shared` in Visual Basic) <xref:System.Windows.Forms.Application.Run%2A> method and passes a <xref:System.Windows.Forms.Form> instance to it.</span></span> <span data-ttu-id="b3f60-108">El <xref:System.Windows.Forms.Application.Run%2A> método procesa los mensajes del sistema operativo a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b3f60-108">The <xref:System.Windows.Forms.Application.Run%2A> method processes messages from the operating system to the application.</span></span>  
  
 <span data-ttu-id="b3f60-109">En el ejemplo de código siguiente se muestran los elementos esenciales de una aplicación de windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b3f60-109">The following code example shows the essential elements of a Windows Forms application.</span></span>  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.Windows.Forms  
  
Public Class MyForm  
   Inherits Form  
  
   Public Sub New()  
      Me.Text = "Hello World"  
   End Sub 'New  
  
   <STAThread()> _  
   Public Shared Sub Main()  
      Dim aform As New MyForm()  
      ' The Application.Run method processes messages from the operating system
      ' to your application. If you comment out the next line of code,
      ' your application will compile and execute, but because it is not in the  
      ' message loop, it will exit after an instance of the form is created.  
      Application.Run(aform)  
   End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Windows.Forms;  
  
public class MyForm : Form {  
  
   public MyForm() {  
      this.Text = "Hello World";  
   }  
   [STAThread]  
   public static void Main(string[] args) {  
     MyForm aform = new MyForm();  
// The Application.Run method processes messages from the operating system
// to your application. If you comment out the next line of code,
// your application will compile and execute, but because it is not in the // message loop, it will exit after an instance of the form is created.  
      Application.Run(aform);  
   }  
}  
```  
  
## <a name="using-controls-in-a-windows-forms-application"></a><span data-ttu-id="b3f60-110">Uso de controles en una aplicación de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b3f60-110">Using Controls in a Windows Forms Application</span></span>  
 <span data-ttu-id="b3f60-111">En el ejemplo de código siguiente se muestra una aplicación sencilla que ilustra cómo las aplicaciones de Windows Forms usan controles y controlan eventos.</span><span class="sxs-lookup"><span data-stu-id="b3f60-111">The following code example shows a simple application that illustrates how Windows Forms applications use controls and handle events.</span></span> <span data-ttu-id="b3f60-112">El ejemplo consta de tres botones en un formulario; cada botón cambia el color de fondo cuando se hace clic.</span><span class="sxs-lookup"><span data-stu-id="b3f60-112">The example consists of three buttons on a form; each button changes the background color when clicked.</span></span>  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.ComponentModel  
Imports System.Windows.Forms  
Imports System.Resources  
Imports System.Drawing  
  
Public Class MyForm  
   Inherits Form  
   Private red As Button  
   Private blue As Button  
   Private green As Button  
  
   Public Sub New()  
      InitializeComponent()  
   End Sub  
  
   Protected Overloads Overrides Sub Dispose(disposing as Boolean)  
      MyBase.Dispose(disposing)  
   End Sub  
  
   ' InitializeComponent is a helper method for the constructor.
   ' It is included for consistency with code that is
   ' auto-generated by the Windows Forms designer in Visual Studio.
   Private Sub InitializeComponent()  
  
      ' Creates three buttons, sets their properties, and attaches  
      ' an event handler to each button.  
      red = New Button()  
      red.Text = "Red"  
      red.Location = New Point(100, 50)  
      red.Size = New Size(50, 50)  
      AddHandler red.Click, AddressOf button_Click  
      Controls.Add(red)  
  
      blue = New Button()  
      blue.Text = "Blue"  
      blue.Location = New Point(100, 100)  
      blue.Size = New Size(50, 50)  
      AddHandler blue.Click, AddressOf button_Click  
      Controls.Add(blue)  
  
      green = New Button()  
      green.Text = "Green"  
      green.Location = New Point(100, 150)  
      green.Size = New Size(50, 50)  
      AddHandler green.Click, AddressOf button_Click  
      Controls.Add(green)  
   End Sub  
  
   ' Event handler.  
   Private Sub button_Click(sender As Object, e As EventArgs)  
      If sender Is red Then  
         Me.BackColor = Color.Red  
      Else  
         If sender Is blue Then  
            Me.BackColor = Color.Blue  
         Else  
            Me.BackColor = Color.Green  
         End If  
      End If
   End Sub  
  
   ' The STAThreadAttribute informs the common language runtime that  
   ' Windows Forms uses the single-threaded apartment model.  
   <STAThread()> _  
   Public Shared Sub Main()  
      Application.Run(New MyForm())  
   End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.ComponentModel;  
using System.Windows.Forms;  
using System.Resources;  
using System.Drawing;  
  
public class MyForm : Form {  
   private Button red;  
   private Button blue;  
   private Button green;  
  
   public MyForm() : base() {
      InitializeComponent();
   }  
  
   protected override void Dispose(bool disposing) {  
      base.Dispose(disposing);  
   }  
  
// InitializeComponent is a helper method for the constructor.
// It is included for consistency with code that is
// auto-generated by the Windows Forms designer in Visual Studio.
   private void InitializeComponent() {  
  
// A delegate for the click event of a button. The argument to
// the constructor contains a reference to the method that performs the
// event handling logic.  
      EventHandler handler = new EventHandler(button_Click);  
  
// Creates three buttons, sets their properties, and attaches  
// an event handler to each button.  
  
      red = new Button();  
      red.Text = "Red";  
      red.Location = new Point(100, 50);  
      red.Size = new Size(50, 50);  
      red.Click +=handler;  
      Controls.Add(red);  
  
      blue = new Button();  
      blue.Text = "Blue";  
      blue.Location = new Point(100, 100);  
      blue.Size = new Size(50, 50);  
      blue.Click += handler;  
      Controls.Add(blue);  
  
      green = new Button();  
      green.Text = "Green";  
      green.Location = new Point(100, 150);  
      green.Size = new Size(50, 50);  
      green.Click += handler;  
      Controls.Add(green);
      }  
  
   // Event handler.  
   private void button_Click(object sender, EventArgs e) {  
            if (sender == red) this.BackColor = Color.Red ;  
                  else if (sender == blue) this.BackColor = Color.Blue;  
                  else this.BackColor = Color.Green;  
        }  
   // The STAThreadAttribute informs the common language runtime that  
   // Windows Forms uses the single-threaded apartment model.  
  [STAThread]  
   public static void Main(string[] args) {  
   Application.Run(new MyForm());  
   }  
  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="b3f60-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b3f60-113">See also</span></span>

- [<span data-ttu-id="b3f60-114">Desarrollar controles personalizados de Windows Forms con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b3f60-114">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="b3f60-115">Fundamentos de desarrollo de controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b3f60-115">Windows Forms Control Development Basics</span></span>](windows-forms-control-development-basics.md)

---
title: "How to: Modify Keyboard Input to a Standard Control | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "keyboard input, modifying"
  - "modifying keyboard input"
  - "Windows Forms, modifying keyboard input"
  - "keyboards, keyboard input"
ms.assetid: 626d3712-d866-4988-bcda-a2d5b36ec0ba
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# How to: Modify Keyboard Input to a Standard Control
Windows Forms permite consumir y modificar la entrada de teclado.  Consumir una tecla es controlar una tecla dentro de un método o controlador de eventos para que otros métodos y eventos más abajo en la cola de mensajes no reciban el valor de la tecla.  Modificar una tecla es modificar el valor de una tecla para que los métodos y controladores de eventos más abajo en la cola de mensajes reciban un valor de tecla diferente.  En este tema se muestra cómo realizar estas tareas.  
  
### Para consumir una tecla  
  
-   En un controlador de eventos <xref:System.Windows.Forms.Control.KeyPress>, establezca la propiedad <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> de la clase <xref:System.Windows.Forms.KeyPressEventArgs> en `true`.  
  
     O bien  
  
     En un controlador de eventos <xref:System.Windows.Forms.Control.KeyDown>, establezca la propiedad <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> de la clase <xref:System.Windows.Forms.KeyEventArgs> en `true`.  
  
    > [!NOTE]
    >  Establecer la propiedad <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> en el controlador de eventos <xref:System.Windows.Forms.Control.KeyDown> no impide que los eventos <xref:System.Windows.Forms.Control.KeyPress> y <xref:System.Windows.Forms.Control.KeyUp> se generen para la pulsación de tecla actual.  Use la propiedad <xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A> para este propósito.  
  
     El ejemplo siguiente es un extracto de una instrucción `switch` que examina la propiedad <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> de <xref:System.Windows.Forms.KeyPressEventArgs> recibido por un controlador de eventos <xref:System.Windows.Forms.Control.KeyPress>.  Este código consume las teclas de caracteres 'A' y 'a'.  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#6](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#6)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#6](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#6)]  
  
### Para modificar una tecla de carácter estándar  
  
-   En un controlador de eventos <xref:System.Windows.Forms.Control.KeyPress>, establezca la propiedad <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> de la clase <xref:System.Windows.Forms.KeyPressEventArgs> en el valor de la nueva tecla de carácter.  
  
     El ejemplo siguiente es un extracto de una instrucción `switch` que modifica 'B' por 'A' y 'b' por 'a'.  Tenga en cuenta que la propiedad <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> del parámetro <xref:System.Windows.Forms.KeyPressEventArgs> está establecida en `false`, por lo que el nuevo valor de tecla se propaga a otros métodos y eventos de la cola de mensajes.  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#7](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#7)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#7](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#7)]  
  
### Para modificar una tecla que no es de carácter  
  
-   Invalide un método <xref:System.Windows.Forms.Control> que procesa los mensajes de Windows, detecte el mensaje WM\_KEYDOWN o WM\_SYSKEYDOWN y establezca la propiedad <xref:System.Windows.Forms.Message.WParam%2A> del parámetro <xref:System.Windows.Forms.Message> en el valor <xref:System.Windows.Forms.Keys> que representa la nueva tecla que no es de carácter.  
  
     En el ejemplo de código siguiente se muestra cómo invalidar el método <xref:System.Windows.Forms.Control.PreProcessMessage%2A> de un control para detectar las teclas F1 a F9 y modificar cualquier pulsación de tecla de F3 por F1.  Para obtener más información sobre los métodos <xref:System.Windows.Forms.Control> que se pueden invalidar para interceptar los mensajes del teclado, consulte [User Input in a Windows Forms Application](../../../docs/framework/winforms/user-input-in-a-windows-forms-application.md) y [How Keyboard Input Works](../../../docs/framework/winforms/how-keyboard-input-works.md).  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#12](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#12)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#12](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#12)]  
  
## Ejemplo  
 El ejemplo de código siguiente es la aplicación completa de los ejemplos de código de las secciones anteriores.  La aplicación usa un control personalizado derivado de la clase <xref:System.Windows.Forms.TextBox> para consumir y modificar la entrada de teclado.  
  
 [!code-csharp[System.Windows.Forms.KeyBoardInput#0](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.KeyBoardInput#0](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#0)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.  
  
 Para obtener información acerca de cómo compilar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../includes/csprcs-md.md)], consulte [Compilar desde la línea de comandos](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) o [Compilar la línea de comandos con csc.exe](../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228%20\(v=vs.110\)).  
  
## Vea también  
 [Keyboard Input in a Windows Forms Application](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)   
 [User Input in a Windows Forms Application](../../../docs/framework/winforms/user-input-in-a-windows-forms-application.md)   
 [How Keyboard Input Works](../../../docs/framework/winforms/how-keyboard-input-works.md)
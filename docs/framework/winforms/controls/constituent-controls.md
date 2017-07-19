---
title: "Controles constituyentes | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "controles constituyentes"
  - "controles personalizados [Windows Forms], controles constituyentes"
  - "controles de usuario [Windows Forms], controles constituyentes"
  - "UserControl (clase)"
ms.assetid: 5565e720-198b-4bbd-a2bd-c447ba641798
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Controles constituyentes
Los controles que componen un control de usuario, que se denominan *controles constituyentes*, son relativamente inflexibles en lo relativo a la representación gráfica personalizada.  Todos los controles de formularios Windows Forms controlan su propia representación por medio de su método <xref:System.Windows.Forms.Control.OnPaint%2A>.  Este método está protegido, por lo que no permite el acceso al programador y, por lo tanto, no se puede evitar que se ejecute al dibujar el control.  Esto no significa, sin embargo, que no pueda agregar código que afecte a la apariencia de los controles constituyentes.  Para disponer de más posibilidades de representación, puede agregar un controlador de eventos.  Por ejemplo, suponga que está creando un control <xref:System.Windows.Forms.UserControl> con un botón denominado `MyButton`.  Si desea realizar otras tareas de representación distintas de las que proporciona la [clase Button](frlrfSystemWebUIWebControlsButtonClassTopic), puede agregar al control de usuario código similar al siguiente:  
  
```vb  
Public Sub MyPaint(ByVal sender as Object, e as PaintEventArgs) Handles _  
   MyButton.Paint  
   'Additional rendering code goes here  
End Sub  
  
```  
  
```csharp  
// Add the event handler to the button's Paint event.  
MyButton.Paint +=   
   new System.Windows.Forms.PaintEventHandler (this.MyPaint);  
// Create the custom painting method.  
protected void MyPaint (object sender,   
System.Windows.Forms.PaintEventArgs e)  
{  
   // Additional rendering code goes here.  
}  
```  
  
> [!NOTE]
>  Algunos controles de formularios Windows Forms, como <xref:System.Windows.Forms.TextBox>, los dibuja Windows directamente.  En estas instancias, nunca se llama al método <xref:System.Windows.Forms.Control.OnPaint%2A>, por lo que nunca se llamaría al ejemplo anterior.  
  
 Este ejemplo crea un método que se ejecuta siempre que se ejecuta el evento `MyButton.Paint`; de esta manera, se agrega al control una representación gráfica adicional.  Observe que esto no impide la ejecución de `MyButton.OnPaint`; por tanto, además de la representación personalizada, se seguirán realizando todas las tareas de dibujo que suele efectuar un botón.  Para obtener información detallada acerca de la tecnología GDI\+ y de la representación personalizada, vea [Crear imágenes gráficas con GDI\+](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).  Si desea obtener una representación única del control, lo más recomendable es crear un control heredado y escribir para él código de representación personalizado.  Para obtener información detallada, vea [Controles dibujados por el usuario](../../../../docs/framework/winforms/controls/user-drawn-controls.md).  
  
## Vea también  
 <xref:System.Windows.Forms.UserControl>   
 <xref:System.Windows.Forms.Control.OnPaint%2A>   
 [Controles dibujados por el usuario](../../../../docs/framework/winforms/controls/user-drawn-controls.md)   
 [Cómo: Crear objetos Graphics para dibujar](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [Variedades de controles personalizados](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
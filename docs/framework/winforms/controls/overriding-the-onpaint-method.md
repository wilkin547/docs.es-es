---
title: "Reemplazar el m&#233;todo OnPaint | Microsoft Docs"
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
  - "OnPaint (método), reemplazar en controles personalizados de Windows Forms"
  - "Paint (evento), controlar en controles personalizados de Windows Forms"
ms.assetid: e9ca2723-0107-4540-bb21-4f5ffb4a9906
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Reemplazar el m&#233;todo OnPaint
Los pasos básicos para reemplazar un evento definido en [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] son los mismos y se resumen en la siguiente lista.  
  
#### Para reemplazar un evento heredado  
  
1.  Invalide el método protegido `On`*nombreDeEvento*.  
  
2.  Llame al método `On`*nombreDeEvento* de la clase base desde el método invalidado `On`*nombreDeEvento*, para que los delegados registrados reciban el evento.  
  
 El evento <xref:System.Windows.Forms.Control.Paint> se explica aquí en detalle dado que cada control de formularios Windows Forms debe reemplazar el evento <xref:System.Windows.Forms.Control.Paint> que hereda de <xref:System.Windows.Forms.Control>.  La clase base <xref:System.Windows.Forms.Control> no sabe cómo debe dibujarse un control derivado y no proporciona una lógica de representación en el método <xref:System.Windows.Forms.Control.OnPaint%2A>.  El método <xref:System.Windows.Forms.Control.OnPaint%2A> de <xref:System.Windows.Forms.Control> se limita a enviar el evento <xref:System.Windows.Forms.Control.Paint> a los receptores de elemento registrados.  
  
 Si ha realizado el ejemplo de [Cómo: Desarrollar un control de formularios Windows Forms sencillo](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md), ha podido ver un ejemplo de cómo reemplazar el método <xref:System.Windows.Forms.Control.OnPaint%2A>.  El fragmento de código siguiente está tomado de dicho ejemplo.  
  
```vb  
Public Class FirstControl  
   Inherits Control  
  
   Public Sub New()  
   End Sub  
  
   Protected Overrides Sub OnPaint(e As PaintEventArgs)  
      ' Call the OnPaint method of the base class.  
      MyBase.OnPaint(e)  
      ' Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, New SolidBrush(ForeColor), RectangleF.op_Implicit(ClientRectangle))  
   End Sub  
End Class   
```  
  
```csharp  
public class FirstControl : Control{  
   public FirstControl() {}  
   protected override void OnPaint(PaintEventArgs e) {  
      // Call the OnPaint method of the base class.  
      base.OnPaint(e);  
      // Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, new SolidBrush(ForeColor), ClientRectangle);  
   }   
}   
```  
  
 La clase <xref:System.Windows.Forms.PaintEventArgs> contiene datos del evento <xref:System.Windows.Forms.Control.Paint>.  Posee dos propiedades, como se muestra en el código siguiente.  
  
```vb  
Public Class PaintEventArgs  
   Inherits EventArgs  
   ...  
   Public ReadOnly Property ClipRectangle() As System.Drawing.Rectangle  
      ...  
   End Property  
  
   Public ReadOnly Property Graphics() As System.Drawing.Graphics  
      ...  
   End Property   
   ...  
End Class  
```  
  
```csharp  
public class PaintEventArgs : EventArgs {  
...  
    public System.Drawing.Rectangle ClipRectangle {}  
    public System.Drawing.Graphics Graphics {}  
...  
}  
```  
  
 La propiedad <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> es el rectángulo que se va a representar y la propiedad <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> hace referencia a un objeto <xref:System.Drawing.Graphics>.  Las clases del espacio de nombres <xref:System.Drawing?displayProperty=fullName> son clases administradas que proporcionan acceso a la funcionalidad de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], la nueva biblioteca gráfica de Windows.  El objeto <xref:System.Drawing.Graphics> dispone de métodos para dibujar puntos, cadenas, líneas, arcos, elipses y muchas otras formas.  
  
 Un control invoca su método <xref:System.Windows.Forms.Control.OnPaint%2A> cuando necesita cambiar su apariencia visual.  Este método provoca a su vez el evento <xref:System.Windows.Forms.Control.Paint>.  
  
## Vea también  
 [Eventos](../../../../docs/standard/events/index.md)   
 [Representar un control de formularios Windows Forms](../../../../docs/framework/winforms/controls/rendering-a-windows-forms-control.md)   
 [Definir un evento en los controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)
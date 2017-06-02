---
title: "C&#243;mo: Crear teclas de acceso con controles Label de formularios Windows Forms | Microsoft Docs"
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
  - "teclas de acceso, crear para controles"
  - "teclas de acceso, Windows Forms"
  - "controles [Windows Forms], teclas de acceso"
  - "controles de cuadro de diálogo, teclas de acceso"
  - "métodos abreviados de teclado, crear para controles"
  - "Label (control) [Windows Forms], crear teclas de acceso"
  - "teclas de acceso"
  - "teclas de acceso, agregar a controles de cuadro de diálogo"
  - "UseMnemonic (propiedad), Label (control)"
  - "controles de Windows Forms, teclas de acceso"
ms.assetid: 5ee8f823-80be-4a4f-96a4-412671e2e306
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Crear teclas de acceso con controles Label de formularios Windows Forms
Los controles <xref:System.Windows.Forms.Label> de formularios Windows Forms pueden utilizarse para definir teclas de acceso a otros controles.  Cuando se define una tecla de acceso en un control de etiqueta, el usuario puede presionar simultáneamente la tecla ALT y el carácter designado para mover el foco al control que lo sigue en el orden de tabulación.  Puesto que las etiquetas no pueden recibir el foco, éste se mueve automáticamente al control siguiente en el orden de tabulación.  Utilice esta técnica para asignar teclas de acceso a cuadros de texto, cuadros combinados, cuadros de lista y cuadrículas de datos.  
  
### Para asignar una tecla de acceso a un control mediante una etiqueta  
  
1.  Dibuje primero la etiqueta y, a continuación, el otro control.  
  
     O bien  
  
     Dibuje los controles en el orden que desee y establezca el valor de la propiedad <xref:System.Windows.Forms.Control.TabIndex%2A> de la etiqueta en el valor del otro control menos uno.  
  
2.  Establezca la propiedad <xref:System.Windows.Forms.Label.UseMnemonic%2A> de la etiqueta en `true`.  
  
3.  Utilice una Y comercial \(&\) en la propiedad <xref:System.Windows.Forms.Label.Text%2A> de la etiqueta para asignar la tecla de acceso a la etiqueta.  Para obtener más información, vea [Crear teclas de acceso para controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).  
  
    > [!NOTE]
    >  Es posible que desee mostrar una Y comercial en un control de etiqueta, en lugar de utilizarla para crear teclas de acceso.  Esto puede ocurrir si enlaza un control de etiqueta con un campo de un conjunto de registros en el que los datos incluyen alguna Y comercial.  Para mostrar una Y comercial en un control de etiqueta, establezca el valor de la propiedad <xref:System.Windows.Forms.Label.UseMnemonic%2A> en `false`.  Si desea mostrar símbolos de Y comercial y tener, además, una tecla de acceso, establezca la propiedad <xref:System.Windows.Forms.Label.UseMnemonic%2A> en `true` e indique la tecla de acceso con una Y comercial \(&\) y la Y comercial que se debe mostrar, con dos símbolos de Y comercial.  
  
    ```vb  
    Label1.UseMnemonic = True  
    Label1.Text = "&Print"  
    Label2.UseMnemonic = True  
    Label2.Text = "&Copy && Paste"  
  
    ```  
  
    ```csharp  
    label1.UseMnemonic = true;  
    label1.Text = "&Print";  
    label2.UseMnemonic = true;  
    label2.Text = "&Copy && Paste";  
  
    ```  
  
    ```cpp  
    label1->UseMnemonic = true;  
    label1->Text = "&Print";  
    label2->UseMnemonic = true;  
    label2->Text = "&Copy && Paste";  
    ```  
  
## Vea también  
 [Cómo: Cambiar el tamaño de un control Label de formularios Windows Forms para ajustar su contenido](../../../../docs/framework/winforms/controls/how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)   
 [Información general sobre el control Label](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)   
 [Label \(Control\)](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)
---
title: "C&#243;mo: Establecer el texto mostrado por un control de formularios Windows Forms | Microsoft Docs"
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
  - "control de botón [Windows Forms], texto del botón"
  - "control de botón [Windows Forms], presentación del texto"
  - "botones, texto"
  - "títulos, establecer"
  - "títulos, controles de Windows Forms"
  - "controles [Windows Forms], títulos"
  - "ejemplos [Windows Forms], controles"
  - "formularios, títulos"
  - "etiquetas, agregar al control CommandButton"
  - "objeto StdFont y título CommandButton"
  - "texto"
  - "Text (propiedad), control de Windows Forms"
  - "texto, controles de Windows Forms"
  - "Windows Forms, títulos"
ms.assetid: 36b95bff-8780-479d-b86a-f1a0673653aa
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# C&#243;mo: Establecer el texto mostrado por un control de formularios Windows Forms
Normalmente, los controles de Windows Forms muestran algún texto relacionado con la función principal del control.  Por ejemplo, un control <xref:System.Windows.Forms.Button> suele mostrar un título que indica qué acción se realizará al hacer clic en el botón.  Para todos los controles, puede establecer o devolver el texto usando la propiedad <xref:System.Windows.Forms.Control.Text%2A>.  Puede cambiar la fuente usando la propiedad <xref:System.Windows.Forms.Control.Font%2A>.  También puede establecer el texto mediante el diseñador.  Consulte también [Cómo: Crear teclas de acceso para controles de Windows Forms mediante el Diseñador](http://msdn.microsoft.com/library/ms233673\(v=vs.110\)), [Cómo: Establecer el texto mostrado por un control de Windows Forms mediante el Diseñador](http://msdn.microsoft.com/library/ms233665\(v=vs.110\)), [Cómo: Establecer la imagen que muestra un control de Windows Forms mediante el Diseñador](http://msdn.microsoft.com/library/ms233656\(v=vs.110\)).  
  
### Para establecer mediante programación el texto que un control muestra  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.Control.Text%2A> en una cadena.  
  
     Para crear una tecla de acceso subrayada, incluya un signo de Y comercial \(&\) antes de la letra que será la tecla de acceso.  
  
2.  Establezca la propiedad <xref:System.Windows.Forms.Control.Font%2A> en un objeto del tipo <xref:System.Drawing.Font>.  
  
    ```vb  
    Button1.Text = "Click here to save changes"  
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)  
    ```  
  
    ```csharp  
    button1.Text = "Click here to save changes";  
    button1.Font = new Font("Arial", 10, FontStyle.Bold,  
       GraphicsUnit.Point);  
    ```  
  
    ```cpp#  
    button1->Text = "Click here to save changes";  
    button1->Font = new System::Drawing::Font("Arial",  
       10, FontStyle::Bold, GraphicsUnit::Point);  
    ```  
  
    > [!NOTE]
    >  Puede usar un carácter de escape para mostrar un carácter especial en elementos de la interfaz de usuario que normalmente interpretarían de forma distinta, por ejemplo, elementos de menú.  Por ejemplo, la siguiente línea de código establece el texto del elemento de menú en "& Now For Something Completely Different":  
  
    ```vb  
    MPMenuItem.Text = "&& Now For Something Completely Different"  
    ```  
  
    ```csharp  
    mpMenuItem.Text = "&& Now For Something Completely Different";  
    ```  
  
    ```cpp#  
    mpMenuItem->Text = "&& Now For Something Completely Different";  
  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.Control.Text%2A?displayProperty=fullName>   
 [Cómo: Crear teclas de acceso para controles de Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)   
 [Cómo: Responder a clics de botones en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)
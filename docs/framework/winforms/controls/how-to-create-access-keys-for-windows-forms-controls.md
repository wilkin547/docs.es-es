---
title: "C&#243;mo: Crear teclas de acceso para controles de Windows Forms | Microsoft Docs"
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
  - "tecla ALT"
  - "y comercial en una tecla de método abreviado"
  - "control de botón [Windows Forms], teclas de acceso"
  - "controles [Windows Forms], teclas de acceso"
  - "controles de cuadro de diálogo, teclas de acceso"
  - "ejemplos [Windows Forms], controles"
  - "métodos abreviados de teclado, crear para controles"
  - "teclas de acceso"
  - "teclas de acceso, agregar a controles de cuadro de diálogo"
  - "Text (propiedad), especificar teclas de acceso para controles"
  - "controles de Windows Forms, teclas de acceso"
ms.assetid: 4faa0991-28ec-4eca-91db-51dc2cd6a7ac
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Crear teclas de acceso para controles de Windows Forms
Una *tecla de acceso* es un carácter subrayado en el texto de un menú, un elemento de menú o la etiqueta de un control tal como un botón.  Permite que el usuario "haga clic" en un botón al presionar la tecla ALT en combinación con la tecla de acceso predefinida.  Por ejemplo, si un botón ejecuta un procedimiento para imprimir un formulario y, por lo tanto, su propiedad `Text` se establece en "Imprimir", y se agrega un símbolo de Y comercial \("&"\) antes de la letra "P", ésta aparecerá subrayada en el texto del botón en tiempo de ejecución.  El usuario puede ejecutar el comando asociado al botón presionando ALT\+P.  No se puede tener una tecla de acceso en un control que no puede recibir el foco.  
  
### Para crear una tecla de acceso para un control  
  
1.  Establezca la propiedad `Text` como una cadena que incluya un signo de Y comercial \(&\) antes de la letra que se convertirá en acceso directo.  
  
    ```vb  
    ' Set the letter "P" as an access key.  
    Button1.Text = "&Print"  
  
    ```  
  
    ```csharp  
    // Set the letter "P" as an access key.  
    button1.Text = "&Print";  
  
    ```  
  
    ```cpp  
    // Set the letter "P" as an access key.  
    button1->Text = "&Print";  
    ```  
  
    > [!NOTE]
    >  Si desea incluir un símbolo de unión en una leyenda sin crear una tecla de acceso, incluya dos símbolos de Y comercial \(&&\).  En la leyenda sólo aparecerá un símbolo de Y comercial y no habrá caracteres subrayados.  
  
## Vea también  
 <xref:System.Windows.Forms.Button>   
 [Cómo: Responder a clics de botones en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)   
 [Cómo: Establecer el texto mostrado por un control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)   
 [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
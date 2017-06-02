---
title: "C&#243;mo: Crear teclas de acceso para controles de formularios Windows Forms mediante el Dise&#241;ador | Microsoft Docs"
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
  - "teclas de acceso, agregar a controles de cuadro de diálogo"
  - "Text (propiedad), especificar teclas de acceso para controles"
  - "controles de Windows Forms, teclas de acceso"
ms.assetid: 4c374c4c-4ca9-4a68-ac96-9dc3ab0f518a
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Crear teclas de acceso para controles de formularios Windows Forms mediante el Dise&#241;ador
Una *tecla de acceso* es un carácter subrayado en el texto de un menú, un elemento de menú o la etiqueta de un control tal como un botón.  Permite que el usuario "haga clic" en un botón al presionar la tecla ALT en combinación con la tecla de acceso predefinida.  Por ejemplo, si un botón ejecuta un procedimiento para imprimir un formulario y, por lo tanto, su propiedad `Text` se establece en "Imprimir", y se agrega un símbolo de Y comercial \("&"\) antes de la letra "P", ésta aparecerá subrayada en el texto del botón en tiempo de ejecución.  El usuario puede ejecutar el comando asociado al botón presionando ALT\+P.  No se puede tener una tecla de acceso en un control que no puede recibir el foco.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para crear una tecla de acceso para un control  
  
1.  En la ventana **Propiedades**, establezca la propiedad `Text` como una cadena que incluya un signo de Y comercial \(&\) antes de la letra que será la tecla de acceso.  Por ejemplo, para establecer la letra "I" como tecla de acceso, escriba &Imprimir en la cuadrícula.  
  
## Vea también  
 <xref:System.Windows.Forms.Button>   
 [Cómo: Responder a clics de botones en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)   
 [Cómo: Establecer el texto mostrado por un control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)   
 [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
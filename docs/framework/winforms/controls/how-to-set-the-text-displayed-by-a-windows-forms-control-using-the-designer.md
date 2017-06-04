---
title: "C&#243;mo: Establecer el texto mostrado por un control de formularios Windows Forms mediante el Dise&#241;ador | Microsoft Docs"
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
  - "controles [Windows Forms], establecer título"
  - "Windows Forms, establecer el texto mostrado"
ms.assetid: 9d18e0e0-f17f-4074-837d-e67ceeeaa89d
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Establecer el texto mostrado por un control de formularios Windows Forms mediante el Dise&#241;ador
Los controles de formularios Windows Forms muestran habitualmente algún texto relacionado con la función principal del control.  Por ejemplo, un control <xref:System.Windows.Forms.Button> muestra habitualmente una leyenda que indica qué acción se ejecutará cuando se haga clic en el botón.  Para todos los controles, puede establecer o devolver el texto utilizando la propiedad <xref:System.Windows.Forms.Control.Text%2A>.  Puede cambiar la fuente utilizando la propiedad <xref:System.Windows.Forms.Control.Font%2A>.  
  
### Para establecer el texto y fuente con el diseñador  
  
1.  En la ventana Propiedades, establezca la propiedad <xref:System.Windows.Forms.Control.Text%2A> del control en la cadena adecuada.  
  
     Para crear una tecla de método abreviado subrayada, incluya un signo de Y comercial \(&\) antes de la letra que se convertirá en tecla de método abreviado.  
  
2.  En la ventana Propiedades, haga clic en el botón de puntos suspensivos \(![Captura de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) situado junto a la propiedad <xref:System.Windows.Forms.Control.Font%2A>.  
  
     En el cuadro de diálogo de fuente estándar, seleccione la fuente, el estilo de fuente, el tamaño, los efectos \(como tachado o subrayado\) y el script que desea.  
  
## Vea también  
 [Cómo: Establecer el texto mostrado por un control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)   
 [Utilizar fuentes y texto](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)   
 [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
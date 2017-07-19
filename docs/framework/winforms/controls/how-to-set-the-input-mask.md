---
title: "C&#243;mo: Establecer la m&#225;scara de entrada | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "net.ComponentModel.MaskPropertyEditor"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "MaskedTextBox (control) [Windows Forms]"
ms.assetid: 779b3a12-cd74-4e58-b46e-04983bda5b2c
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Establecer la m&#225;scara de entrada
El control de cuadro de texto enmascarado es un control de cuadro de texto mejorado que admite una sintaxis declarativa para aceptar o rechazar los datos proporcionados por el usuario.  Mediante la propiedad Mask, puede especificar los datos que puede proporcionar el usuario sin escribir una lógica de validación personalizada en la aplicación.  Para obtener más información, vea la sección Comentarios de la clase <xref:System.Windows.Forms.MaskedTextBox>.  
  
## Establecer manualmente la propiedad Mask  
 Si está familiarizado con los caracteres que la propiedad Mask admite, puede escribirla manualmente.  Para obtener un resumen de los caracteres que la propiedad Mask admite, vea la sección Comentarios de la propiedad <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>.  
  
#### Para establecer manualmente la propiedad Mask  
  
1.  En la vista **Diseño**, seleccione <xref:System.Windows.Forms.MaskedTextBox>.  
  
2.  En la ventana **Propiedades**, busque la propiedad <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>.  
  
3.  Escriba la máscara que desee.  Por ejemplo, escriba `###`.  
  
## Usar el cuadro de diálogo Máscara de entrada  
 El cuadro de diálogo Máscara de entrada proporciona algunas máscaras de entrada predefinidas.  Puede cambiar también las máscaras predefinidas o escribir manualmente su propia máscara.  
  
#### Para abrir el cuadro de diálogo Máscara de entrada  
  
1.  En la vista **Diseño**, seleccione <xref:System.Windows.Forms.MaskedTextBox>.  
  
    1.  Haga clic en la etiqueta inteligente para abrir el panel **Tareas de MaskedTextBox**.  
  
    2.  Haga clic en **Establecer máscara**.  
  
     \-O bien\-  
  
    1.  En la ventana **Propiedades**, seleccione la propiedad <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>.  
  
    2.  Haga clic en el botón de puntos suspensivos en la columna del valor de propiedad.  
  
     Aparece el cuadro de diálogo **Máscara de entrada**.  
  
#### Para utilizar el cuadro de diálogo Máscara de entrada  
  
1.  \(Opcional\) Haga clic en una de las máscaras predefinidas de la lista.  
  
2.  \(Opcional\) Modifique la máscara predefinida en el cuadro **Máscara**.  
  
3.  \(Opcional\) Escriba una nueva máscara en el cuadro **Máscara**.  Es decir, no tiene que utilizar una de las máscaras predefinidas.  
  
    > [!NOTE]
    >  En el cuadro Vista previa se muestran los caracteres que el usuario ve en <xref:System.Windows.Forms.MaskedTextBox>.  Estos caracteres son una guía para ayudar al usuario a escribir correctamente los datos.  
  
4.  Active o desactive la casilla **Utilizar ValidatingType**.  La casilla **Utilizar ValidatingType** especifica si un tipo de datos se utiliza para comprobar la entrada de datos del usuario.  Para obtener más información, vea la propiedad <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A>.  
  
5.  Haga clic en **Aceptar**.  
  
     La máscara se escribe en la propiedad **Mask** en la ventana **Propiedades**.  
  
## Vea también  
 [Tutorial: Trabajar con el control MaskedTextBox](../../../../docs/framework/winforms/controls/walkthrough-working-with-the-maskedtextbox-control.md)
---
title: "C&#243;mo: Extraer el icono asociado a un archivo en Windows Forms | Microsoft Docs"
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
  - "mostrar un nombre de archivo y el icono de tipo de archivo en un control ListView [Windows Forms]"
  - "extraer iconos asociados a un tipo de archivo [Windows Forms]"
  - "iconos de extensiones de nombre de archivo [Windows Forms], mostrar en un control ListView"
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Extraer el icono asociado a un archivo en Windows Forms
Muchos archivos tienen iconos incrustados que proporcionan una representación visual del tipo de archivo asociado.  Por ejemplo, los documentos de Microsoft Word contienen un icono que los identifica como documentos de Word.  Al mostrar los archivos en un control de lista o control de tabla, quizás desee mostrar el icono que representa el tipo de archivo al lado de cada nombre de archivo.  Esto es fácil con el método <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A>.  
  
## Ejemplo  
 En el ejemplo de código siguiente se muestra cómo extraer el icono asociado a un archivo y cómo mostrar el nombre de archivo y el icono asociado en un control <xref:System.Windows.Forms.ListView>.  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## Compilar el código  
 Para compilar el ejemplo:  
  
-   Pegue el código anterior en un Windows Form y llame al método `ExtractAssociatedIconExample` desde el constructor del formulario o al método de control del evento <xref:System.Windows.Forms.Form.Load>.  
  
     Necesitará asegurarse de que su formulario importa el espacio de nombres <xref:System.IO>.  
  
## Vea también  
 [Imágenes, mapas de bits y metarchivos](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [ListView \(Control\)](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)
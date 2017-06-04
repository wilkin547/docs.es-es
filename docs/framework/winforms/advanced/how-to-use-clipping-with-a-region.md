---
title: "C&#243;mo: Utilizar el recorte en una regi&#243;n | Microsoft Docs"
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
  - "regiones, recortar"
  - "regiones, restringir la superficie de dibujo"
ms.assetid: 43d121b4-e14c-4901-b25c-2d6c25ba4e29
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Utilizar el recorte en una regi&#243;n
Una de las propiedades de la clase <xref:System.Drawing.Graphics> es la región de recorte.  Todo el dibujo realizado por un determinado objeto <xref:System.Drawing.Graphics> está limitado a la región de recorte de dicho objeto <xref:System.Drawing.Graphics>.  Para establecer la región de recorte hay que llamar al método <xref:System.Drawing.Graphics.SetClip%2A>.  
  
## Ejemplo  
 En el siguiente ejemplo, se traza una ruta formando un solo polígono.  Luego, el código crea una región basada en dicha ruta.  La región se pasa al método <xref:System.Drawing.Graphics.SetClip%2A> de un objeto <xref:System.Drawing.Graphics> y, a continuación, se dibujan dos cadenas.  
  
 En la siguiente ilustración se muestran las cadenas recortadas.  
  
 ![Clip](../../../../docs/framework/winforms/advanced/media/clip1.png "clip1")  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.MiscLegacyTopics#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#41)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Vea también  
 [Regiones de GDI\+](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)   
 [Utilizar regiones](../../../../docs/framework/winforms/advanced/using-regions.md)
---
title: "Utilizar contenedores de gr&#225;ficos | Microsoft Docs"
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
  - "ejemplos [Windows Forms], contenedores de gráficos"
  - "contenedores de gráficos"
  - "gráficos, con contenedores"
ms.assetid: 74632f91-cefa-4f51-ab7c-f9ac91942caf
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Utilizar contenedores de gr&#225;ficos
Los objetos <xref:System.Drawing.Graphics> proporcionan métodos como <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A> y <xref:System.Drawing.Graphics.DrawString%2A> para mostrar imágenes, vectoriales, imágenes de trama y texto.  Los objetos <xref:System.Drawing.Graphics> también poseen varias propiedades que afectan a la calidad y orientación de los elementos dibujados.  Por ejemplo, la propiedad de modo de suavizado determina si el suavizado de contorno se aplicará a las líneas y curvas, mientras que la propiedad de transformación universal afecta a la posición y rotación de los elementos dibujados.  
  
 Los objetos <xref:System.Drawing.Graphics> están asociados a un determinado dispositivo de pantalla.  Cuando se utiliza un objeto <xref:System.Drawing.Graphics> para dibujar en una ventana, dicho objeto<xref:System.Drawing.Graphics> también se asocia a la pantalla en cuestión.  
  
 Los objetos <xref:System.Drawing.Graphics> pueden considerarse como contenedores ya que almacenan un conjunto de propiedades que afectan al dibujo y están vinculados a información específica de dispositivos.  Se puede crear un contenedor secundario con un objeto <xref:System.Drawing.Graphics> al llamar al método <xref:System.Drawing.Graphics.BeginContainer%2A> de dicho objeto <xref:System.Drawing.Graphics>.  
  
## En esta sección  
 [Administrar el estado de un objeto Graphics](../../../../docs/framework/winforms/advanced/managing-the-state-of-a-graphics-object.md)  
 Describe cómo administrar la configuración de calidad, el área de recorte y las transformaciones de un objeto <xref:System.Drawing.Graphics>.  
  
 [Utilizar contenedores de gráficos anidados](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)  
 Muestra cómo utilizar contenedores para controlar el estado del objeto <xref:System.Drawing.Graphics>.
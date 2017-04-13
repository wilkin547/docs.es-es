---
title: "Estructura de la interfaz gr&#225;fica | Microsoft Docs"
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
  - "GDI+, mediante la interfaz administrada"
  - "gráficos, estructura de clases"
ms.assetid: 010a1e46-656b-40a1-8d5d-87aa05ee1243
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Estructura de la interfaz gr&#225;fica
La interfaz de clases administradas en [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] contiene en torno a 60 clases, 50 enumeraciones y 8 estructuras.  La clase <xref:System.Drawing.Graphics> es la base de la funcionalidad de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]; es la clase que realmente dibuja líneas, curvas, figuras, imágenes y texto.  
  
## Clases importantes  
 Muchas clases funcionan junto con la clase <xref:System.Drawing.Graphics>.  Por ejemplo, el método <xref:System.Drawing.Graphics.DrawLine%2A> recibe un objeto <xref:System.Drawing.Pen>, que contiene los atributos \(color, ancho, estilo de guión, etc.\) de la línea que se va a dibujar.  El método <xref:System.Drawing.Graphics.FillRectangle%2A> puede recibir un puntero a un objeto <xref:System.Drawing.Drawing2D.LinearGradientBrush>, que funciona con el objeto <xref:System.Drawing.Graphics> para llenar un rectángulo con cambio de color gradual.  Los objetos <xref:System.Drawing.StringFormat> y <xref:System.Drawing.Font> influyen en la manera en que un objeto <xref:System.Drawing.Graphics> dibuja texto.  Un objeto <xref:System.Drawing.Drawing2D.Matrix> almacena y manipula la transformación de un objeto <xref:System.Drawing.Graphics>, que se utiliza para girar, ajustar la escala y voltear imágenes.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona varias estructuras \(por ejemplo, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Point> y <xref:System.Drawing.Size>\) para organizar los datos de los gráficos.  Además, algunas clases sirven principalmente como tipos de datos estructurados.  Por ejemplo, la clase <xref:System.Drawing.Imaging.BitmapData> es un auxiliar para la clase <xref:System.Drawing.Bitmap>, y la clase <xref:System.Drawing.Drawing2D.PathData> es un auxiliar para la clase <xref:System.Drawing.Drawing2D.GraphicsPath>.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] define varias enumeraciones, que son colecciones de constantes relacionadas.  Por ejemplo, la enumeración <xref:System.Drawing.Drawing2D.LineJoin> contiene los elementos <xref:System.Drawing.Drawing2D.LineJoin>, <xref:System.Drawing.Drawing2D.LineJoin> y <xref:System.Drawing.Drawing2D.LineJoin>, que especifican estilos que pueden utilizarse para combinar dos líneas.  
  
## Vea también  
 [Información general de gráficos](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)   
 [Código administrado de GDI\+](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)   
 [Utilizar clases gráficas administradas](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)
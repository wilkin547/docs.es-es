---
title: "C&#243;mo: Aplanar un trazado curvo en una l&#237;nea | Microsoft Docs"
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
  - "curvas, aplanar"
  - "dibujar, aplanar curvas"
  - "Flatten (método)"
  - "gráficos, aplanar curvas de líneas"
  - "GraphicsPath (objeto)"
  - "rutas de acceso, aplanar"
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Aplanar un trazado curvo en una l&#237;nea
Un objeto <xref:System.Drawing.Drawing2D.GraphicsPath> almacena una secuencia de líneas y curvas spline de Bézier.  Se pueden agregar varios tipos de curvas \(elipses, arcos, curvas spline cardinales\) a un trazado, pero cada curva se convierte en una curva spline de Bézier antes de almacenarse en el trazado.  El aplanamiento de un trazado consiste en convertir cada curva spline de Bézier del trazado en una secuencia de líneas rectas.  En la siguiente ilustración se muestra un trazado antes y después del aplanamiento.  
  
 ![Líneas rectas y curvas](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art32a.png "AboutGdip02\_Art32A")  
  
### Para aplanar un trazado  
  
-   Llame al método <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> de un objeto <xref:System.Drawing.Drawing2D.GraphicsPath>.  El método <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> recibe un argumento de aplanamiento que especifica la distancia máxima entre el trazado aplanado y el trazado original.  
  
## Vea también  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=fullName>   
 [Líneas, curvas y formas](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Crear y dibujar trazados](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
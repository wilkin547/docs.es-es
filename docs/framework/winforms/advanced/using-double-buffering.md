---
title: "Utilizar el doble b&#250;fer | Microsoft Docs"
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
  - "almacenamiento en búfer, doble búfer"
  - "doble búfer"
  - "parpadeo, reducir en formularios Windows Forms"
  - "gráficos, doble búfer"
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Utilizar el doble b&#250;fer
Puede utilizar gráficos de doble búfer para reducir el parpadeo en las aplicaciones que contienen operaciones de dibujo complejas.  .NET Framework contiene soporte integrado para búfer doble o puede administrar y representar manualmente los gráficos.  
  
## En esta sección  
 [Gráficos de doble búfer](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 Introduce el concepto de búfer doble y esquematiza la compatibilidad de .NET Framework.  
  
 [Cómo: Reducir el parpadeo de los gráficos con un búfer doble en formularios y controles](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 Muestra cómo utilizar la compatibilidad del búfer doble predeterminada en .NET Framework.  
  
 [Cómo: Administrar manualmente gráficos almacenados en búfer](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)  
 Muestra cómo administrar el búfer doble en aplicaciones.  
  
 [Cómo: Representar manualmente gráficos almacenados en búfer](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)  
 Muestra cómo representar gráficos de búfer doble.  
  
## Referencia  
 <xref:System.Windows.Forms.Control.SetStyle%2A> ,  
 Método de control que habilita el búfer doble.  
  
 <xref:System.Drawing.BufferedGraphicsContext> ,  
 Proporciona métodos para crear búferes de gráficos.  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 Proporciona el acceso al contexto gráfico almacenado en búfer para un dominio de aplicación.
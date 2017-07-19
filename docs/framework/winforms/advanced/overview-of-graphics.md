---
title: "Informaci&#243;n general de gr&#225;ficos | Microsoft Docs"
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
  - "gráficos, acerca de los gráficos"
  - "gráficos, mediante la interfaz administrada"
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Informaci&#243;n general de gr&#225;ficos
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] es una interfaz de programación de aplicaciones \(API\) que forma el subsistema del sistema operativo Microsoft Windows. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] se encarga de la visualización de información en pantallas e impresoras.  Como sugiere su nombre, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] es la sucesora de [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], la interfaz de dispositivo gráfico incluida en versiones anteriores de Windows.  
  
## Interfaz de clases administradas  
 La API [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] se expone a través de un conjunto de clases implementadas como código administrado.  Este conjunto de clases se denomina *interfaz de clases administradas* a [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  Los espacios de nombres siguientes constituyen la interfaz de clases administradas:  
  
-   <xref:System.Drawing>  
  
-   <xref:System.Drawing.Drawing2D>  
  
-   <xref:System.Drawing.Imaging>  
  
-   <xref:System.Drawing.Text>  
  
-   <xref:System.Drawing.Printing>  
  
 Con una interfaz de dispositivo de gráfico, como [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], puede mostrar información en una pantalla o impresora sin tener que preocuparse por los detalles de un dispositivo de pantalla determinado.  El programador llama a métodos proporcionados por clases [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]. A su vez, estos métodos realizan las llamadas adecuadas a controladores de dispositivos específicos.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] aísla la aplicación del hardware gráfico. Este aislamiento permite al programador crear aplicaciones independientes del dispositivo.  
  
## Vea también  
 [Información general de gráficos](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)
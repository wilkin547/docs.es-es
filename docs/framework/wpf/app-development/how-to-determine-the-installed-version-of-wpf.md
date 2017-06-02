---
title: "C&#243;mo: Determinar la versi&#243;n actualmente instalada de WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "versión, buscar"
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
caps.latest.revision: 3
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 3
---
# C&#243;mo: Determinar la versi&#243;n actualmente instalada de WPF
El número de versión para versión instalada actualmente de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] se encuentra en el **Registro**.  
  
 Para buscar el número de versión:  
  
1.  En el menú **Inicio**, haga clic en **Ejecutar**.  
  
2.  En **Abrir**, escriba **regedit.exe**.  
  
3.  Abra la clave siguiente:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 El número de versión de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se almacena en el valor **Version**.
---
title: "Cómo: Determinar la versión actualmente instalada de WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: version [WPF], finding
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 60f2dd65702a5dfcff4cbafa97e5a48080b8e5be
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-determine-the-installed-version-of-wpf"></a>Cómo: Determinar la versión actualmente instalada de WPF
El número de versión para la versión instalada actualmente de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] se encuentra en la **registro**.  
  
 Para buscar el número de versión:  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**.  
  
2.  En **abiertos**, tipo **regedit.exe**.  
  
3.  Abra la clave siguiente:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] número de versión se almacena en la **versión** valor.

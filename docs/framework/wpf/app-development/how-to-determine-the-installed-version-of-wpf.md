---
title: Filtrar Determinar la versión actualmente instalada de WPF
ms.date: 03/30/2017
helpviewer_keywords:
- version [WPF], finding
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
ms.openlocfilehash: ffbd9a4c7f66dff9c8773dff4259551e20aa963d
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59305681"
---
# <a name="how-to-determine-the-installed-version-of-wpf"></a>Filtrar Determinar la versión actualmente instalada de WPF
El número de versión para la versión instalada actualmente de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] se encuentra en la **registro**.  
  
 Para buscar el número de versión:  
  
1. En el **iniciar** menú, haga clic en **ejecutar**.  
  
2. En **abierto**, tipo **regedit.exe**.  
  
3. Abra la siguiente clave:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] número de versión se almacena en el **versión** valor.

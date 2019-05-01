---
title: Procedimiento Determinar la versión actualmente instalada de WPF
ms.date: 03/30/2017
helpviewer_keywords:
- version [WPF], finding
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
ms.openlocfilehash: ffbd9a4c7f66dff9c8773dff4259551e20aa963d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052461"
---
# <a name="how-to-determine-the-installed-version-of-wpf"></a>Procedimiento Determinar la versión actualmente instalada de WPF
El número de versión para la versión instalada actualmente de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] se encuentra en la **registro**.  
  
 Para buscar el número de versión:  
  
1. En el **iniciar** menú, haga clic en **ejecutar**.  
  
2. En **abierto**, tipo **regedit.exe**.  
  
3. Abra la siguiente clave:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] número de versión se almacena en el **versión** valor.

---
title: 'Cómo: Determinar la versión actualmente instalada de WPF'
ms.date: 03/30/2017
helpviewer_keywords:
- version [WPF], finding
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
ms.openlocfilehash: c59fa0d0a4d94c6e6a2ab72a4cd7a3c066649fb8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545856"
---
# <a name="how-to-determine-the-installed-version-of-wpf"></a>Cómo: Determinar la versión actualmente instalada de WPF
El número de versión para la versión instalada actualmente de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] se encuentra en la **registro**.  
  
 Para buscar el número de versión:  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**.  
  
2.  En **abiertos**, tipo **regedit.exe**.  
  
3.  Abra la clave siguiente:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] número de versión se almacena en la **versión** valor.

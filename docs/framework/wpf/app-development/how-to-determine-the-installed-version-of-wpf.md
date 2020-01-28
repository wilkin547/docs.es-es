---
title: Determinar la versión instalada de WPF
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- version [WPF], finding
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
ms.openlocfilehash: 8fc5c380779891b44b7c4f7f8aeb5ed119d8b768
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735696"
---
# <a name="how-to-determine-the-installed-version-of-wpf"></a>Cómo: Determinar la versión actualmente instalada de WPF
El número de versión de la versión instalada actualmente de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] se encuentra en el **registro**.  
  
 Para buscar el número de versión:  
  
1. En el menú **Inicio** , haga clic en **Ejecutar**.  
  
2. En **abrir**, escriba **regedit. exe**.  
  
3. Abra la clave siguiente:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 El número de versión de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se almacena en el valor **version** .

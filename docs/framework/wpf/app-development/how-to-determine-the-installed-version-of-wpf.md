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
# <a name="how-to-determine-the-installed-version-of-wpf"></a><span data-ttu-id="f1bbb-102">Cómo: Determinar la versión actualmente instalada de WPF</span><span class="sxs-lookup"><span data-stu-id="f1bbb-102">How to: Determine the Installed Version of WPF</span></span>
<span data-ttu-id="f1bbb-103">El número de versión para la versión instalada actualmente de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] se encuentra en la **registro**.</span><span class="sxs-lookup"><span data-stu-id="f1bbb-103">The version number for the current installed version of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] is located in the **Registry**.</span></span>  
  
 <span data-ttu-id="f1bbb-104">Para buscar el número de versión:</span><span class="sxs-lookup"><span data-stu-id="f1bbb-104">To find the version number:</span></span>  
  
1.  <span data-ttu-id="f1bbb-105">En el **iniciar** menú, haga clic en **ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="f1bbb-105">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="f1bbb-106">En **abiertos**, tipo **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="f1bbb-106">In **Open**, type **regedit.exe**.</span></span>  
  
3.  <span data-ttu-id="f1bbb-107">Abra la clave siguiente:</span><span class="sxs-lookup"><span data-stu-id="f1bbb-107">Open the following key:</span></span>  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 <span data-ttu-id="f1bbb-108">El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] número de versión se almacena en la **versión** valor.</span><span class="sxs-lookup"><span data-stu-id="f1bbb-108">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] version number is stored in the **Version** value.</span></span>

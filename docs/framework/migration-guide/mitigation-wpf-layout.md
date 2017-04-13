---
title: "Mitigaci&#243;n: dise&#241;o de WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 805ffd7f-8d1e-427e-a648-601ca8ec37a5
caps.latest.revision: 3
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 3
---
# Mitigaci&#243;n: dise&#241;o de WPF
El diseño de los controles WPF puede cambiar ligeramente.  
  
## Impacto  
 Debido a este cambio:  
  
-   El ancho o alto de los elementos puede aumentar o disminuir un píxel como máximo.  
  
-   La posición de un objeto se puede mover un píxel como máximo.  
  
-   Los elementos centrados pueden estar descentrados como máximo en un píxel en vertical o en horizontal.  
  
 De forma predeterminada, este nuevo diseño solo está habilitado para las aplicaciones que tienen como destino .NET Framework 4.6.  
  
## Mitigación  
 Dado que esta modificación tiende a eliminar el recorte de la parte derecha o inferior de los controles WPF en PPP altos, las aplicaciones destinadas a versiones anteriores de .NET Framework que se ejecutan en .NET Framework 4.6 pueden optar por este nuevo comportamiento agregando la siguiente línea a la sección `<runtime>` del archivo app.config:  
  
```  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false" />  
```  
  
 Las aplicaciones que tienen como destino .NET Framework 4.6 y que desean que los controles WPF efectúen la representación con el algoritmo de diseño anterior pueden hacerlo agregando la siguiente línea a la sección `<runtime>` del archivo app.config:  
  
```  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true" />  
```  
  
## Vea también  
 [Cambios de redestinación](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
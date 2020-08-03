---
title: 'Mitigación: diseño de WPF'
description: Obtenga información sobre cómo mitigar los problemas derivados de un cambio en el diseño de los controles de WPF, como el desplazamiento en un píxel de la posición de un objeto.
ms.date: 03/30/2017
ms.assetid: 805ffd7f-8d1e-427e-a648-601ca8ec37a5
ms.openlocfilehash: e4e4612f7b39eefbf0e76ac86c8eb644c257ba75
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475351"
---
# <a name="mitigation-wpf-layout"></a>Mitigación: Diseño de WPF
El diseño de los controles WPF puede cambiar ligeramente.  
  
## <a name="impact"></a>Impacto  
 Debido a este cambio:  
  
- El ancho o alto de los elementos puede aumentar o disminuir un píxel como máximo.  
  
- La posición de un objeto se puede mover un píxel como máximo.  
  
- Los elementos centrados pueden estar descentrados como máximo en un píxel en vertical o en horizontal.  
  
 De forma predeterminada, este nuevo diseño solo está habilitado para las aplicaciones que tienen como destino .NET Framework 4.6.  
  
## <a name="mitigation"></a>Mitigación  
 Dado que esta modificación tiende a eliminar el recorte de la parte derecha o inferior de los controles WPF en PPP altos, las aplicaciones destinadas a versiones anteriores de .NET Framework que se ejecutan en .NET Framework 4.6 pueden optar por este nuevo comportamiento agregando la siguiente línea a la sección `<runtime>` del archivo app.config:  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false" />  
```  
  
 Las aplicaciones que tienen como destino .NET Framework 4.6 y que desean que los controles WPF efectúen la representación con el algoritmo de diseño anterior pueden hacerlo agregando la siguiente línea a la sección `<runtime>` del archivo app.config:  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true" />  
```  
  
## <a name="see-also"></a>Vea también

- [Compatibilidad de aplicaciones](application-compatibility.md)

---
title: "Mitigación: Asignación de espacio del control de cuadrícula en columnas de estrella | Microsoft Docs"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- WPF retargeting changes
- Grid control retargeting changes
ms.assetid: 707c064d-85e9-4ea1-aefb-e42b60b88679
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 39e8e757a446b30ab18914465853138e1c239e40
ms.openlocfilehash: 75b3c39fa2739b58fdee5c2183d5dfaaeb2f6af5
ms.contentlocale: es-es
ms.lasthandoff: 05/22/2017

---
# <a name="mitigation-grid-control39s-space-allocation-to-star-columns"></a>Mitigación: Asignación de espacio del control de cuadrícula en columnas de estrella

A partir de las aplicaciones que tienen como destino .NET Framework 4.7, WPF reemplaza el algoritmo que el control <xref:System.Windows.Controls.Grid> utiliza para asignar espacio a las columnas \*. 

## <a name="whats-changed"></a>Cambios

El nuevo algoritmo corrige varios errores presentes en el algoritmo antiguo:

1. La asignación total a columnas puede superar el ancho de la cuadrícula. Esto puede ocurrir cuando se asigna espacio a una columna cuya parte proporcional es inferior a su tamaño mínimo. El algoritmo asigna el tamaño mínimo, lo que disminuye el espacio disponible para otras columnas. Si no hay ninguna columna \* que asignar, la asignación total será demasiado grande.

1. La asignación total puede no alcanzar el ancho de la cuadrícula. Este es el doble problema que presenta el n.º 1, que surge cuando se asigna a una columna cuya parte proporcional es superior al tamaño máximo, sin columnas \* para ocupar el margen de demora.

1. Las dos columnas \* pueden recibir ubicaciones no proporcionales a sus pesos. Esta es una versión más ligera de n.º 1/n.º 2, que surge cuando se asigna a las columnas * A, B y C (en ese orden), donde la parte proporcional de B infringe la limitación mínima (o máxima). Como ocurría anteriormente, esto cambia el espacio disponible en la columna C, que obtiene menos (o más) asignación proporcional respecto a A.

1. Las columnas con pesos extremadamente grandes (> 10 ^ 298) se tratan como si tuvieran peso 10 ^ 298. Las diferencias proporcionales entre ellas (y entre columnas con pesos ligeramente más reducidos) no se han respetado.

1. Las columnas con pesos infinitos no se han administrado correctamente. [De hecho, no puede establecer un peso en infinito, pero esta es una restricción artificial. El código de ubicación estaba intentando administrarlo, pero de forma incorrecta].

1. Algunos problemas leves al evitar el desbordamiento, el subdesbordamiento, la pérdida de precisión y problemas de punto flotante similares.

1. Los ajustes del redondeo del diseño son incorrectos en los puntos por pulgada suficientemente elevados.

El nuevo algoritmo genera resultados que cumplen los siguientes criterios:

Un archivo . El ancho real asignado a una columna * nunca es inferior al ancho mínimo ni superior al ancho máximo.

B. Cada columna a la que no se le asigne un ancho mínimo o máximo, se le asigna un ancho proporcional a su peso. Para ser precisos, si dos columnas se declaran con un ancho x e y respectivamente, y si ninguna columna tiene un ancho mínimo o máximo, los anchos reales v y w asignados a las columnas tienen la misma proporción: v / w == x / y.

C. El ancho total asignado a las columnas \* proporcionales es igual al espacio disponible después de la asignación a las columnas restringidas (columnas \*, automáticas y fijas a las que se asignan el ancho mínimo o máximo). Debe ser cero, por ejemplo si la suma de los anchos mínimos supera el ancho disponible de la cuadrícula.

D. Todas estas instrucciones tienen que interpretarse en relación con el diseño "ideal". Cuando se aplica el redondeo del diseño, los anchos reales pueden diferir de los ideales como máximo un píxel.

Se respetó el algoritmo antiguo (A), pero se produjo un error al respetar los demás criterios en los casos descritos anteriormente.

Toda la información que se indica sobre las columnas y los anchos en este tema se aplica también a las filas y las alturas.

## <a name="impact"></a>Impacto

El nuevo algoritmo cambia el ancho real asignado a las columnas \* en una serie de casos:

- Cuando una o más columnas \* tienen un ancho mínimo o máximo que invalida la asignación proporcional para esa columna. (El ancho mínimo puede derivarse de la declaración <xref:System.Windows.FrameworkElement.MinWidth%2A> explícita o de un mínimo implícito obtenido del contenido de la columna. El ancho máximo solo puede definirse de forma explícita, a partir de una declaración <xref:System.Windows.FrameworkElement.MaxWidth%2A>).

- Cuando una o más columnas \* declaran un peso \* extremadamente grande, superior a 10^298.

- Cuando los pesos \* son suficientemente distintos como para detectar una inestabilidad de punto flotante (desbordamiento, subdesbordamiento y pérdida de precisión).

- Cuando se habilita el redondeo del diseño, y el punto por pulgada de visualización efectivo es suficientemente alto.

En los primeros dos casos, los anchos producidos por el nuevo algoritmo pueden ser significativamente distintos de los producidos por el algoritmo antiguo; en el último caso, la diferencia será como máximo de uno o dos píxeles.

## <a name="mitigation"></a>Mitigación

De forma predeterminada, las aplicaciones que tienen como destino versiones de .NET Framework a partir de .NET Framework 4.7 utilizarán el nuevo algoritmo, mientras que las aplicaciones que tienen como destino NET Framework 4.6.2 o versiones anteriores, usarán el algoritmo antiguo.

Para invalidar el valor predeterminado, utilice el siguiente ajuste de configuración:

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=true" /> 
</runtime>
```

El valor 'true' selecciona el algoritmo antiguo y el valor 'false' el nuevo.

## <a name="see-also"></a>Vea también
[Cambios de redestinación en .NET Framework 4.7](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)


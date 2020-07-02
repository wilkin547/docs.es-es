---
ms.openlocfilehash: e0f72d19a884087b1f0f6ebd1b6baea75bc37af4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620716"
---
### <a name="wpf-spawns-a-wisptisexe-process-which-can-freeze-the-mouse"></a>WPF genera un proceso de wisptis.exe que puede inmovilizar el mouse

#### <a name="details"></a>Detalles

En la versión 4.5.2 apareció un problema que hace que se genere <code>wisptis.exe</code> y que puede inmovilizar la entrada del mouse.

#### <a name="suggestion"></a>Sugerencia

Una corrección para este problema está disponible en una versión de servicio de .NET Framework 4.5.2 (paquete acumulativo de revisiones 3026376), o bien mediante la actualización a .NET Framework 4.6.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Major|
|Versión|4.5.2|
|Tipo|Tiempo de ejecución|

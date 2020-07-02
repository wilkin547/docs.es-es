---
ms.openlocfilehash: a44458484ea09c566defeabc9b604bd55d994e93
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617551"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a>Las llamadas a System.Windows.Input.PenContext.Disable en sistemas táctiles pueden iniciar una excepción ArgumentException

#### <a name="details"></a>Detalles

En algunas circunstancias, las llamadas al método interno **System.Windows.Intput.PenContext.Disable** en sistemas táctiles pueden iniciar una excepción `T:System.ArgumentException` no controlada debido a la reentrada.

#### <a name="suggestion"></a>Sugerencia

Este problema se ha corregido en .NET Framework 4.7. Para evitar la excepción, actualice a una versión de .NET Framework a partir de .NET Framework 4.7.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.6.1       |
| Tipo    | Redestinación |

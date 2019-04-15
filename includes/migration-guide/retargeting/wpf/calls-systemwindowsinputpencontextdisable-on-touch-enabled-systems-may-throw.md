---
ms.openlocfilehash: 3cd5052dffcb059c240a310e0b89384f28409264
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234547"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a>Las llamadas a System.Windows.Input.PenContext.Disable en sistemas táctiles pueden iniciar una excepción ArgumentException

|   |   |
|---|---|
|Detalles|En algunas circunstancias, las llamadas al método interno <strong>System.Windows.Intput.PenContext.Disable</strong> en sistemas táctiles pueden iniciar una excepción <code>T:System.ArgumentException</code> no controlada debido a la reentrada.|
|Sugerencia|Este problema se ha corregido en .NET Framework 4.7. Para evitar la excepción, actualice a una versión de .NET Framework a partir de .NET Framework 4.7.|
|Ámbito|Borde|
|Versión|4.6.1|
|Tipo|Redestinación|

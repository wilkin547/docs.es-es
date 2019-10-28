---
ms.openlocfilehash: 6bb8c87af66e744514fb43e628c6423487342ac2
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2019
ms.locfileid: "72887840"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a>Las llamadas a System.Windows.Input.PenContext.Disable en sistemas táctiles pueden iniciar una excepción ArgumentException

|   |   |
|---|---|
|Detalles|En algunas circunstancias, las llamadas al método interno **System.Windows.Intput.PenContext.Disable** en sistemas táctiles pueden iniciar una excepción <code>T:System.ArgumentException</code> no controlada debido a la reentrada.|
|Sugerencia|Este problema se ha corregido en .NET Framework 4.7. Para evitar la excepción, actualice a una versión de .NET Framework a partir de .NET Framework 4.7.|
|Ámbito|Borde|
|Versión|4.6.1|
|Tipo|Redestinación|

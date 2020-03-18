---
ms.openlocfilehash: 09e3f0e168e0dcbe79d8ee7216f2671c67bfb87e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802972"
---
### <a name="wpf-spell-checking-fails-in-unexpected-ways"></a>Se produce un error inesperado en la revisión ortográfica de WPF

|   |   |
|---|---|
|Detalles|Esto incluye una serie de problemas del corrector ortográfico de WPF:<ul><li>En ocasiones, el corrector ortográfico de WPF inicia una excepción <xref:System.Runtime.InteropServices.COMException?displayProperty=name>.</li><li>Se produce un error en el corrector ortográfico de WPF con una excepción <xref:System.UnauthorizedAccessException> cuando las aplicaciones se inician mediante "Ejecutar como otro usuario".</li><li>El corrector ortográfico de WPF identifica incorrectamente errores ortográficos en palabras compuestas, como "Hausnummer" en alemán.</li></ul>|
|Sugerencia|Problema 1: esto se ha solucionado en .NET Framework 4.6.2. Problema 2: el corrector ortográfico de WPF ya no se admite cuando las aplicaciones se inician con la opción "Ejecutar como otro usuario". A partir de .NET Framework 4.6.2, las aplicaciones iniciadas de esta manera ya no se bloquean de forma inesperada; en su lugar, el corrector ortográfico se deshabilita en modo silencioso. Problema 3: esto se ha solucionado en .NET Framework 4.6.2.|
|Ámbito|Borde|
|Versión|4.6.1|
|Tipo|Tiempo de ejecución|

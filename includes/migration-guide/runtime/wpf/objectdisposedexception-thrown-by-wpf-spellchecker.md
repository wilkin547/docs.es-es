---
ms.openlocfilehash: 9d09f598538b9d5ee3f995d6281b8eb4b2668050
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761374"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a>El corrector ortográfico de WPF inicia la excepción ObjectDisposedException

|   |   |
|---|---|
|Detalles|En ocasiones, las aplicaciones de WPF se bloquean durante el cierre de la aplicación y el corrector ortográfico inicia una excepción <xref:System.ObjectDisposedException?displayProperty=name>. Esto se ha corregido en WPF de .NET Framework 4.7 mediante el control correcto de la excepción, lo que garantiza que las aplicaciones ya no se ven afectadas de manera negativa. Debe tenerse en cuenta que se pueden seguir observando primeras excepciones ocasionales en las aplicaciones que se ejecutan con un depurador.|
|Sugerencia|Actualizar a .NET Framework 4.7|
|Ámbito|Borde|
|Versión|4.6.1|
|Tipo|Tiempo de ejecución|


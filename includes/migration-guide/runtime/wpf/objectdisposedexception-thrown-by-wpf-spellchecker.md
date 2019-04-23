---
ms.openlocfilehash: a3f5f512fd17ab2b076f868be24e5c73d8698c49
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774226"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a>El corrector ortográfico de WPF inicia la excepción ObjectDisposedException

|   |   |
|---|---|
|Detalles|En ocasiones, las aplicaciones de WPF se bloquean durante el cierre de la aplicación y el corrector ortográfico inicia una excepción <xref:System.ObjectDisposedException?displayProperty=name>. Esto se ha corregido en WPF de .NET Framework 4.7 mediante el control correcto de la excepción, lo que garantiza que las aplicaciones ya no se ven afectadas de manera negativa. Debe tenerse en cuenta que se pueden seguir observando primeras excepciones ocasionales en las aplicaciones que se ejecutan con un depurador.|
|Sugerencia|Actualizar a .NET Framework 4.7|
|Ámbito|Borde|
|Versión|4.6.1|
|Tipo|Tiempo de ejecución|

---
ms.openlocfilehash: 8dc98b2d9c2c0b5f145ebce48cf8f5e054975c6e
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858575"
---
### <a name="corprfgcroothandles-are-not-being-enumerated-by-profilers"></a>Los generadores de perfiles no enumeran COR_PRF_GC_ROOT_HANDLE

|   |   |
|---|---|
|Detalles|En .NET Framework v4.5.1, el método <code>RootReferences2()</code> de la API de generación de perfiles de manera incorrecta nunca devuelve <code>COR_PRF_GC_ROOT_HANDLE</code> (en su lugar se devuelven como <code>COR_PRF_GC_ROOT_OTHER</code>). Este problema se corrigió a partir de .NET Framework 4.6.|
|Sugerencia|Este problema se ha corregido en .NET Framework 4.6 y se puede solucionar mediante la actualización a esa versión de .NET Framework.|
|Ámbito|Secundaria|
|Versión|4.5.1|
|Tipo|Tiempo de ejecución|


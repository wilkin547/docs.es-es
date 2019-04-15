---
ms.openlocfilehash: 38c35f3f6f2262d06409690d2326d9b982e1ec86
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235967"
---
### <a name="managed-browser-hosting-controls-from-the-net-framework-11-and-20-are-blocked"></a>Los controles de hospedaje de explorador administrado de .NET Framework 1.1 y 2.0 están bloqueados

|   |   |
|---|---|
|Detalles|El hospedaje de estos controles está bloqueado en Internet Explorer.|
|Sugerencia|Internet Explorer no podrá iniciar una aplicación que use controles de hospedaje de explorador administrados. El comportamiento anterior se puede restaurar si se establece el valor EnableIEHosting de la subclave del Registro <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> en <code>1</code> para los sistemas x86 y para los procesos de 32 bits en sistemas x64, y el valor <code>EnableIEHosting</code> de la subclave del Registro <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> en <code>1</code> para los procesos de 64 bits en sistemas x64.|
|Ámbito|Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|

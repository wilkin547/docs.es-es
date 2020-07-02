---
ms.openlocfilehash: 83d3f24680531d1e447f047151a28c98ce0da04b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620671"
---
### <a name="managed-browser-hosting-controls-from-the-net-framework-11-and-20-are-blocked"></a>Los controles de hospedaje de explorador administrado de .NET Framework 1.1 y 2.0 están bloqueados

#### <a name="details"></a>Detalles

El hospedaje de estos controles está bloqueado en Internet Explorer.

#### <a name="suggestion"></a>Sugerencia

Internet Explorer no podrá iniciar una aplicación que use controles de hospedaje de explorador administrados. El comportamiento anterior se puede restaurar si se establece el valor EnableIEHosting de la subclave del Registro <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> en <code>1</code> para los sistemas x86 y para los procesos de 32 bits en sistemas x64, y el valor <code>EnableIEHosting</code> de la subclave del Registro <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> en <code>1</code> para los procesos de 64 bits en sistemas x64.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|

---
ms.openlocfilehash: 4a65e721e5639f12445a9a44f46baa0d26898a88
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615753"
---
### <a name="il-ret-not-allowed-in-a-try-region"></a>No se permite ret de IL en una región try

#### <a name="details"></a>Detalles

A diferencia del compilador Just-In-Time JIT64, RyuJIT (que se usa en .NET Framework 4.6) no admite una instrucción ret de nivel de integridad en una región try. Devolver desde una región try no permite la especificación de ECMA-335 y ningún compilador administrado conocido genera tal IL. Sin embargo, el compilador JIT64 ejecutará dicho IL si se genera mediante la emisión de reflexión.

#### <a name="suggestion"></a>Sugerencia

Si una aplicación genera un IL que incluye un código de operación de ret en una región try, la aplicación puede tener como destino .NET Framework 4.5 para usar el JIT antiguo y evitar esta interrupción. Como alternativa, se puede actualizar el IL generado para que devuelva después de la región try.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.6         |
| Tipo    | Redestinación |

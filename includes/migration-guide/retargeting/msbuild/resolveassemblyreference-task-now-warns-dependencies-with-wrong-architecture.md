---
ms.openlocfilehash: 4d410811095786b33580d25f6c6eab3ac2f27148
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616100"
---
### <a name="resolveassemblyreference-task-now-warns-of-dependencies-with-the-wrong-architecture"></a>La tarea ResolveAssemblyReference ahora advierte sobre dependencias con la arquitectura incorrecta

#### <a name="details"></a>Detalles

La tarea emite una advertencia, MSB3270, que indica que una referencia o cualquiera de sus dependencias no coincide con la arquitectura de la aplicación. Por ejemplo, esto ocurre si una aplicación compilada con la opción `AnyCPU` incluye una referencia a x86. Este tipo de escenario podría producir un error de la aplicación en tiempo de ejecución (en este caso, si la aplicación se implementa como un proceso x64).

#### <a name="suggestion"></a>Sugerencia

Existen dos áreas de impacto:

- Una nueva compilación genera advertencias que no aparecieron al compilar la aplicación con una versión anterior de MSBuild. Sin embargo, dado que la advertencia identifica un posible origen de errores en el runtime, se debe investigar y solucionar.
- Si las advertencias se tratan como errores, la aplicación no se compilará.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.5.1       |
| Tipo    | Redestinación |

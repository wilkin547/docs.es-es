---
ms.openlocfilehash: 09fb7a54fccd5cf37800483c64e2fa6a54681f11
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621431"
---
### <a name="the-net-framework-46-does-not-use-a-45xx-version-when-registering-itself-in-the-registry"></a>En .NET Framework 4.6 no se usa una versión de 4.5.x.x al registrarse a sí mismo en el Registro

#### <a name="details"></a>Detalles

Como se podría esperar, la clave de versión que se establece en el Registro (en <code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>) para .NET Framework 4.6 comienza con "4.6", no con "4.5". Las aplicaciones que dependen de estas claves del Registro para saber qué versiones de .NET Framework están instaladas en un equipo se deben actualizar para entender que 4.6 es una nueva versión posible, y que es compatible con las versiones 4.5.x anteriores.

#### <a name="suggestion"></a>Sugerencia

Actualice las aplicaciones que sondean una instalación de .NET Framework 4.5 examinando las claves del Registro de 4.5 para que también acepten la versión 4.6.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.6|
|Tipo|Tiempo de ejecución|

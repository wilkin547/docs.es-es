---
ms.openlocfilehash: c0551fa086644497c631cd9b6d7058398ff9ccfa
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702299"
---
### <a name="c-locale-maps-to-the-invariant-locale"></a>La configuración regional de “C” se asigna a la configuración regional invariable

.NET Core 2.2 y las versiones anteriores dependen del comportamiento predeterminado de ICU, el cual asigna la configuración regional de “C” a la configuración regional en_US_POSIX. La configuración regional en_US_POSIX tiene un comportamiento de intercalación no deseado, porque no admite comparaciones de cadenas que no distinguen mayúsculas de minúsculas. Algunas distribuciones de Linux establecían la configuración regional de “C” como la configuración regional predeterminada, por lo que los usuarios experimentaban un comportamiento inesperado.

#### <a name="change-description"></a>Descripción del cambio

A partir de .NET Core 3.0, la asignación de la configuración regional de “C” ha cambiado para usar la configuración regional invariable en lugar de en_US_POSIX. La configuración regional de “C” con la asignación invariable también se aplica a Windows para mantener la coherencia.

La asignación de “C” a la referencia cultural en_US_POSIX causaba confusión entre los clientes porque en_US_POSIX no admite operaciones de ordenación y búsqueda de cadenas que no distinguen mayúsculas de minúsculas. Dado que la configuración regional de “C” se usa como configuración regional predeterminada en algunas de las distribuciones de Linux, los clientes experimentaron este comportamiento no deseado en estos sistemas operativos.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="recommended-action"></a>Acción recomendada

Nada más aparte de conocer este cambio. Este cambio solo afecta a las aplicaciones que usan la asignación de configuración regional de “C”.

#### <a name="category"></a>Categoría

Globalización

#### <a name="affected-apis"></a>API afectadas

Este cambio afecta a todas las API de intercalación y de referencia cultural.

<!--

#### Affected APIs

-->

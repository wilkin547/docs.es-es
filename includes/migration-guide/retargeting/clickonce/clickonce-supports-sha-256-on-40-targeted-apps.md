---
ms.openlocfilehash: c967a5b09b5e9ffeee7bff046f0c96469bc7fb02
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615744"
---
### <a name="clickonce-supports-sha-256-on-40-targeted-apps"></a>ClickOnce admite SHA-256 en aplicaciones destinadas a la versión 4.0

#### <a name="details"></a>Detalles

Anteriormente, una aplicación ClickOnce con un certificado firmado con SHA-256 requería la presencia de .NET Framework 4.5 o una versión posterior, incluso si la aplicación se destinaba a la versión 4.0. Ahora, las aplicaciones ClickOnce destinadas a .NET Framework 4.0 se pueden ejecutar en .NET Framework 4.0, incluso si están firmadas con SHA-256.

#### <a name="suggestion"></a>Sugerencia

Este cambio elimina esa dependencia y permite usar certificados de SHA-256 para firmar las aplicaciones ClickOnce que tienen como destino .NET Framework 4 y versiones anteriores.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.6         |
| Tipo    | Redestinación |

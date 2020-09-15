---
ms.openlocfilehash: f980c8029375074889505a8eb7e8a65aaa8d74e4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614773"
---
### <a name="resgen-refuses-to-load-content-from-the-web"></a>Resgen rechaza la carga de contenido desde la web.

#### <a name="details"></a>Detalles

Los archivos .resx pueden contener entradas con formato binario. Si intenta usar resgen para cargar un archivo que se descargó desde una ubicación que no es de confianza, se producirá un error al cargar la entrada de forma predeterminada.

#### <a name="suggestion"></a>Sugerencia

Los usuarios de resgen que necesiten cargar entradas con formato binario desde ubicaciones no confiables pueden eliminar la marca de la web del archivo de entrada o aplicar la opción de exclusión en toda la máquina: [HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft.NETFramework\SDK] &quot;AllowProcessOfUntrustedResourceFiles&quot;=&quot;true&quot;

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.7.2       |
| Tipo    | Redestinación |

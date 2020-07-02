---
ms.openlocfilehash: 416590c7bd959eea011b7e7c5db48f22d349d0f5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615747"
---
### <a name="apps-published-with-clickonce-that-use-a-sha-256-code-signing-certificate-may-fail-on-windows-2003"></a>Puede producirse un error en las aplicaciones publicadas con ClickOnce que usan un certificado de firma de código SHA-256 en Windows 2003

#### <a name="details"></a>Detalles

El archivo ejecutable está firmado con SHA-256. Antes se firmaba con SHA1, independientemente de si el certificado de firma de código era SHA-1 o SHA-256. Esto se aplica a lo siguiente:

- Todas las aplicaciones compiladas con Visual Studio 2012 o versiones posteriores.
- Aplicaciones compiladas con Visual Studio 2010 o versiones anteriores en sistemas con .NET Framework 4.5.
Además, si está presente .NET Framework 4.5 o versiones posteriores, el manifiesto de ClickOnce también está firmado con SHA-256 para certificados SHA-256, independientemente de la versión de .NET Framework con la que se compiló.

#### <a name="suggestion"></a>Sugerencia

El cambio en la firma del ejecutable ClickOnce solo afecta a los sistemas Windows Server 2003; necesitan que KB 938397 esté instalado. El cambio al firmar el manifiesto con SHA-256, incluso cuando una aplicación tiene como destino .NET Framework 4.0 o versiones anteriores, introduce una dependencia de tiempo de ejecución en .NET Framework 4.5 o versiones posteriores.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.5         |
| Tipo    | Redestinación |

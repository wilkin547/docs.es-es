---
ms.openlocfilehash: 51208762cea2a5688c5d43e5d444d4e014e5f0b4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621428"
---
### <a name="x509certificate2tostringboolean-does-not-throw-now-when-net-cannot-handle-the-certificate"></a>X509Certificate2.ToString(Boolean) ahora no se inicia cuando .NET no puede controlar el certificado

#### <a name="details"></a>Detalles

En .NET Framework 4.5.2 y versiones anteriores, este método iniciaba una excepción si se pasaba <code>true</code> para el parámetro detallado y había certificados instalados no admitidos por .NET Framework. Ahora, el método se realizará correctamente y devolverá una cadena válida que omite las partes inaccesibles del certificado.

#### <a name="suggestion"></a>Sugerencia

Cualquier código que dependa de <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> se debe actualizar para esperar que la cadena devuelta pueda excluir algunos datos del certificado (como la clave pública, la clave privada y las extensiones) en algunos casos en los que anteriormente se habría iniciado la API.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.6|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType></li></ul>|

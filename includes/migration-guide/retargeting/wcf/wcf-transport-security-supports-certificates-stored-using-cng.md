---
ms.openlocfilehash: 5c09bee92f679cd7e7a95cd23d5ce0ca9b57170c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614740"
---
### <a name="wcf-transport-security-supports-certificates-stored-using-cng"></a>La seguridad de transporte de WCF admite los certificados almacenados con CNG

#### <a name="details"></a>Detalles

A partir de las aplicaciones destinadas a .NET Framework 4.6.2, la seguridad de transporte de WCF es compatible con los certificados almacenados mediante la biblioteca de criptografía (CNG) de Windows. Esta compatibilidad está limitada a los certificados con una clave pública que tengan un exponente con una longitud no superior a 32 bits. Cuando una aplicación está destinada a .NET Framework 4.6.2, esta característica está activada de manera predeterminada. En versiones anteriores de .NET Framework, el intento de usar certificados X509 con un proveedor de almacenamiento de claves CSG inicia una excepción.

#### <a name="suggestion"></a>Sugerencia

Las aplicaciones que tienen como destino .NET Framework 4.6.1 y versiones anteriores, pero que se ejecutan en .NET Framework 4.6.2, pueden habilitar la compatibilidad para los certificados de CNG si agregan la línea siguiente a la sección `<runtime>` del archivo app.config o web.config:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableCngCertificates=false" />
</runtime>
```

Esto también puede realizarse mediante programación con el siguiente código:

```csharp
private const string DisableCngCertificates = @"Switch.System.ServiceModel.DisableCngCertificate";

AppContext.SetSwitch(disableCngCertificates, false);
```

```vb
Const DisableCngCertificates As String = "Switch.System.ServiceModel.DisableCngCertificates"
AppContext.SetSwitch(disableCngCertificates, False)
```

Tenga en cuenta que, debido a este cambio, cualquier código erróneo de control de excepciones que dependa del intento de iniciar una comunicación segura con un certificado CNG dejará de ejecutarse.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.6.2       |
| Tipo    | Redestinación |

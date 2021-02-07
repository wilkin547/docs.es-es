---
description: 'Más información sobre: clase UnsafeNclNativeMethods'
title: Clase UnsafeNclNativeMethods (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.UnsafeNclNativeMethods
- System.Net.UnsafeNclNativeMethods.NativePKI
- System.Net.UnsafeNclNativeMethods.NativePKI.FindClientCertificates
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: fa1084efddae0ba5cbfc9a949dcd94d2c64f3272
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699498"
---
# <a name="unsafenclnativemethods-class"></a>Clase UnsafeNclNativeMethods

Contiene clases que importan métodos de red nativos no seguros. Esta clase no puede heredarse.

```csharp
internal static class UnsafeNclNativeMethods
```

> [!WARNING]
> Esta clase es interna y no está diseñada para usarse directamente en el código.
>
> Microsoft no admite el uso de esta clase en una aplicación de producción en cualquier circunstancia.

## <a name="nativepki-class"></a>Clase NativePKI

Contiene métodos importados desde crypt32.dll. Estos métodos controlan los certificados cuando se usa el protocolo de transferencia de hipertexto seguro (HTTPS). Esta clase no puede heredarse.

```csharp
internal static class NativePKI
```

## <a name="nativepkifindclientcertificates-method"></a>NativePKI. FindClientCertificates, método

Detecta los certificados de cliente disponibles para enviar al servidor.

```csharp
internal static X509CertificateCollection FindClientCertificates
```

### <a name="return-value"></a>Valor devuelto

<xref:System.Security.Cryptography.X509Certificates.X509CertificateCollection?displayProperty=nameWithType>

Colección de certificados de cliente disponibles.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Net>

**Ensamblado:** Sistema (en System.dll)

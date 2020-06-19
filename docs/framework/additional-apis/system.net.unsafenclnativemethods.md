---
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
ms.openlocfilehash: 46756a0d1d69b4768dbb8dcdd7ab098d3f1849bf
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990495"
---
# <a name="unsafenclnativemethods-class"></a>Clase UnsafeNclNativeMethods

Contiene clases que importan métodos de red nativos no seguros. No se puede heredar esta clase.

```csharp
internal static class UnsafeNclNativeMethods
```

> [!WARNING]
> Esta clase es interna y no está diseñada para usarse directamente en el código.
>
> Microsoft no admite el uso de esta clase en una aplicación de producción en cualquier circunstancia.

## <a name="nativepki-class"></a>Clase NativePKI

Contiene métodos importados desde crypt32.dll. Estos métodos controlan los certificados cuando se usa el protocolo de transferencia de hipertexto seguro (HTTPS). No se puede heredar esta clase.

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

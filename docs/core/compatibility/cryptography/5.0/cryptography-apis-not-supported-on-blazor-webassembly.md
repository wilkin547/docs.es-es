---
title: 'Cambio importante: No se admiten las API de System.Security.Cryptography en Blazor WebAssembly'
description: Obtenga información sobre el cambio importante en .NET 5.0 donde las API de criptografía inician una excepción cuando se ejecutan en un explorador.
ms.date: 09/16/2020
ms.openlocfilehash: ec10fa777e91f641b5582378830536a0cfa8dd72
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760123"
---
# <a name="systemsecuritycryptography-apis-not-supported-on-blazor-webassembly"></a>No se admiten las API de System.Security.Cryptography en Blazor WebAssembly

Las API de <xref:System.Security.Cryptography> inician una excepción <xref:System.PlatformNotSupportedException> en tiempo de ejecución cuando se ejecutan en un explorador.

## <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, la mayoría de las API de <xref:System.Security.Cryptography> no están disponibles para las aplicaciones de Blazor WebAssembly. A partir de .NET 5.0, las aplicaciones de Blazor WebAssembly tienen como destino el área expuesta de la API de .NET 5 completa, sin embargo, no se admiten todas las API de .NET 5 debido a las restricciones de espacio aislado del explorador. En .NET 5.0 y versiones posteriores, las API de <xref:System.Security.Cryptography> no compatibles inician una excepción <xref:System.PlatformNotSupportedException> cuando se ejecutan en WebAssembly.

> [!TIP]
> El [analizador de compatibilidad de plataformas](../../code-analysis/5.0/ca1416-platform-compatibility-analyzer.md) marcará todas las llamadas a las API afectadas al compilar un proyecto que admita la plataforma del explorador. Este analizador se ejecuta de forma predeterminada en las aplicaciones .NET 5.0 y versiones posteriores.

## <a name="reason-for-change"></a>Motivo del cambio

Microsoft no puede enviar OpenSSL como una dependencia en la configuración de Blazor WebAssembly. Se intentó solucionar este error realizando la integración con la API de `SubtleCrypto` del explorador. Sin embargo, requirió importantes cambios en la API que dificultaron su integración.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="recommended-action"></a>Acción recomendada

En este momento no hay ninguna solución alternativa adecuada que sugerir.

## <a name="affected-apis"></a>API afectadas

Todas las API de <xref:System.Security.Cryptography?displayProperty=fullName>, excepto las siguientes:

- `System.Security.Cryptography.RandomNumberGenerator`
- `System.Security.Cryptography.IncrementalHash`
- `System.Security.Cryptography.SHA1`
- `System.Security.Cryptography.SHA256`
- `System.Security.Cryptography.SHA384`
- `System.Security.Cryptography.SHA512`
- `System.Security.Cryptography.SHA1Managed`
- `System.Security.Cryptography.SHA256Managed`
- `System.Security.Cryptography.SHA384Managed`
- `System.Security.Cryptography.SHA512Managed`

<!--

### Affected APIs

- `T:System.Security.Cryptography`

### Category

- ASP.NET Core
- Cryptography

-->

---
title: Cambios importantes en la interoperabilidad
description: Enumera los cambios importantes de la interoperabilidad en .NET Core, .NET 5.0 y versiones posteriores.
ms.date: 06/23/2020
ms.openlocfilehash: a38fb1837e565be33f8ae1119480c8f1ae848ab0
ms.sourcegitcommit: b4a46f6d7ebf44c0035627d00924164bcae2db30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2020
ms.locfileid: "91438048"
---
# <a name="interop-breaking-changes"></a>Cambios importantes en la interoperabilidad

En esta página se documentan los siguientes cambios importantes:

| Cambio importante | Versión introducida |
| - | :-: |
| [Excepción PlatformNotSupportedException al convertir un contenedor RCW en una interfaz de `InterfaceIsIInspectable`](#casting-rcw-to-an-interfaceisiinspectable-interface-throws-platformnotsupportedexception) | 5.0 |
| [Exclusión del sondeo del sufijo A/W en plataformas que no son de Windows](#no-aw-suffix-probing-on-non-windows-platforms) | 5.0 |
| [.NET deja de tener compatibilidad integrada con WinRT](#built-in-support-for-winrt-is-removed-from-net) | 5.0 |

## <a name="net-50"></a>.NET 5.0

[!INCLUDE [casting-rcw-to-inspectable-interface-throws-exception](../../../includes/core-changes/interop/5.0/casting-rcw-to-inspectable-interface-throws-exception.md)]

***

[!INCLUDE [function-suffix-pinvoke](../../../includes/core-changes/interop/5.0/function-suffix-pinvoke.md)]

***

[!INCLUDE [built-in-support-for-winrt-removed](~/includes/core-changes/interop/5.0/built-in-support-for-winrt-removed.md)]

***

---
title: 'Cambio importante: Nombres de parámetro modificados en RC2'
description: Obtenga información sobre el cambio importante de .NET 5 en las bibliotecas básicas de .NET, donde se han cambiado algunos nombres de parámetro de ensamblado de referencia de las versiones preliminares y candidatas para lanzamiento de .NET 5.0.
ms.date: 11/01/2020
ms.openlocfilehash: caca9055bda50174b40d5675c6d34679df61deba
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257198"
---
# <a name="parameter-names-changed-in-rc2"></a>Nombres de parámetro modificados en RC2

Se han cambiado algunos nombres de parámetros de ensamblado de referencia para coincidir con los nombres de parámetro de los ensamblados de implementación.

## <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET 5 Preview y RC, algunos nombres de parámetros de [ensamblado de referencia](../../../../standard/assembly/reference-assemblies.md) son diferentes de sus parámetros correspondientes en el ensamblado de implementación. Esto puede producir problemas al usar argumentos con nombre y reflexión.

En .NET 5 RC2, estos nombres de parámetros no coincidentes se han actualizado en los ensamblados de referencia para que coincidan exactamente con los nombres de parámetro correspondientes en los ensamblados de implementación.

En esta tabla se muestran las API y los nombres de los parámetros que han cambiado.

| API | Nombre del parámetro antiguo | Nombre del parámetro nuevo |
| - | - | - |
| <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)> | `traceOptions` | `traceFlags` |
| <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=nameWithType> | `suffix` | `prefix` |

## <a name="reason-for-change"></a>Motivo del cambio

Los nombres de los parámetros se han cambiado por coherencia y para evitar errores al usar argumentos con nombre y reflexión.

## <a name="version-introduced"></a>Versión introducida

5.0 RC2

## <a name="recommended-action"></a>Acción recomendada

Si se produce un error del compilador debido a un cambio de nombre de un parámetro, actualice el nombre del parámetro en consecuencia.

## <a name="affected-apis"></a>API afectadas

- <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)>
- <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `M:System.Diagnostics.ActivityContext.#ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)`
- `M:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)`

-->

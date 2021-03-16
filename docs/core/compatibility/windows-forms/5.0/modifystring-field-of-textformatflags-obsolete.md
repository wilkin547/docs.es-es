---
title: 'Cambio importante: TextFormatFlags.ModifyString está obsoleto'
description: Obtenga información sobre el cambio importante en .NET 5 donde el campo TextFormatFlags.ModifyString está obsoleto como una advertencia.
ms.date: 11/05/2020
ms.openlocfilehash: 9fe1e04b1ad36070b08af2affdca1e058ec74bb8
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256171"
---
# <a name="textformatflagsmodifystring-is-obsolete"></a>TextFormatFlags.ModifyString está obsoleto

El campo <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> está obsoleto, como advertencia, y es posible que se quite en una versión futura de .NET.

## <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, el campo de enumeración <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> no está marcado como obsoleto. En .NET 5 y versiones posteriores, está marcado como obsoleto como advertencia. Es posible que este campo se quite en una versión futura de .NET.

## <a name="reason-for-change"></a>Motivo del cambio

Pasar una cadena a <xref:System.Windows.Forms.TextRenderer.MeasureText%2A?displayProperty=nameWithType> con <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> modifica la cadena en algunas situaciones. Este comportamiento incumple la promesa de inmutabilidad de la cadena y puede provocar daños graves en el estado del entorno de ejecución de .NET.

## <a name="version-introduced"></a>Versión introducida

.NET 5.0

## <a name="recommended-action"></a>Acción recomendada

Actualice cualquier código que se base en <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType>.

## <a name="affected-apis"></a>API afectadas

- <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=fullName>

<!--

### Affected APIs

- `F:System.Windows.Forms.TextFormatFlags.ModifyString`

### Category

Windows Forms

-->

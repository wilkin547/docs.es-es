---
title: 'Cambio importante: Longitud máxima de texto de NotifyIcon.Text aumentada'
description: Obtenga información sobre el cambio importante de.NET 6 que provoca un aumento de la longitud máxima del texto de la propiedad NotifyIcon.Text.
ms.date: 01/19/2021
ms.openlocfilehash: f87b98dd852ce202689ae9360bee9b6cfbf01794
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102255781"
---
# <a name="notifyicontext-maximum-text-length-increased"></a>Longitud máxima de texto de NotifyIcon.Text aumentada

La longitud máxima de texto permitida para la propiedad <xref:System.Windows.Forms.NotifyIcon.Text?displayProperty=nameWithType> aumentó de 63 a 127.

## <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, la longitud de texto máxima permitida para la propiedad <xref:System.Windows.Forms.NotifyIcon.Text?displayProperty=nameWithType> era de 63 caracteres. A partir de .NET 6, la longitud máxima permitida del texto es de 127 caracteres. En cualquier versión, se produce una excepción <xref:System.ArgumentException> cuando se intenta establecer un valor que supera el límite.

## <a name="reason-for-change"></a>Motivo del cambio

La longitud máxima permitida del texto se ha incrementado en consonancia con la [API subyacente de Windows](/windows/win32/api/shellapi/ns-shellapi-notifyicondataw#nif_showtip-0x00000080). La API de Windows se actualizó en Windows 2000, pero, debido a problemas de compatibilidad, el límite de tamaño de esta propiedad no se ha actualizado en .NET Framework.

## <a name="version-introduced"></a>Versión introducida

.NET 6 (versión preliminar 1)

## <a name="recommended-action"></a>Acción recomendada

Revise el código y modifique las condiciones de protección existentes, si es necesario.

## <a name="affected-apis"></a>API afectadas

<xref:System.Windows.Forms.NotifyIcon.Text?displayProperty=fullName>

<!--

### Affected APIs

- `P:System.Windows.Forms.NotifyIcon.Text`

### Category

Windows Forms

-->

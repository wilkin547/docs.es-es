---
title: 'Cambio importante: Kestrel: Atributos de mensaje de registro modificados'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 6.0 titulado Kestrel: Atributos de mensaje de registro modificados'
author: scottaddie
ms.author: scaddie
ms.date: 02/01/2021
ms.openlocfilehash: 30b03c22a6c85623fec7db14b58b169f887395a0
ms.sourcegitcommit: 4df8e005c074ceb1f978f007b222fe253be2baf3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2021
ms.locfileid: "99551543"
---
# <a name="kestrel-log-message-attributes-changed"></a>Kestrel: Atributos de mensaje de registro modificados

Los mensajes de registro de Kestrel tienen identificadores y nombres asociados. Estos atributos identifican de forma única los distintos tipos de mensajes de registro. Algunos de esos identificadores y nombres se han duplicado incorrectamente. Este problema de duplicación se ha corregido en ASP.NET Core 6.0.

## <a name="version-introduced"></a>Versión introducida

6.0

## <a name="old-behavior"></a>Comportamiento anterior

En la tabla siguiente se muestra el estado de los mensajes de registro afectados antes de ASP.NET Core 6.0.

| Descripción del mensaje                   | Nombre                    | ID |
|---------------------------------------|-------------------------|----|
| Mensajes de registros de conexión cerrada HTTP/2 | `Http2ConnectionClosed` | 36 |
| Mensajes de registros de envío del marco HTTP/2     | `Http2FrameReceived`    | 37 |

## <a name="new-behavior"></a>Comportamiento nuevo

En la tabla siguiente se muestra el estado de los mensajes de registro afectados en ASP.NET Core 6.0.

| Descripción del mensaje                   | Nombre                    | ID |
|---------------------------------------|-------------------------|----|
| Mensajes de registros de conexión cerrada HTTP/2 | `Http2ConnectionClosed` | 48 |
| Mensajes de registros de envío del marco HTTP/2     | `Http2FrameSending`     | 49 |

## <a name="reason-for-change"></a>Motivo del cambio

Los identificadores de registro y los nombres deben ser únicos, por lo que se pueden identificar distintos tipos de mensajes.

## <a name="recommended-action"></a>Acción recomendada

Si tiene un código o una configuración que hace referencia a los identificadores y nombres antiguos, actualice esas referencias para usar los nuevos identificadores y nombres.

<!--

## Category

ASP.NET Core

## Affected APIs

Not detectable via API analysis

-->

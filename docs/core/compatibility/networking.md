---
title: Cambios importantes en las redes
description: Enumera los cambios importantes en las redes en .NET Core.
ms.date: 05/05/2020
ms.openlocfilehash: 568d26bde43ccd6e19fbe2d947f576ef5f99450a
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608464"
---
# <a name="networking-breaking-changes"></a>Cambios importantes en las redes

En esta página se documentan los siguientes cambios importantes:

| Cambio importante | Versión introducida |
| - | - |
| [WinHttpHandler quitado del entorno de ejecución de .NET](#winhttphandler-removed-from-net-runtime) | 5.0 |
| [MulticastOption.Group no acepta un valor NULL](#multicastoptiongroup-doesnt-accept-a-null-value) | 5.0 |
| [El valor predeterminado de HttpRequestMessage.Version ha cambiado a 1.1](#default-value-of-httprequestmessageversion-changed-to-11) | 3.0 |
| [WebClient.CancelAsync no siempre se cancela inmediatamente](#webclientcancelasync-doesnt-always-cancel-immediately) | 2.0 |

## <a name="net-50"></a>.NET 5.0

[!INCLUDE [winhttphandler-removed-from-runtime](../../../includes/core-changes/networking/5.0/winhttphandler-removed-from-runtime.md)]

***

[!INCLUDE [multicastoption-group-doesnt-accept-null](../../../includes/core-changes/networking/5.0/multicastoption-group-doesnt-accept-null.md)]

***

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE[Default value of HttpRequestMessage.Version changed to 1.1](~/includes/core-changes/networking/3.0/httprequestmessage-version-change.md)]

***

## <a name="net-core-20"></a>.NET Core 2.0

[!INCLUDE [behavior-change-webclient-cancelasync](../../../includes/core-changes/networking/2.0/behavior-change-webclient-cancelasync.md)]

***

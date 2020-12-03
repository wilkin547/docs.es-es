---
title: Cambios importantes en las redes
description: Se enumeran los cambios importantes para redes en .NET Core 2.0 y 3.0.
ms.date: 05/05/2020
ms.openlocfilehash: 761c6481888bcb8e91f7b4212355aca067632495
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689217"
---
# <a name="networking-breaking-changes-in-net-core-20-and-30"></a><span data-ttu-id="16731-103">Cambios importantes para redes en .NET Core 2.0 y 3.0</span><span class="sxs-lookup"><span data-stu-id="16731-103">Networking breaking changes in .NET Core 2.0 and 3.0</span></span>

<span data-ttu-id="16731-104">En esta página se documentan los siguientes cambios importantes:</span><span class="sxs-lookup"><span data-stu-id="16731-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="16731-105">Cambio importante</span><span class="sxs-lookup"><span data-stu-id="16731-105">Breaking change</span></span> | <span data-ttu-id="16731-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="16731-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="16731-107">El valor predeterminado de HttpRequestMessage.Version ha cambiado a 1.1</span><span class="sxs-lookup"><span data-stu-id="16731-107">Default value of HttpRequestMessage.Version changed to 1.1</span></span>](#default-value-of-httprequestmessageversion-changed-to-11) | <span data-ttu-id="16731-108">3.0</span><span class="sxs-lookup"><span data-stu-id="16731-108">3.0</span></span> |
| [<span data-ttu-id="16731-109">WebClient.CancelAsync no siempre se cancela inmediatamente</span><span class="sxs-lookup"><span data-stu-id="16731-109">WebClient.CancelAsync doesn't always cancel immediately</span></span>](#webclientcancelasync-doesnt-always-cancel-immediately) | <span data-ttu-id="16731-110">2.0</span><span class="sxs-lookup"><span data-stu-id="16731-110">2.0</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="16731-111">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="16731-111">.NET Core 3.0</span></span>

[!INCLUDE[Default value of HttpRequestMessage.Version changed to 1.1](~/includes/core-changes/networking/3.0/httprequestmessage-version-change.md)]

***

## <a name="net-core-20"></a><span data-ttu-id="16731-112">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="16731-112">.NET Core 2.0</span></span>

[!INCLUDE [behavior-change-webclient-cancelasync](../../../includes/core-changes/networking/2.0/behavior-change-webclient-cancelasync.md)]

***

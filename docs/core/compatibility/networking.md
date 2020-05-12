---
title: Cambios importantes en las redes
description: Enumera los cambios importantes en las redes en .NET Core.
ms.date: 05/05/2020
ms.openlocfilehash: 07e0b2e062ce244cd6312bbe08bcc63db4c74347
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859624"
---
# <a name="networking-breaking-changes"></a><span data-ttu-id="64af9-103">Cambios importantes en las redes</span><span class="sxs-lookup"><span data-stu-id="64af9-103">Networking breaking changes</span></span>

<span data-ttu-id="64af9-104">En esta página se documentan los siguientes cambios importantes:</span><span class="sxs-lookup"><span data-stu-id="64af9-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="64af9-105">Cambio importante</span><span class="sxs-lookup"><span data-stu-id="64af9-105">Breaking change</span></span> | <span data-ttu-id="64af9-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="64af9-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="64af9-107">El valor predeterminado de HttpRequestMessage.Version ha cambiado a 1.1</span><span class="sxs-lookup"><span data-stu-id="64af9-107">Default value of HttpRequestMessage.Version changed to 1.1</span></span>](#default-value-of-httprequestmessageversion-changed-to-11) | <span data-ttu-id="64af9-108">3.0</span><span class="sxs-lookup"><span data-stu-id="64af9-108">3.0</span></span> |
| [<span data-ttu-id="64af9-109">WebClient.CancelAsync no siempre se cancela inmediatamente</span><span class="sxs-lookup"><span data-stu-id="64af9-109">WebClient.CancelAsync doesn't always cancel immediately</span></span>](#webclientcancelasync-doesnt-always-cancel-immediately) | <span data-ttu-id="64af9-110">2.0</span><span class="sxs-lookup"><span data-stu-id="64af9-110">2.0</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="64af9-111">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="64af9-111">.NET Core 3.0</span></span>

[!INCLUDE[Default value of HttpRequestMessage.Version changed to 1.1](~/includes/core-changes/networking/3.0/httprequestmessage-version-change.md)]

***

## <a name="net-core-20"></a><span data-ttu-id="64af9-112">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="64af9-112">.NET Core 2.0</span></span>

[!INCLUDE [behavior-change-webclient-cancelasync](../../../includes/core-changes/networking/2.0/behavior-change-webclient-cancelasync.md)]

***

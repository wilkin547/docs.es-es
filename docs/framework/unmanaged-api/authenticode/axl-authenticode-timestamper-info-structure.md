---
title: AXL_AUTHENTICODE_TIMESTAMPER_INFO (Estructura)
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
ms.openlocfilehash: b6852519da6cf4e12669aa2efa24862053adbc03
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674247"
---
# <a name="axl_authenticode_timestamper_info-structure"></a><span data-ttu-id="5d62f-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="5d62f-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>

<span data-ttu-id="5d62f-103">Define la información del autor de la marca de hora de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="5d62f-103">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d62f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d62f-104">Syntax</span></span>  
  
```cpp  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="5d62f-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="5d62f-105">Members</span></span>  
  
|<span data-ttu-id="5d62f-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="5d62f-106">Member</span></span>|<span data-ttu-id="5d62f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d62f-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="5d62f-108">Tamaño de esta estructura.</span><span class="sxs-lookup"><span data-stu-id="5d62f-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="5d62f-109">Código de error.</span><span class="sxs-lookup"><span data-stu-id="5d62f-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="5d62f-110">Algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="5d62f-110">The hash algorithm.</span></span>|  
|`ftTimestamp`|<span data-ttu-id="5d62f-111">Hora de la marca de hora.</span><span class="sxs-lookup"><span data-stu-id="5d62f-111">The time of the time stamp.</span></span>|  
|`pChainContext`|<span data-ttu-id="5d62f-112">Contexto de cadena del autor de la marca de hora.</span><span class="sxs-lookup"><span data-stu-id="5d62f-112">The time stamper’s chain context.</span></span>  <span data-ttu-id="5d62f-113">Vea la estructura [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) .</span><span class="sxs-lookup"><span data-stu-id="5d62f-113">See the [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5d62f-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5d62f-114">See also</span></span>

- [<span data-ttu-id="5d62f-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="5d62f-115">Authenticode</span></span>](index.md)

---
title: AXL_AUTHENTICODE_TIMESTAMPER_INFO (Estructura)
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
ms.openlocfilehash: 036397928703aea6199a59ae9c1e66153c30ec7b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132503"
---
# <a name="axl_authenticode_timestamper_info-structure"></a><span data-ttu-id="e1d36-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="e1d36-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>
<span data-ttu-id="e1d36-103">Define la información del autor de la marca de hora de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="e1d36-103">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1d36-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e1d36-104">Syntax</span></span>  
  
```cpp  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="e1d36-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="e1d36-105">Members</span></span>  
  
|<span data-ttu-id="e1d36-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="e1d36-106">Member</span></span>|<span data-ttu-id="e1d36-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1d36-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="e1d36-108">Tamaño de esta estructura.</span><span class="sxs-lookup"><span data-stu-id="e1d36-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="e1d36-109">Código de error.</span><span class="sxs-lookup"><span data-stu-id="e1d36-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="e1d36-110">Algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="e1d36-110">The hash algorithm.</span></span>|  
|`ftTimestamp`|<span data-ttu-id="e1d36-111">Hora de la marca de hora.</span><span class="sxs-lookup"><span data-stu-id="e1d36-111">The time of the time stamp.</span></span>|  
|`pChainContext`|<span data-ttu-id="e1d36-112">Contexto de cadena del autor de la marca de hora.</span><span class="sxs-lookup"><span data-stu-id="e1d36-112">The time stamper’s chain context.</span></span>  <span data-ttu-id="e1d36-113">Vea la estructura [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) .</span><span class="sxs-lookup"><span data-stu-id="e1d36-113">See the [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e1d36-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1d36-114">See also</span></span>

- [<span data-ttu-id="e1d36-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="e1d36-115">Authenticode</span></span>](index.md)

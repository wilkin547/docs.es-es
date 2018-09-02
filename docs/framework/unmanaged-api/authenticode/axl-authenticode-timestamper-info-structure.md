---
title: AXL_AUTHENTICODE_TIMESTAMPER_INFO (Estructura)
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d7f4fff4f2c2b3dd04625f4cf50b8b19a0ef6f39
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43415902"
---
# <a name="axlauthenticodetimestamperinfo-structure"></a><span data-ttu-id="3b2d7-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="3b2d7-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>
<span data-ttu-id="3b2d7-103">Define la información del autor de la marca de hora de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="3b2d7-103">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b2d7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b2d7-104">Syntax</span></span>  
  
```  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="3b2d7-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="3b2d7-105">Members</span></span>  
  
|<span data-ttu-id="3b2d7-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="3b2d7-106">Member</span></span>|<span data-ttu-id="3b2d7-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b2d7-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="3b2d7-108">Tamaño de esta estructura.</span><span class="sxs-lookup"><span data-stu-id="3b2d7-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="3b2d7-109">Código de error.</span><span class="sxs-lookup"><span data-stu-id="3b2d7-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="3b2d7-110">Algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="3b2d7-110">The hash algorithm.</span></span>|  
|`ftTimestamp`|<span data-ttu-id="3b2d7-111">Hora de la marca de hora.</span><span class="sxs-lookup"><span data-stu-id="3b2d7-111">The time of the time stamp.</span></span>|  
|`pChainContext`|<span data-ttu-id="3b2d7-112">Contexto de cadena del autor de la marca de hora.</span><span class="sxs-lookup"><span data-stu-id="3b2d7-112">The time stamper’s chain context.</span></span>  <span data-ttu-id="3b2d7-113">Consulte la [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) estructura.</span><span class="sxs-lookup"><span data-stu-id="3b2d7-113">See the [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3b2d7-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b2d7-114">See Also</span></span>  
 [<span data-ttu-id="3b2d7-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="3b2d7-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)

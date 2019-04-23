---
title: AXL_AUTHENTICODE_TIMESTAMPER_INFO (Estructura)
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d82ed3299f967457fe967d096a238da6143751a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59219166"
---
# <a name="axlauthenticodetimestamperinfo-structure"></a><span data-ttu-id="2d54c-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="2d54c-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>
<span data-ttu-id="2d54c-103">Define la información del autor de la marca de hora de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="2d54c-103">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d54c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d54c-104">Syntax</span></span>  
  
```  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="2d54c-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="2d54c-105">Members</span></span>  
  
|<span data-ttu-id="2d54c-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="2d54c-106">Member</span></span>|<span data-ttu-id="2d54c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d54c-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="2d54c-108">Tamaño de esta estructura.</span><span class="sxs-lookup"><span data-stu-id="2d54c-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="2d54c-109">Código de error.</span><span class="sxs-lookup"><span data-stu-id="2d54c-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="2d54c-110">Algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="2d54c-110">The hash algorithm.</span></span>|  
|`ftTimestamp`|<span data-ttu-id="2d54c-111">Hora de la marca de hora.</span><span class="sxs-lookup"><span data-stu-id="2d54c-111">The time of the time stamp.</span></span>|  
|`pChainContext`|<span data-ttu-id="2d54c-112">Contexto de cadena del autor de la marca de hora.</span><span class="sxs-lookup"><span data-stu-id="2d54c-112">The time stamper’s chain context.</span></span>  <span data-ttu-id="2d54c-113">Consulte la [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) estructura.</span><span class="sxs-lookup"><span data-stu-id="2d54c-113">See the [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2d54c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d54c-114">See also</span></span>

- [<span data-ttu-id="2d54c-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="2d54c-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)

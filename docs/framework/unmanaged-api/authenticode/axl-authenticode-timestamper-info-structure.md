---
description: 'Más información acerca de: estructura de AXL_AUTHENTICODE_TIMESTAMPER_INFO'
title: AXL_AUTHENTICODE_TIMESTAMPER_INFO (Estructura)
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
ms.openlocfilehash: 35e30241c3c3b5747e247c57183e28e726c0cae3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747418"
---
# <a name="axl_authenticode_timestamper_info-structure"></a><span data-ttu-id="f30d0-103">AXL_AUTHENTICODE_TIMESTAMPER_INFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="f30d0-103">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>

<span data-ttu-id="f30d0-104">Define la información del autor de la marca de hora de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="f30d0-104">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f30d0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f30d0-105">Syntax</span></span>  
  
```cpp  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="f30d0-106">Members</span><span class="sxs-lookup"><span data-stu-id="f30d0-106">Members</span></span>  
  
|<span data-ttu-id="f30d0-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="f30d0-107">Member</span></span>|<span data-ttu-id="f30d0-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="f30d0-108">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="f30d0-109">Tamaño de esta estructura.</span><span class="sxs-lookup"><span data-stu-id="f30d0-109">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="f30d0-110">Código de error.</span><span class="sxs-lookup"><span data-stu-id="f30d0-110">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="f30d0-111">Algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="f30d0-111">The hash algorithm.</span></span>|  
|`ftTimestamp`|<span data-ttu-id="f30d0-112">Hora de la marca de hora.</span><span class="sxs-lookup"><span data-stu-id="f30d0-112">The time of the time stamp.</span></span>|  
|`pChainContext`|<span data-ttu-id="f30d0-113">Contexto de cadena del autor de la marca de hora.</span><span class="sxs-lookup"><span data-stu-id="f30d0-113">The time stamper’s chain context.</span></span>  <span data-ttu-id="f30d0-114">Vea la estructura [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) .</span><span class="sxs-lookup"><span data-stu-id="f30d0-114">See the [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f30d0-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f30d0-115">See also</span></span>

- [<span data-ttu-id="f30d0-116">Authenticode</span><span class="sxs-lookup"><span data-stu-id="f30d0-116">Authenticode</span></span>](index.md)

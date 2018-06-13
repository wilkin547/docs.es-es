---
title: AXL_AUTHENTICODE_TIMESTAMPER_INFO (Estructura)
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c89845008307e4cfb00d0f9b9a168a43ba5378c0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402368"
---
# <a name="axlauthenticodetimestamperinfo-structure"></a><span data-ttu-id="098c1-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="098c1-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>
<span data-ttu-id="098c1-103">Define la información del autor de la marca de hora de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="098c1-103">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="098c1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="098c1-104">Syntax</span></span>  
  
```  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="098c1-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="098c1-105">Members</span></span>  
  
|<span data-ttu-id="098c1-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="098c1-106">Member</span></span>|<span data-ttu-id="098c1-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="098c1-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="098c1-108">Tamaño de esta estructura.</span><span class="sxs-lookup"><span data-stu-id="098c1-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="098c1-109">Código de error.</span><span class="sxs-lookup"><span data-stu-id="098c1-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="098c1-110">Algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="098c1-110">The hash algorithm.</span></span>|  
|`ftTimestamp`|<span data-ttu-id="098c1-111">Hora de la marca de hora.</span><span class="sxs-lookup"><span data-stu-id="098c1-111">The time of the time stamp.</span></span>|  
|`pChainContext`|<span data-ttu-id="098c1-112">Contexto de cadena del autor de la marca de hora.</span><span class="sxs-lookup"><span data-stu-id="098c1-112">The time stamper’s chain context.</span></span>  <span data-ttu-id="098c1-113">Consulte la [CERT_CONTEXT](http://msdn.microsoft.com/library/windows/desktop/aa377189.aspx) estructura.</span><span class="sxs-lookup"><span data-stu-id="098c1-113">See the [CERT_CONTEXT](http://msdn.microsoft.com/library/windows/desktop/aa377189.aspx) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="098c1-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="098c1-114">See Also</span></span>  
 [<span data-ttu-id="098c1-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="098c1-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)

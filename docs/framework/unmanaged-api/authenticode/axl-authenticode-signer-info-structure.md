---
title: AXL_AUTHENTICODE_SIGNER_INFO (Estructura)
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c69be0de98e2996176e7360bae0bb0736c1a797
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038439"
---
# <a name="axl_authenticode_signer_info-structure"></a><span data-ttu-id="81724-102">AXL_AUTHENTICODE_SIGNER_INFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="81724-102">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>
<span data-ttu-id="81724-103">Define la información del firmante de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="81724-103">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81724-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="81724-104">Syntax</span></span>  
  
```cpp  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    LPCWSTR pwszHash  
    LPCWSTR pwszDescription;  
    LPCWSTR pwszDescriptionUrl;  
    PCCERT_CHAIN_CONTEXT pChainContext  
} AXL_AUTHENTICODE_SIGNER_INFO, * PAXL_AUTHENTICODE_SIGNER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="81724-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="81724-105">Members</span></span>  
  
|<span data-ttu-id="81724-106">Member</span><span class="sxs-lookup"><span data-stu-id="81724-106">Member</span></span>|<span data-ttu-id="81724-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="81724-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="81724-108">Tamaño de esta estructura.</span><span class="sxs-lookup"><span data-stu-id="81724-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="81724-109">Código de error.</span><span class="sxs-lookup"><span data-stu-id="81724-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="81724-110">Algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="81724-110">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="81724-111">Hash.</span><span class="sxs-lookup"><span data-stu-id="81724-111">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="81724-112">Description.</span><span class="sxs-lookup"><span data-stu-id="81724-112">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="81724-113">Dirección URL de la descripción.</span><span class="sxs-lookup"><span data-stu-id="81724-113">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="81724-114">Contexto de cadena del firmante.</span><span class="sxs-lookup"><span data-stu-id="81724-114">The chain context of the signer.</span></span> <span data-ttu-id="81724-115">Vea la estructura [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) .</span><span class="sxs-lookup"><span data-stu-id="81724-115">See the [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="81724-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="81724-116">See also</span></span>

- [<span data-ttu-id="81724-117">Authenticode</span><span class="sxs-lookup"><span data-stu-id="81724-117">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)

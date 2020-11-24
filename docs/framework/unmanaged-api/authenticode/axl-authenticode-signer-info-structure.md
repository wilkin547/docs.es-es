---
title: AXL_AUTHENTICODE_SIGNER_INFO (Estructura)
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
ms.openlocfilehash: 1bb6df4aa82f8dfc367083732af2065aba9d07b1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679993"
---
# <a name="axl_authenticode_signer_info-structure"></a><span data-ttu-id="a72fa-102">AXL_AUTHENTICODE_SIGNER_INFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="a72fa-102">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>

<span data-ttu-id="a72fa-103">Define la información del firmante de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="a72fa-103">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a72fa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a72fa-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="a72fa-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="a72fa-105">Members</span></span>  
  
|<span data-ttu-id="a72fa-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="a72fa-106">Member</span></span>|<span data-ttu-id="a72fa-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a72fa-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="a72fa-108">Tamaño de esta estructura.</span><span class="sxs-lookup"><span data-stu-id="a72fa-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="a72fa-109">Código de error.</span><span class="sxs-lookup"><span data-stu-id="a72fa-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="a72fa-110">Algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="a72fa-110">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="a72fa-111">El hash.</span><span class="sxs-lookup"><span data-stu-id="a72fa-111">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="a72fa-112">La descripción.</span><span class="sxs-lookup"><span data-stu-id="a72fa-112">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="a72fa-113">Dirección URL de la descripción.</span><span class="sxs-lookup"><span data-stu-id="a72fa-113">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="a72fa-114">Contexto de cadena del firmante.</span><span class="sxs-lookup"><span data-stu-id="a72fa-114">The chain context of the signer.</span></span> <span data-ttu-id="a72fa-115">Vea la estructura [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) .</span><span class="sxs-lookup"><span data-stu-id="a72fa-115">See the [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a72fa-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a72fa-116">See also</span></span>

- [<span data-ttu-id="a72fa-117">Authenticode</span><span class="sxs-lookup"><span data-stu-id="a72fa-117">Authenticode</span></span>](index.md)

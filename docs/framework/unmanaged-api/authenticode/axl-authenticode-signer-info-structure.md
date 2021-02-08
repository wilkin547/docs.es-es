---
description: 'Más información acerca de: estructura de AXL_AUTHENTICODE_SIGNER_INFO'
title: AXL_AUTHENTICODE_SIGNER_INFO (Estructura)
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
ms.openlocfilehash: 940652cf184e26f141df806b060c391333d1bb95
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781966"
---
# <a name="axl_authenticode_signer_info-structure"></a><span data-ttu-id="8a180-103">AXL_AUTHENTICODE_SIGNER_INFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="8a180-103">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>

<span data-ttu-id="8a180-104">Define la información del firmante de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="8a180-104">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a180-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a180-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="8a180-106">Members</span><span class="sxs-lookup"><span data-stu-id="8a180-106">Members</span></span>  
  
|<span data-ttu-id="8a180-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="8a180-107">Member</span></span>|<span data-ttu-id="8a180-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a180-108">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="8a180-109">Tamaño de esta estructura.</span><span class="sxs-lookup"><span data-stu-id="8a180-109">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="8a180-110">Código de error.</span><span class="sxs-lookup"><span data-stu-id="8a180-110">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="8a180-111">Algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="8a180-111">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="8a180-112">El hash.</span><span class="sxs-lookup"><span data-stu-id="8a180-112">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="8a180-113">La descripción.</span><span class="sxs-lookup"><span data-stu-id="8a180-113">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="8a180-114">Dirección URL de la descripción.</span><span class="sxs-lookup"><span data-stu-id="8a180-114">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="8a180-115">Contexto de cadena del firmante.</span><span class="sxs-lookup"><span data-stu-id="8a180-115">The chain context of the signer.</span></span> <span data-ttu-id="8a180-116">Vea la estructura [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) .</span><span class="sxs-lookup"><span data-stu-id="8a180-116">See the [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8a180-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a180-117">See also</span></span>

- [<span data-ttu-id="8a180-118">Authenticode</span><span class="sxs-lookup"><span data-stu-id="8a180-118">Authenticode</span></span>](index.md)

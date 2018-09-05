---
title: AXL_AUTHENTICODE_SIGNER_INFO (Estructura)
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b9f54c7c57d122ac1214b9f31cc4e1d1cddd71c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43670537"
---
# <a name="axlauthenticodesignerinfo-structure"></a><span data-ttu-id="44cd8-102">AXL_AUTHENTICODE_SIGNER_INFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="44cd8-102">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>
<span data-ttu-id="44cd8-103">Define la información del firmante de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="44cd8-103">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44cd8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="44cd8-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="44cd8-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="44cd8-105">Members</span></span>  
  
|<span data-ttu-id="44cd8-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="44cd8-106">Member</span></span>|<span data-ttu-id="44cd8-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="44cd8-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="44cd8-108">Tamaño de esta estructura.</span><span class="sxs-lookup"><span data-stu-id="44cd8-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="44cd8-109">Código de error.</span><span class="sxs-lookup"><span data-stu-id="44cd8-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="44cd8-110">Algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="44cd8-110">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="44cd8-111">Hash.</span><span class="sxs-lookup"><span data-stu-id="44cd8-111">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="44cd8-112">Description.</span><span class="sxs-lookup"><span data-stu-id="44cd8-112">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="44cd8-113">Dirección URL de la descripción.</span><span class="sxs-lookup"><span data-stu-id="44cd8-113">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="44cd8-114">Contexto de cadena del firmante.</span><span class="sxs-lookup"><span data-stu-id="44cd8-114">The chain context of the signer.</span></span> <span data-ttu-id="44cd8-115">Consulte la [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) estructura.</span><span class="sxs-lookup"><span data-stu-id="44cd8-115">See the [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44cd8-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="44cd8-116">See Also</span></span>  
 [<span data-ttu-id="44cd8-117">Authenticode</span><span class="sxs-lookup"><span data-stu-id="44cd8-117">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)

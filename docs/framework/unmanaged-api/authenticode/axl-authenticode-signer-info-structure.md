---
title: AXL_AUTHENTICODE_SIGNER_INFO (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c53ca8073adda5cba497e9f45404024435cc161f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="axlauthenticodesignerinfo-structure"></a><span data-ttu-id="5d918-102">AXL_AUTHENTICODE_SIGNER_INFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="5d918-102">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>
<span data-ttu-id="5d918-103">Define la información del firmante de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="5d918-103">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d918-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d918-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="5d918-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="5d918-105">Members</span></span>  
  
|<span data-ttu-id="5d918-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="5d918-106">Member</span></span>|<span data-ttu-id="5d918-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d918-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="5d918-108">Tamaño de esta estructura.</span><span class="sxs-lookup"><span data-stu-id="5d918-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="5d918-109">Código de error.</span><span class="sxs-lookup"><span data-stu-id="5d918-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="5d918-110">Algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="5d918-110">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="5d918-111">Hash.</span><span class="sxs-lookup"><span data-stu-id="5d918-111">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="5d918-112">Description.</span><span class="sxs-lookup"><span data-stu-id="5d918-112">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="5d918-113">Dirección URL de la descripción.</span><span class="sxs-lookup"><span data-stu-id="5d918-113">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="5d918-114">Contexto de cadena del firmante.</span><span class="sxs-lookup"><span data-stu-id="5d918-114">The chain context of the signer.</span></span> <span data-ttu-id="5d918-115">Consulte la [CERT_CONTEXT](http://msdn.microsoft.com/library/windows/desktop/aa377189.aspx) estructura.</span><span class="sxs-lookup"><span data-stu-id="5d918-115">See the [CERT_CONTEXT](http://msdn.microsoft.com/library/windows/desktop/aa377189.aspx) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5d918-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d918-116">See Also</span></span>  
 [<span data-ttu-id="5d918-117">Authenticode</span><span class="sxs-lookup"><span data-stu-id="5d918-117">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)

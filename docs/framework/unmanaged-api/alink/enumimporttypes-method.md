---
title: "EnumImportTypes (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- EnumImportTypes
- IALink.EnumImportTypes
api_location: alink.dll
api_type: COM
f1_keywords: EnumImportTypes
helpviewer_keywords: EnumImportTypes method
ms.assetid: 83a0e4e7-ec06-40cb-9b63-700b9695bb04
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 08644816d3fa11ade5a8ebee1573e8f66d526101
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="enumimporttypes-method"></a><span data-ttu-id="9335d-102">EnumImportTypes (Método)</span><span class="sxs-lookup"><span data-stu-id="9335d-102">EnumImportTypes Method</span></span>
<span data-ttu-id="9335d-103">Enumera cada tipo en cada ámbito.</span><span class="sxs-lookup"><span data-stu-id="9335d-103">Enumerates each type in each scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9335d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9335d-104">Syntax</span></span>  
  
```  
HRESULT EnumImportTypes(  
    HALINKENUM   hEnum,  
    DWORD        dwMax,  
    mdTypeDef    aTypeDefs[],  
    DWORD*       pdwCount  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9335d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9335d-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="9335d-106">Identificador del enumerador.</span><span class="sxs-lookup"><span data-stu-id="9335d-106">Handle for enumerator.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="9335d-107">Número máximo de tipos que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="9335d-107">Maximum number of types to retrieve.</span></span>  
  
 `aTypeDefs`  
 <span data-ttu-id="9335d-108">Recibe los símbolos (tokens), no debe superar de tipo `dwMax`.</span><span class="sxs-lookup"><span data-stu-id="9335d-108">Recieves type tokens, not to exceed `dwMax`.</span></span>  
  
 `pdwCount`  
 <span data-ttu-id="9335d-109">Recibe el número real de tipo en `aTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="9335d-109">Receives actual number of type in `aTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9335d-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9335d-110">Return Value</span></span>  
 <span data-ttu-id="9335d-111">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="9335d-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9335d-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9335d-112">Requirements</span></span>  
 <span data-ttu-id="9335d-113">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="9335d-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9335d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="9335d-114">See Also</span></span>  
 [<span data-ttu-id="9335d-115">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9335d-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="9335d-116">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9335d-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="9335d-117">API de ALink</span><span class="sxs-lookup"><span data-stu-id="9335d-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

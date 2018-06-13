---
title: EnumImportTypes (Método)
ms.date: 03/30/2017
api_name:
- EnumImportTypes
- IALink.EnumImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumImportTypes
helpviewer_keywords:
- EnumImportTypes method
ms.assetid: 83a0e4e7-ec06-40cb-9b63-700b9695bb04
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 90319886dfe149a3d2d76451c1a8526299cf5b89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401653"
---
# <a name="enumimporttypes-method"></a><span data-ttu-id="612a0-102">EnumImportTypes (Método)</span><span class="sxs-lookup"><span data-stu-id="612a0-102">EnumImportTypes Method</span></span>
<span data-ttu-id="612a0-103">Enumera cada tipo en cada ámbito.</span><span class="sxs-lookup"><span data-stu-id="612a0-103">Enumerates each type in each scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="612a0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="612a0-104">Syntax</span></span>  
  
```  
HRESULT EnumImportTypes(  
    HALINKENUM   hEnum,  
    DWORD        dwMax,  
    mdTypeDef    aTypeDefs[],  
    DWORD*       pdwCount  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="612a0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="612a0-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="612a0-106">Identificador del enumerador.</span><span class="sxs-lookup"><span data-stu-id="612a0-106">Handle for enumerator.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="612a0-107">Número máximo de tipos que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="612a0-107">Maximum number of types to retrieve.</span></span>  
  
 `aTypeDefs`  
 <span data-ttu-id="612a0-108">Recibe los símbolos (tokens), no debe superar de tipo `dwMax`.</span><span class="sxs-lookup"><span data-stu-id="612a0-108">Recieves type tokens, not to exceed `dwMax`.</span></span>  
  
 `pdwCount`  
 <span data-ttu-id="612a0-109">Recibe el número real de tipo en `aTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="612a0-109">Receives actual number of type in `aTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="612a0-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="612a0-110">Return Value</span></span>  
 <span data-ttu-id="612a0-111">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="612a0-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="612a0-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="612a0-112">Requirements</span></span>  
 <span data-ttu-id="612a0-113">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="612a0-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="612a0-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="612a0-114">See Also</span></span>  
 [<span data-ttu-id="612a0-115">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="612a0-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="612a0-116">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="612a0-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="612a0-117">API de ALink</span><span class="sxs-lookup"><span data-stu-id="612a0-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

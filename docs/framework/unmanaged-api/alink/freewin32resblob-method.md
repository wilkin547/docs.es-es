---
title: FreeWin32ResBlob (Método)
ms.date: 03/30/2017
api_name:
- IALink.FreeWin32ResBlob
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- FreeWin32ResBlob
helpviewer_keywords:
- FreeWin32ResBlob method
ms.assetid: d941102b-2679-4c49-b15e-c0fc9c53e11f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e52984e12f22486212f0a2ec02d452a77242400e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491833"
---
# <a name="freewin32resblob-method"></a><span data-ttu-id="3387e-102">FreeWin32ResBlob (Método)</span><span class="sxs-lookup"><span data-stu-id="3387e-102">FreeWin32ResBlob Method</span></span>
<span data-ttu-id="3387e-103">Libera el objeto binario de recursos Win32 y recursos asociados.</span><span class="sxs-lookup"><span data-stu-id="3387e-103">Releases the Win32 resource blob and associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3387e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3387e-104">Syntax</span></span>  
  
```  
HRESULT FreeWin32ResBlob(  
    const void** ppResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3387e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3387e-105">Parameters</span></span>  
 `ppResBlob`  
 <span data-ttu-id="3387e-106">El objeto binario de recursos para publicarse.</span><span class="sxs-lookup"><span data-stu-id="3387e-106">The resource blob to be released.</span></span> <span data-ttu-id="3387e-107">Este método asigna el puntero de blob a NULL.</span><span class="sxs-lookup"><span data-stu-id="3387e-107">This method assigns the blob pointer to NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3387e-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3387e-108">Return Value</span></span>  
 <span data-ttu-id="3387e-109">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="3387e-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3387e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3387e-110">Requirements</span></span>  
 <span data-ttu-id="3387e-111">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="3387e-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3387e-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3387e-112">See also</span></span>
- [<span data-ttu-id="3387e-113">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3387e-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="3387e-114">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3387e-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="3387e-115">API de ALink</span><span class="sxs-lookup"><span data-stu-id="3387e-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

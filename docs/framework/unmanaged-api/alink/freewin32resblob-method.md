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
ms.openlocfilehash: 196a57b3e919ea4ccbc0b91e5b6f281ad3c30b62
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59118162"
---
# <a name="freewin32resblob-method"></a><span data-ttu-id="aaaef-102">FreeWin32ResBlob (Método)</span><span class="sxs-lookup"><span data-stu-id="aaaef-102">FreeWin32ResBlob Method</span></span>
<span data-ttu-id="aaaef-103">Libera el objeto binario de recursos Win32 y recursos asociados.</span><span class="sxs-lookup"><span data-stu-id="aaaef-103">Releases the Win32 resource blob and associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aaaef-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aaaef-104">Syntax</span></span>  
  
```  
HRESULT FreeWin32ResBlob(  
    const void** ppResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="aaaef-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aaaef-105">Parameters</span></span>  
 `ppResBlob`  
 <span data-ttu-id="aaaef-106">El objeto binario de recursos para publicarse.</span><span class="sxs-lookup"><span data-stu-id="aaaef-106">The resource blob to be released.</span></span> <span data-ttu-id="aaaef-107">Este método asigna el puntero de blob a NULL.</span><span class="sxs-lookup"><span data-stu-id="aaaef-107">This method assigns the blob pointer to NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aaaef-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="aaaef-108">Return Value</span></span>  
 <span data-ttu-id="aaaef-109">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="aaaef-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aaaef-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aaaef-110">Requirements</span></span>  
 <span data-ttu-id="aaaef-111">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="aaaef-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaaef-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="aaaef-112">See also</span></span>

- [<span data-ttu-id="aaaef-113">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="aaaef-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="aaaef-114">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="aaaef-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="aaaef-115">API de ALink</span><span class="sxs-lookup"><span data-stu-id="aaaef-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

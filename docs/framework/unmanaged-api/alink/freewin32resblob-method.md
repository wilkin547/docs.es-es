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
ms.openlocfilehash: 44c5228f7ee467abd02a9ec09590d0352fc82036
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684764"
---
# <a name="freewin32resblob-method"></a><span data-ttu-id="1ebbe-102">FreeWin32ResBlob (Método)</span><span class="sxs-lookup"><span data-stu-id="1ebbe-102">FreeWin32ResBlob Method</span></span>

<span data-ttu-id="1ebbe-103">Libera el BLOB de recursos de Win32 y los recursos asociados.</span><span class="sxs-lookup"><span data-stu-id="1ebbe-103">Releases the Win32 resource blob and associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ebbe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ebbe-104">Syntax</span></span>  
  
```cpp  
HRESULT FreeWin32ResBlob(  
    const void** ppResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ebbe-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1ebbe-105">Parameters</span></span>  

 `ppResBlob`  
 <span data-ttu-id="1ebbe-106">El BLOB de recursos que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="1ebbe-106">The resource blob to be released.</span></span> <span data-ttu-id="1ebbe-107">Este método asigna el puntero de BLOB a NULL.</span><span class="sxs-lookup"><span data-stu-id="1ebbe-107">This method assigns the blob pointer to NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ebbe-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1ebbe-108">Return Value</span></span>  

 <span data-ttu-id="1ebbe-109">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="1ebbe-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ebbe-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1ebbe-110">Requirements</span></span>  

 <span data-ttu-id="1ebbe-111">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="1ebbe-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ebbe-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1ebbe-112">See also</span></span>

- [<span data-ttu-id="1ebbe-113">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1ebbe-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="1ebbe-114">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1ebbe-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="1ebbe-115">API de ALink</span><span class="sxs-lookup"><span data-stu-id="1ebbe-115">ALink API</span></span>](index.md)

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
ms.openlocfilehash: ea0fbceb1e778a2f26e0625a337b803f417b59eb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777246"
---
# <a name="freewin32resblob-method"></a><span data-ttu-id="cbfd6-102">FreeWin32ResBlob (Método)</span><span class="sxs-lookup"><span data-stu-id="cbfd6-102">FreeWin32ResBlob Method</span></span>
<span data-ttu-id="cbfd6-103">Libera el BLOB de recursos de Win32 y los recursos asociados.</span><span class="sxs-lookup"><span data-stu-id="cbfd6-103">Releases the Win32 resource blob and associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbfd6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cbfd6-104">Syntax</span></span>  
  
```cpp  
HRESULT FreeWin32ResBlob(  
    const void** ppResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbfd6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cbfd6-105">Parameters</span></span>  
 `ppResBlob`  
 <span data-ttu-id="cbfd6-106">El BLOB de recursos que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="cbfd6-106">The resource blob to be released.</span></span> <span data-ttu-id="cbfd6-107">Este método asigna el puntero de BLOB a NULL.</span><span class="sxs-lookup"><span data-stu-id="cbfd6-107">This method assigns the blob pointer to NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cbfd6-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cbfd6-108">Return Value</span></span>  
 <span data-ttu-id="cbfd6-109">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="cbfd6-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbfd6-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cbfd6-110">Requirements</span></span>  
 <span data-ttu-id="cbfd6-111">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="cbfd6-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbfd6-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="cbfd6-112">See also</span></span>

- [<span data-ttu-id="cbfd6-113">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cbfd6-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="cbfd6-114">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cbfd6-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="cbfd6-115">API de ALink</span><span class="sxs-lookup"><span data-stu-id="cbfd6-115">ALink API</span></span>](index.md)

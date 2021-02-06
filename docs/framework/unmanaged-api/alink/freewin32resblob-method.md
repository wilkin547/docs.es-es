---
description: 'Más información sobre: método Freewin32resblob ('
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
ms.openlocfilehash: 56c83632b623eec76e8e2d24030c79a8262f506f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637948"
---
# <a name="freewin32resblob-method"></a><span data-ttu-id="e5ac8-103">FreeWin32ResBlob (Método)</span><span class="sxs-lookup"><span data-stu-id="e5ac8-103">FreeWin32ResBlob Method</span></span>

<span data-ttu-id="e5ac8-104">Libera el BLOB de recursos de Win32 y los recursos asociados.</span><span class="sxs-lookup"><span data-stu-id="e5ac8-104">Releases the Win32 resource blob and associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5ac8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5ac8-105">Syntax</span></span>  
  
```cpp  
HRESULT FreeWin32ResBlob(  
    const void** ppResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5ac8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e5ac8-106">Parameters</span></span>  

 `ppResBlob`  
 <span data-ttu-id="e5ac8-107">El BLOB de recursos que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="e5ac8-107">The resource blob to be released.</span></span> <span data-ttu-id="e5ac8-108">Este método asigna el puntero de BLOB a NULL.</span><span class="sxs-lookup"><span data-stu-id="e5ac8-108">This method assigns the blob pointer to NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5ac8-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e5ac8-109">Return Value</span></span>  

 <span data-ttu-id="e5ac8-110">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="e5ac8-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5ac8-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e5ac8-111">Requirements</span></span>  

 <span data-ttu-id="e5ac8-112">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="e5ac8-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5ac8-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5ac8-113">See also</span></span>

- [<span data-ttu-id="e5ac8-114">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e5ac8-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="e5ac8-115">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e5ac8-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="e5ac8-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="e5ac8-116">ALink API</span></span>](index.md)

---
title: CloseEnum (Método)
ms.date: 03/30/2017
api_name:
- CloseEnum
- IALink.CloseEnum
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- CloseEnum
helpviewer_keywords:
- CloseEnum method
ms.assetid: aa4a091e-13fe-4264-91de-e12f1c767c87
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 009f7d20dfd6efc279b3187af8f5c95132ae51e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54525240"
---
# <a name="closeenum-method"></a><span data-ttu-id="9759b-102">CloseEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="9759b-102">CloseEnum Method</span></span>
<span data-ttu-id="9759b-103">La enumeración indicada se cierra y libera los recursos asociados.</span><span class="sxs-lookup"><span data-stu-id="9759b-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9759b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9759b-104">Syntax</span></span>  
  
```  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9759b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9759b-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="9759b-106">Identificador de la enumeración que se cerrará.</span><span class="sxs-lookup"><span data-stu-id="9759b-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9759b-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9759b-107">Return Value</span></span>  
 <span data-ttu-id="9759b-108">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="9759b-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9759b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9759b-109">Requirements</span></span>  
 <span data-ttu-id="9759b-110">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="9759b-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9759b-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="9759b-111">See also</span></span>
- [<span data-ttu-id="9759b-112">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9759b-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="9759b-113">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9759b-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="9759b-114">API de ALink</span><span class="sxs-lookup"><span data-stu-id="9759b-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

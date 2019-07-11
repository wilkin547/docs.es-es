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
ms.openlocfilehash: 9b6c839cc664105149f26b0d21d7ba7fb91b3e29
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742202"
---
# <a name="closeenum-method"></a><span data-ttu-id="d4e38-102">CloseEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="d4e38-102">CloseEnum Method</span></span>
<span data-ttu-id="d4e38-103">La enumeración indicada se cierra y libera los recursos asociados.</span><span class="sxs-lookup"><span data-stu-id="d4e38-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4e38-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d4e38-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4e38-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d4e38-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="d4e38-106">Identificador de la enumeración que se cerrará.</span><span class="sxs-lookup"><span data-stu-id="d4e38-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4e38-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d4e38-107">Return Value</span></span>  
 <span data-ttu-id="d4e38-108">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="d4e38-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4e38-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d4e38-109">Requirements</span></span>  
 <span data-ttu-id="d4e38-110">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="d4e38-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4e38-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4e38-111">See also</span></span>

- [<span data-ttu-id="d4e38-112">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d4e38-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="d4e38-113">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d4e38-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="d4e38-114">API de ALink</span><span class="sxs-lookup"><span data-stu-id="d4e38-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

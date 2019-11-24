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
ms.openlocfilehash: 018af6929ad4023c70bfb975b9be010912415dd7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446562"
---
# <a name="closeenum-method"></a><span data-ttu-id="db288-102">CloseEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="db288-102">CloseEnum Method</span></span>
<span data-ttu-id="db288-103">Closes the indicated enumeration and frees associated resources.</span><span class="sxs-lookup"><span data-stu-id="db288-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db288-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db288-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="db288-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="db288-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="db288-106">Handle of enumeration to be closed.</span><span class="sxs-lookup"><span data-stu-id="db288-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="db288-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="db288-107">Return Value</span></span>  
 <span data-ttu-id="db288-108">Returns S_OK if the method succeeds.</span><span class="sxs-lookup"><span data-stu-id="db288-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db288-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="db288-109">Requirements</span></span>  
 <span data-ttu-id="db288-110">Requires alink.h</span><span class="sxs-lookup"><span data-stu-id="db288-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db288-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="db288-111">See also</span></span>

- [<span data-ttu-id="db288-112">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="db288-112">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="db288-113">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="db288-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="db288-114">API de ALink</span><span class="sxs-lookup"><span data-stu-id="db288-114">ALink API</span></span>](index.md)

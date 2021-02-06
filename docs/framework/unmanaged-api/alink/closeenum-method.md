---
description: 'Más información sobre: método Closeenum ('
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
ms.openlocfilehash: 700c54de5af2e5c0be6940d4045019092655d46f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638384"
---
# <a name="closeenum-method"></a><span data-ttu-id="af3fa-103">CloseEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="af3fa-103">CloseEnum Method</span></span>

<span data-ttu-id="af3fa-104">Cierra la enumeración indicada y libera los recursos asociados.</span><span class="sxs-lookup"><span data-stu-id="af3fa-104">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af3fa-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af3fa-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="af3fa-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="af3fa-106">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="af3fa-107">Identificador de la enumeración que se va a cerrar.</span><span class="sxs-lookup"><span data-stu-id="af3fa-107">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af3fa-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="af3fa-108">Return Value</span></span>  

 <span data-ttu-id="af3fa-109">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="af3fa-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af3fa-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="af3fa-110">Requirements</span></span>  

 <span data-ttu-id="af3fa-111">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="af3fa-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af3fa-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="af3fa-112">See also</span></span>

- [<span data-ttu-id="af3fa-113">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="af3fa-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="af3fa-114">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="af3fa-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="af3fa-115">API de ALink</span><span class="sxs-lookup"><span data-stu-id="af3fa-115">ALink API</span></span>](index.md)

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
ms.openlocfilehash: 8d9529022eb04c81152dced5c63f255c510851a0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777465"
---
# <a name="closeenum-method"></a><span data-ttu-id="af0ec-102">CloseEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="af0ec-102">CloseEnum Method</span></span>
<span data-ttu-id="af0ec-103">Cierra la enumeración indicada y libera los recursos asociados.</span><span class="sxs-lookup"><span data-stu-id="af0ec-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af0ec-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af0ec-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="af0ec-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="af0ec-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="af0ec-106">Identificador de la enumeración que se va a cerrar.</span><span class="sxs-lookup"><span data-stu-id="af0ec-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af0ec-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="af0ec-107">Return Value</span></span>  
 <span data-ttu-id="af0ec-108">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="af0ec-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af0ec-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="af0ec-109">Requirements</span></span>  
 <span data-ttu-id="af0ec-110">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="af0ec-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af0ec-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="af0ec-111">See also</span></span>

- [<span data-ttu-id="af0ec-112">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="af0ec-112">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="af0ec-113">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="af0ec-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="af0ec-114">API de ALink</span><span class="sxs-lookup"><span data-stu-id="af0ec-114">ALink API</span></span>](index.md)

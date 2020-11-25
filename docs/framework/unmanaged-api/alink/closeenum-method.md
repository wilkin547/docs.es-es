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
ms.openlocfilehash: 59b1ec3f9ca382ef13680e3aad4d0c0c0e175f1c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716972"
---
# <a name="closeenum-method"></a><span data-ttu-id="15a3c-102">CloseEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="15a3c-102">CloseEnum Method</span></span>

<span data-ttu-id="15a3c-103">Cierra la enumeración indicada y libera los recursos asociados.</span><span class="sxs-lookup"><span data-stu-id="15a3c-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15a3c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15a3c-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="15a3c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="15a3c-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="15a3c-106">Identificador de la enumeración que se va a cerrar.</span><span class="sxs-lookup"><span data-stu-id="15a3c-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15a3c-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="15a3c-107">Return Value</span></span>  

 <span data-ttu-id="15a3c-108">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="15a3c-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15a3c-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15a3c-109">Requirements</span></span>  

 <span data-ttu-id="15a3c-110">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="15a3c-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15a3c-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="15a3c-111">See also</span></span>

- [<span data-ttu-id="15a3c-112">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="15a3c-112">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="15a3c-113">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="15a3c-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="15a3c-114">API de ALink</span><span class="sxs-lookup"><span data-stu-id="15a3c-114">ALink API</span></span>](index.md)

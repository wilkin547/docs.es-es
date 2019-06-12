---
title: ICorDebugComObjectValue::GetCachedInterfaceTypes (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
helpviewer_keywords:
- GetCachedInterface method, ICorDebugComObjectValue interface [.NET Framework debugging]
- ICorDebugComObjectValue::GetCachedInterface method [.NET Framework debugging]
ms.assetid: d492284f-d3c5-4614-adb8-d718d5042500
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e1da347fd85e1b3856615faf49c60b607cc7f0da
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025842"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a><span data-ttu-id="7825c-102">ICorDebugComObjectValue::GetCachedInterfaceTypes (Método)</span><span class="sxs-lookup"><span data-stu-id="7825c-102">ICorDebugComObjectValue::GetCachedInterfaceTypes Method</span></span>
<span data-ttu-id="7825c-103">Proporciona un enumerador para los tipos de interfaz que el objeto actual tiene se convierte en o se utiliza como.</span><span class="sxs-lookup"><span data-stu-id="7825c-103">Provides an enumerator for the interface types that the current object has been cast to or used as.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7825c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7825c-104">Syntax</span></span>  
  
```  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7825c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7825c-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="7825c-106">[in] Un valor que indica si el método devuelve sólo las interfaces de Windows en tiempo de ejecución (`IInspectable` interfaces) o todas las interfaces COM que se almacena en caché el contenedor invocable en tiempo de ejecución (RCW).</span><span class="sxs-lookup"><span data-stu-id="7825c-106">[in] A value that indicates whether the method returns only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces cached by the runtime callable wrapper (RCW).</span></span>  
  
 `ppInterfacesEnum`  
 <span data-ttu-id="7825c-107">[out] Un puntero a la dirección del enumerador ICorDebugTypeEnum que proporciona acceso a objetos ICorDebugType que representan tipos de interfaz almacenados en caché se filtra según `bIInspectableOnly`.</span><span class="sxs-lookup"><span data-stu-id="7825c-107">[out] A pointer to the address of an ICorDebugTypeEnum enumerator that provides access to ICorDebugType objects that represent cached interface types filtered according to `bIInspectableOnly`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7825c-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7825c-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7825c-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7825c-109">Requirements</span></span>  
 <span data-ttu-id="7825c-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7825c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7825c-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7825c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7825c-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7825c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7825c-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7825c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7825c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="7825c-114">See also</span></span>

- [<span data-ttu-id="7825c-115">ICorDebugComObjectValue (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7825c-115">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="7825c-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="7825c-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

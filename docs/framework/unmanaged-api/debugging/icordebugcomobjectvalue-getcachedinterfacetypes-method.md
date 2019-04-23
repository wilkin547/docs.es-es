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
ms.openlocfilehash: 36e6313ae7b4c67a20bee6d2a76a4ed1da84acbe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115224"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a><span data-ttu-id="cba01-102">ICorDebugComObjectValue::GetCachedInterfaceTypes (Método)</span><span class="sxs-lookup"><span data-stu-id="cba01-102">ICorDebugComObjectValue::GetCachedInterfaceTypes Method</span></span>
<span data-ttu-id="cba01-103">Proporciona un enumerador para los tipos de interfaz que el objeto actual tiene se convierte en o se utiliza como.</span><span class="sxs-lookup"><span data-stu-id="cba01-103">Provides an enumerator for the interface types that the current object has been cast to or used as.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cba01-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cba01-104">Syntax</span></span>  
  
```  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cba01-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cba01-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="cba01-106">[in] Un valor que indica si el método devuelve sólo [!INCLUDE[wrt](../../../../includes/wrt-md.md)] interfaces (`IInspectable` interfaces) o todas las interfaces COM que se almacena en caché el contenedor invocable en tiempo de ejecución (RCW).</span><span class="sxs-lookup"><span data-stu-id="cba01-106">[in] A value that indicates whether the method returns only [!INCLUDE[wrt](../../../../includes/wrt-md.md)] interfaces (`IInspectable` interfaces) or all COM interfaces cached by the runtime callable wrapper (RCW).</span></span>  
  
 `ppInterfacesEnum`  
 <span data-ttu-id="cba01-107">[out] Un puntero a la dirección del enumerador ICorDebugTypeEnum que proporciona acceso a objetos ICorDebugType que representan tipos de interfaz almacenados en caché se filtra según `bIInspectableOnly`.</span><span class="sxs-lookup"><span data-stu-id="cba01-107">[out] A pointer to the address of an ICorDebugTypeEnum enumerator that provides access to ICorDebugType objects that represent cached interface types filtered according to `bIInspectableOnly`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cba01-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cba01-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cba01-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cba01-109">Requirements</span></span>  
 <span data-ttu-id="cba01-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cba01-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cba01-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cba01-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cba01-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cba01-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cba01-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cba01-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cba01-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="cba01-114">See also</span></span>

- [<span data-ttu-id="cba01-115">ICorDebugComObjectValue (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cba01-115">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="cba01-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="cba01-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

---
title: 'Icordebugtype2:: GetTypeId (método)'
ms.date: 03/30/2017
api_name:
- ICorDebugType2.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetTypeID
helpviewer_keywords:
- GetTypeID method, ICorDebugType2 interface [.NET Framework debugging]
- ICorDebugType2.GetTypeID method [.NET Framework debugging]
ms.assetid: 0b933686-226e-4373-92b7-fac579ee7b1a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b19efdedc21f66e4692ce1850eb3947f856e436
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993803"
---
# <a name="icordebugtype2gettypeid-method"></a><span data-ttu-id="2859a-102">Icordebugtype2:: GetTypeId (método)</span><span class="sxs-lookup"><span data-stu-id="2859a-102">ICorDebugType2::GetTypeID Method</span></span>
<span data-ttu-id="2859a-103">Obtiene un [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) para este tipo.</span><span class="sxs-lookup"><span data-stu-id="2859a-103">Gets a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) for this type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2859a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2859a-104">Syntax</span></span>  
  
```  
HRESULT GetTypeID(  
    ([out] COR_TYPEID *id  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2859a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2859a-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="2859a-106">[out] Un puntero a la [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) para esta instancia de ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="2859a-106">[out] A pointer to the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) for this ICorDebugType.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2859a-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2859a-107">Return Value</span></span>  
 <span data-ttu-id="2859a-108">El valor devuelto es `S_OK` si se realiza correctamente, o un código de error `HRESULT` en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="2859a-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="2859a-109">El `HRESULT` códigos incluyen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2859a-109">The `HRESULT` codes include the following:</span></span>  
  
|<span data-ttu-id="2859a-110">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="2859a-110">Return code</span></span>|<span data-ttu-id="2859a-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="2859a-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="2859a-112">El método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="2859a-112">Method succeeded.</span></span> <span data-ttu-id="2859a-113">El método ha recuperado válido [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md).</span><span class="sxs-lookup"><span data-stu-id="2859a-113">The method has retrieved a valid [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md).</span></span>|  
|`CORDBG_E_CLASS_NOT_LOADED`|<span data-ttu-id="2859a-114">El tipo no se ha cargado.</span><span class="sxs-lookup"><span data-stu-id="2859a-114">The type has not been loaded.</span></span>|  
|`CORDBG_E_UNSUPPORTED`|<span data-ttu-id="2859a-115">No se admite el tipo.</span><span class="sxs-lookup"><span data-stu-id="2859a-115">The type is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2859a-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2859a-116">Remarks</span></span>  
 <span data-ttu-id="2859a-117">Este método proporciona una asignación de ICorDebugType, que representa un tipo que puede o es posible que no se han cargado en el tiempo de ejecución a un [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), controlar que actúa como opaco que identifica un tipo que se cargan en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2859a-117">This method provides a mapping from the ICorDebugType, which represents a type that may or may not have been loaded into the runtime, to a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), which serves as an opaque handle that identifies a type loaded into the runtime.</span></span>  
  
 <span data-ttu-id="2859a-118">Cuando el tipo que representa la instancia de ICorDebugType aún no se ha cargado, este método devuelve `CORDBG_E_CLASS_NOT_LOADED`.</span><span class="sxs-lookup"><span data-stu-id="2859a-118">When the type that the ICorDebugType represents has not yet been loaded, this method returns `CORDBG_E_CLASS_NOT_LOADED`.</span></span>  <span data-ttu-id="2859a-119">Si no se admite el tipo, devuelve `CORDBG_E_UNSUPPORTED`.</span><span class="sxs-lookup"><span data-stu-id="2859a-119">If the type is not supported, it returns `CORDBG_E_UNSUPPORTED`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2859a-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2859a-120">Requirements</span></span>  
 <span data-ttu-id="2859a-121">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2859a-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2859a-122">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2859a-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2859a-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2859a-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2859a-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2859a-124">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2859a-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="2859a-125">See also</span></span>

- [<span data-ttu-id="2859a-126">ICorDebugType2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2859a-126">ICorDebugType2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-interface.md)

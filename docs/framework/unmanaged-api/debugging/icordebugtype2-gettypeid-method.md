---
title: 'ICorDebugType2:: GetTypeID (método)'
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
ms.openlocfilehash: 631f605fd18559b36071964e35a15761cd4c8228
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791226"
---
# <a name="icordebugtype2gettypeid-method"></a><span data-ttu-id="eaf31-102">ICorDebugType2:: GetTypeID (método)</span><span class="sxs-lookup"><span data-stu-id="eaf31-102">ICorDebugType2::GetTypeID Method</span></span>
<span data-ttu-id="eaf31-103">Obtiene un [COR_TYPEID](cor-typeid-structure.md) para este tipo.</span><span class="sxs-lookup"><span data-stu-id="eaf31-103">Gets a [COR_TYPEID](cor-typeid-structure.md) for this type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eaf31-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eaf31-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeID(  
    ([out] COR_TYPEID *id  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eaf31-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="eaf31-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="eaf31-106">enuncia Puntero a la [COR_TYPEID](cor-typeid-structure.md) para esta ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="eaf31-106">[out] A pointer to the [COR_TYPEID](cor-typeid-structure.md) for this ICorDebugType.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eaf31-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="eaf31-107">Return Value</span></span>  
 <span data-ttu-id="eaf31-108">El valor devuelto es `S_OK` si se realiza correctamente, o un código de error `HRESULT` en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="eaf31-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="eaf31-109">Entre los códigos de `HRESULT` se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="eaf31-109">The `HRESULT` codes include the following:</span></span>  
  
|<span data-ttu-id="eaf31-110">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="eaf31-110">Return code</span></span>|<span data-ttu-id="eaf31-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="eaf31-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="eaf31-112">El método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="eaf31-112">Method succeeded.</span></span> <span data-ttu-id="eaf31-113">El método ha recuperado un [COR_TYPEID](cor-typeid-structure.md)válido.</span><span class="sxs-lookup"><span data-stu-id="eaf31-113">The method has retrieved a valid [COR_TYPEID](cor-typeid-structure.md).</span></span>|  
|`CORDBG_E_CLASS_NOT_LOADED`|<span data-ttu-id="eaf31-114">No se ha cargado el tipo.</span><span class="sxs-lookup"><span data-stu-id="eaf31-114">The type has not been loaded.</span></span>|  
|`CORDBG_E_UNSUPPORTED`|<span data-ttu-id="eaf31-115">El tipo no se admite.</span><span class="sxs-lookup"><span data-stu-id="eaf31-115">The type is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eaf31-116">Notas</span><span class="sxs-lookup"><span data-stu-id="eaf31-116">Remarks</span></span>  
 <span data-ttu-id="eaf31-117">Este método proporciona una asignación de la ICorDebugType, que representa un tipo que se puede o no haber cargado en el tiempo de ejecución, en una [COR_TYPEID](cor-typeid-structure.md), que actúa como un identificador opaco que identifica un tipo cargado en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="eaf31-117">This method provides a mapping from the ICorDebugType, which represents a type that may or may not have been loaded into the runtime, to a [COR_TYPEID](cor-typeid-structure.md), which serves as an opaque handle that identifies a type loaded into the runtime.</span></span>  
  
 <span data-ttu-id="eaf31-118">Cuando el tipo que representa la ICorDebugType no se ha cargado todavía, este método devuelve `CORDBG_E_CLASS_NOT_LOADED`.</span><span class="sxs-lookup"><span data-stu-id="eaf31-118">When the type that the ICorDebugType represents has not yet been loaded, this method returns `CORDBG_E_CLASS_NOT_LOADED`.</span></span>  <span data-ttu-id="eaf31-119">Si no se admite el tipo, devuelve `CORDBG_E_UNSUPPORTED`.</span><span class="sxs-lookup"><span data-stu-id="eaf31-119">If the type is not supported, it returns `CORDBG_E_UNSUPPORTED`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eaf31-120">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="eaf31-120">Requirements</span></span>  
 <span data-ttu-id="eaf31-121">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eaf31-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eaf31-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eaf31-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eaf31-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eaf31-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eaf31-124">**.NET Framework versiones:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eaf31-124">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaf31-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="eaf31-125">See also</span></span>

- [<span data-ttu-id="eaf31-126">ICorDebugType2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="eaf31-126">ICorDebugType2 Interface</span></span>](icordebugtype2-interface.md)

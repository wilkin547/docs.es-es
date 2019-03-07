---
title: Método ICorDebugProcess6::GetExportStepInfo
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3b60bad75cb6286bda026e5b67e0a4fa8e2347dd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487179"
---
# <a name="icordebugprocess6getexportstepinfo-method"></a><span data-ttu-id="9eb80-102">Método ICorDebugProcess6::GetExportStepInfo</span><span class="sxs-lookup"><span data-stu-id="9eb80-102">ICorDebugProcess6::GetExportStepInfo Method</span></span>
<span data-ttu-id="9eb80-103">Proporciona información sobre las funciones exportadas en tiempo de ejecución para ayudar a recorrer el código administrado.</span><span class="sxs-lookup"><span data-stu-id="9eb80-103">Provides information on runtime exported functions to help step through managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9eb80-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9eb80-104">Syntax</span></span>  
  
```  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,   
    [out] CorDebugCodeInvokeKind* pInvokeKind,   
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9eb80-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9eb80-105">Parameters</span></span>  
 <span data-ttu-id="9eb80-106">pszExportName</span><span class="sxs-lookup"><span data-stu-id="9eb80-106">pszExportName</span></span>  
 <span data-ttu-id="9eb80-107">[in] Nombre de una función de exportación en tiempo de ejecución según aparece escrito en la tabla de exportación de PE.</span><span class="sxs-lookup"><span data-stu-id="9eb80-107">[in] The name of a runtime export function as written in the PE export table.</span></span>  
  
 <span data-ttu-id="9eb80-108">invokeKind</span><span class="sxs-lookup"><span data-stu-id="9eb80-108">invokeKind</span></span>  
 <span data-ttu-id="9eb80-109">[out] Un puntero a un miembro de la [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md) enumeración que describe cómo la función exportada invocará código administrado.</span><span class="sxs-lookup"><span data-stu-id="9eb80-109">[out] A pointer to a member of the [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md) enumeration that describes how the exported function will invoke managed code.</span></span>  
  
 <span data-ttu-id="9eb80-110">invokePurpose</span><span class="sxs-lookup"><span data-stu-id="9eb80-110">invokePurpose</span></span>  
 <span data-ttu-id="9eb80-111">[out] Un puntero a un miembro de la [CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md) enumeración que describe por qué la función exportada llamará a código administrado.</span><span class="sxs-lookup"><span data-stu-id="9eb80-111">[out] A pointer to a member of the [CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md) enumeration that describes why the exported function will call managed code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9eb80-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9eb80-112">Return Value</span></span>  
 <span data-ttu-id="9eb80-113">El método puede devolver los valores enumerados en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="9eb80-113">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="9eb80-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9eb80-114">Return value</span></span>|<span data-ttu-id="9eb80-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="9eb80-115">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="9eb80-116">La llamada al método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="9eb80-116">The method call was successful.</span></span>|  
|`E_POINTER`|<span data-ttu-id="9eb80-117">`pInvokeKind` o `pInvokePurpose` es **null**.</span><span class="sxs-lookup"><span data-stu-id="9eb80-117">`pInvokeKind` or `pInvokePurpose` is **null**.</span></span>|  
|<span data-ttu-id="9eb80-118">Otros valores de error de `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="9eb80-118">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="9eb80-119">Según el caso.</span><span class="sxs-lookup"><span data-stu-id="9eb80-119">As appropriate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9eb80-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9eb80-120">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9eb80-121">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9eb80-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9eb80-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9eb80-122">Requirements</span></span>  
 <span data-ttu-id="9eb80-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9eb80-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9eb80-124">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9eb80-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9eb80-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9eb80-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9eb80-126">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9eb80-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eb80-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="9eb80-127">See also</span></span>
- [<span data-ttu-id="9eb80-128">ICorDebugProcess6 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9eb80-128">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="9eb80-129">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="9eb80-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

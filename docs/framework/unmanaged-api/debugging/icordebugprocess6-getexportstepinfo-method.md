---
title: Método ICorDebugProcess6::GetExportStepInfo
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
ms.openlocfilehash: 118f52db63464b4c9355ba9ee7f330b996c5bf71
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792245"
---
# <a name="icordebugprocess6getexportstepinfo-method"></a><span data-ttu-id="27dbd-102">Método ICorDebugProcess6::GetExportStepInfo</span><span class="sxs-lookup"><span data-stu-id="27dbd-102">ICorDebugProcess6::GetExportStepInfo Method</span></span>
<span data-ttu-id="27dbd-103">Proporciona información sobre las funciones exportadas en tiempo de ejecución para ayudar a recorrer el código administrado.</span><span class="sxs-lookup"><span data-stu-id="27dbd-103">Provides information on runtime exported functions to help step through managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27dbd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="27dbd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,   
    [out] CorDebugCodeInvokeKind* pInvokeKind,   
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27dbd-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="27dbd-105">Parameters</span></span>  
 <span data-ttu-id="27dbd-106">pszExportName</span><span class="sxs-lookup"><span data-stu-id="27dbd-106">pszExportName</span></span>  
 <span data-ttu-id="27dbd-107">[in] Nombre de una función de exportación en tiempo de ejecución según aparece escrito en la tabla de exportación de PE.</span><span class="sxs-lookup"><span data-stu-id="27dbd-107">[in] The name of a runtime export function as written in the PE export table.</span></span>  
  
 <span data-ttu-id="27dbd-108">invokeKind</span><span class="sxs-lookup"><span data-stu-id="27dbd-108">invokeKind</span></span>  
 <span data-ttu-id="27dbd-109">enuncia Un puntero a un miembro de la enumeración [CorDebugCodeInvokeKind](cordebugcodeinvokekind-enumeration.md) que describe cómo la función exportada llamará al código administrado.</span><span class="sxs-lookup"><span data-stu-id="27dbd-109">[out] A pointer to a member of the [CorDebugCodeInvokeKind](cordebugcodeinvokekind-enumeration.md) enumeration that describes how the exported function will invoke managed code.</span></span>  
  
 <span data-ttu-id="27dbd-110">invokePurpose</span><span class="sxs-lookup"><span data-stu-id="27dbd-110">invokePurpose</span></span>  
 <span data-ttu-id="27dbd-111">enuncia Un puntero a un miembro de la enumeración [CorDebugCodeInvokePurpose](cordebugcodeinvokepurpose-enumeration.md) que describe por qué la función exportada llamará al código administrado.</span><span class="sxs-lookup"><span data-stu-id="27dbd-111">[out] A pointer to a member of the [CorDebugCodeInvokePurpose](cordebugcodeinvokepurpose-enumeration.md) enumeration that describes why the exported function will call managed code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27dbd-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="27dbd-112">Return Value</span></span>  
 <span data-ttu-id="27dbd-113">El método puede devolver los valores enumerados en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="27dbd-113">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="27dbd-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="27dbd-114">Return value</span></span>|<span data-ttu-id="27dbd-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="27dbd-115">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="27dbd-116">La llamada al método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="27dbd-116">The method call was successful.</span></span>|  
|`E_POINTER`|<span data-ttu-id="27dbd-117">`pInvokeKind` o `pInvokePurpose` es **null**.</span><span class="sxs-lookup"><span data-stu-id="27dbd-117">`pInvokeKind` or `pInvokePurpose` is **null**.</span></span>|  
|<span data-ttu-id="27dbd-118">Otros valores de error de `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="27dbd-118">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="27dbd-119">Según el caso.</span><span class="sxs-lookup"><span data-stu-id="27dbd-119">As appropriate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27dbd-120">Notas</span><span class="sxs-lookup"><span data-stu-id="27dbd-120">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="27dbd-121">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="27dbd-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27dbd-122">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="27dbd-122">Requirements</span></span>  
 <span data-ttu-id="27dbd-123">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27dbd-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27dbd-124">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="27dbd-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27dbd-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27dbd-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27dbd-126">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27dbd-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27dbd-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="27dbd-127">See also</span></span>

- [<span data-ttu-id="27dbd-128">ICorDebugProcess6 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="27dbd-128">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="27dbd-129">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="27dbd-129">Debugging Interfaces</span></span>](debugging-interfaces.md)

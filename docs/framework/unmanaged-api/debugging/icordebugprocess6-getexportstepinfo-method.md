---
description: 'Más información sobre: método icordebugprocess6:: GetExportStepInfo (método)'
title: Método ICorDebugProcess6::GetExportStepInfo
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
ms.openlocfilehash: e14b5e66d90fb2ece91991b3634fc2ad86fac895
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722014"
---
# <a name="icordebugprocess6getexportstepinfo-method"></a><span data-ttu-id="cf827-103">Método ICorDebugProcess6::GetExportStepInfo</span><span class="sxs-lookup"><span data-stu-id="cf827-103">ICorDebugProcess6::GetExportStepInfo Method</span></span>

<span data-ttu-id="cf827-104">Proporciona información sobre las funciones exportadas en tiempo de ejecución para ayudar a recorrer el código administrado.</span><span class="sxs-lookup"><span data-stu-id="cf827-104">Provides information on runtime exported functions to help step through managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf827-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf827-105">Syntax</span></span>  
  
```cpp  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,
    [out] CorDebugCodeInvokeKind* pInvokeKind,
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf827-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cf827-106">Parameters</span></span>  

 <span data-ttu-id="cf827-107">pszExportName</span><span class="sxs-lookup"><span data-stu-id="cf827-107">pszExportName</span></span>  
 <span data-ttu-id="cf827-108">[in] Nombre de una función de exportación en tiempo de ejecución según aparece escrito en la tabla de exportación de PE.</span><span class="sxs-lookup"><span data-stu-id="cf827-108">[in] The name of a runtime export function as written in the PE export table.</span></span>  
  
 <span data-ttu-id="cf827-109">invokeKind</span><span class="sxs-lookup"><span data-stu-id="cf827-109">invokeKind</span></span>  
 <span data-ttu-id="cf827-110">enuncia Un puntero a un miembro de la enumeración [CorDebugCodeInvokeKind](cordebugcodeinvokekind-enumeration.md) que describe cómo la función exportada llamará al código administrado.</span><span class="sxs-lookup"><span data-stu-id="cf827-110">[out] A pointer to a member of the [CorDebugCodeInvokeKind](cordebugcodeinvokekind-enumeration.md) enumeration that describes how the exported function will invoke managed code.</span></span>  
  
 <span data-ttu-id="cf827-111">invokePurpose</span><span class="sxs-lookup"><span data-stu-id="cf827-111">invokePurpose</span></span>  
 <span data-ttu-id="cf827-112">enuncia Un puntero a un miembro de la enumeración [CorDebugCodeInvokePurpose](cordebugcodeinvokepurpose-enumeration.md) que describe por qué la función exportada llamará al código administrado.</span><span class="sxs-lookup"><span data-stu-id="cf827-112">[out] A pointer to a member of the [CorDebugCodeInvokePurpose](cordebugcodeinvokepurpose-enumeration.md) enumeration that describes why the exported function will call managed code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cf827-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cf827-113">Return Value</span></span>  

 <span data-ttu-id="cf827-114">El método puede devolver los valores enumerados en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="cf827-114">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="cf827-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cf827-115">Return value</span></span>|<span data-ttu-id="cf827-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="cf827-116">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="cf827-117">La llamada al método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="cf827-117">The method call was successful.</span></span>|  
|`E_POINTER`|<span data-ttu-id="cf827-118">`pInvokeKind` o `pInvokePurpose` es **null**.</span><span class="sxs-lookup"><span data-stu-id="cf827-118">`pInvokeKind` or `pInvokePurpose` is **null**.</span></span>|  
|<span data-ttu-id="cf827-119">Otros valores de error de `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="cf827-119">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="cf827-120">Según el caso.</span><span class="sxs-lookup"><span data-stu-id="cf827-120">As appropriate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf827-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cf827-121">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cf827-122">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="cf827-122">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf827-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cf827-123">Requirements</span></span>  

 <span data-ttu-id="cf827-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf827-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf827-125">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf827-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf827-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf827-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf827-127">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf827-127">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf827-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf827-128">See also</span></span>

- [<span data-ttu-id="cf827-129">Interfaz ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="cf827-129">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="cf827-130">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="cf827-130">Debugging Interfaces</span></span>](debugging-interfaces.md)

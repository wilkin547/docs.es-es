---
title: Método ICorDebugProcess6::GetExportStepInfo
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
ms.openlocfilehash: 9d195c61d95f084c7b6b40d2c81623fd81cd94cf
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206352"
---
# <a name="icordebugprocess6getexportstepinfo-method"></a><span data-ttu-id="96802-102">Método ICorDebugProcess6::GetExportStepInfo</span><span class="sxs-lookup"><span data-stu-id="96802-102">ICorDebugProcess6::GetExportStepInfo Method</span></span>
<span data-ttu-id="96802-103">Proporciona información sobre las funciones exportadas en tiempo de ejecución para ayudar a recorrer el código administrado.</span><span class="sxs-lookup"><span data-stu-id="96802-103">Provides information on runtime exported functions to help step through managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96802-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="96802-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,
    [out] CorDebugCodeInvokeKind* pInvokeKind,
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96802-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="96802-105">Parameters</span></span>  
 <span data-ttu-id="96802-106">pszExportName</span><span class="sxs-lookup"><span data-stu-id="96802-106">pszExportName</span></span>  
 <span data-ttu-id="96802-107">[in] Nombre de una función de exportación en tiempo de ejecución según aparece escrito en la tabla de exportación de PE.</span><span class="sxs-lookup"><span data-stu-id="96802-107">[in] The name of a runtime export function as written in the PE export table.</span></span>  
  
 <span data-ttu-id="96802-108">invokeKind</span><span class="sxs-lookup"><span data-stu-id="96802-108">invokeKind</span></span>  
 <span data-ttu-id="96802-109">enuncia Un puntero a un miembro de la enumeración [CorDebugCodeInvokeKind](cordebugcodeinvokekind-enumeration.md) que describe cómo la función exportada llamará al código administrado.</span><span class="sxs-lookup"><span data-stu-id="96802-109">[out] A pointer to a member of the [CorDebugCodeInvokeKind](cordebugcodeinvokekind-enumeration.md) enumeration that describes how the exported function will invoke managed code.</span></span>  
  
 <span data-ttu-id="96802-110">invokePurpose</span><span class="sxs-lookup"><span data-stu-id="96802-110">invokePurpose</span></span>  
 <span data-ttu-id="96802-111">enuncia Un puntero a un miembro de la enumeración [CorDebugCodeInvokePurpose](cordebugcodeinvokepurpose-enumeration.md) que describe por qué la función exportada llamará al código administrado.</span><span class="sxs-lookup"><span data-stu-id="96802-111">[out] A pointer to a member of the [CorDebugCodeInvokePurpose](cordebugcodeinvokepurpose-enumeration.md) enumeration that describes why the exported function will call managed code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="96802-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="96802-112">Return Value</span></span>  
 <span data-ttu-id="96802-113">El método puede devolver los valores enumerados en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="96802-113">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="96802-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="96802-114">Return value</span></span>|<span data-ttu-id="96802-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="96802-115">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="96802-116">La llamada al método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="96802-116">The method call was successful.</span></span>|  
|`E_POINTER`|<span data-ttu-id="96802-117">`pInvokeKind`o `pInvokePurpose` es **null**.</span><span class="sxs-lookup"><span data-stu-id="96802-117">`pInvokeKind` or `pInvokePurpose` is **null**.</span></span>|  
|<span data-ttu-id="96802-118">Otros valores de error de `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="96802-118">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="96802-119">Según el caso.</span><span class="sxs-lookup"><span data-stu-id="96802-119">As appropriate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96802-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="96802-120">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="96802-121">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="96802-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96802-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="96802-122">Requirements</span></span>  
 <span data-ttu-id="96802-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96802-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96802-124">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96802-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96802-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96802-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96802-126">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96802-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96802-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="96802-127">See also</span></span>

- [<span data-ttu-id="96802-128">Interfaz ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="96802-128">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="96802-129">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="96802-129">Debugging Interfaces</span></span>](debugging-interfaces.md)

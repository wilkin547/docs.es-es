---
title: ICorDebugType::GetStaticFieldValue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetStaticFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 62eb5d55-53ee-4fb3-8d47-7b6c96808f9e
topic_type:
- apiref
ms.openlocfilehash: 83ac91133b226e2ac263356941c3fc3288355e7e
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379939"
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a><span data-ttu-id="81df8-102">ICorDebugType::GetStaticFieldValue (Método)</span><span class="sxs-lookup"><span data-stu-id="81df8-102">ICorDebugType::GetStaticFieldValue Method</span></span>
<span data-ttu-id="81df8-103">Obtiene un puntero de interfaz a un objeto ICorDebugValue que contiene el valor del campo estático al que hace referencia el token de campo especificado en el marco de pila especificado.</span><span class="sxs-lookup"><span data-stu-id="81df8-103">Gets an interface pointer to an ICorDebugValue object that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81df8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="81df8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81df8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="81df8-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="81df8-106">de Un `mdFieldDef` token que especifica el campo estático.</span><span class="sxs-lookup"><span data-stu-id="81df8-106">[in] An `mdFieldDef` token that specifies the static field.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="81df8-107">de Un puntero a un ICorDebugFrame que representa el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="81df8-107">[in] A pointer to an ICorDebugFrame that represents the stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="81df8-108">enuncia Un puntero a la dirección de un `ICorDebugValue` que contiene el valor del campo estático.</span><span class="sxs-lookup"><span data-stu-id="81df8-108">[out] A pointer to the address of an `ICorDebugValue` that contains the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81df8-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="81df8-109">Remarks</span></span>  
 <span data-ttu-id="81df8-110">El `GetStaticFieldValue` método solo se puede usar si el tipo es ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, tal y como se indica en el método [ICorDebugType:: GetType](icordebugtype-gettype-method.md) .</span><span class="sxs-lookup"><span data-stu-id="81df8-110">The `GetStaticFieldValue` method may be used only if the type is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, as indicated by the [ICorDebugType::GetType](icordebugtype-gettype-method.md) method.</span></span>  
  
 <span data-ttu-id="81df8-111">En el caso de los tipos no genéricos, la operación realizada por `GetStaticFieldValue` es idéntica a llamar a [ICorDebugClass:: GetStaticFieldValue](icordebugclass-getstaticfieldvalue-method.md) en el objeto ICorDebugClass que devuelve [ICorDebugType:: GetClass](icordebugtype-getclass-method.md).</span><span class="sxs-lookup"><span data-stu-id="81df8-111">For non-generic types, the operation performed by `GetStaticFieldValue` is identical to calling [ICorDebugClass::GetStaticFieldValue](icordebugclass-getstaticfieldvalue-method.md) on the ICorDebugClass object that is returned by [ICorDebugType::GetClass](icordebugtype-getclass-method.md).</span></span>  
  
 <span data-ttu-id="81df8-112">En el caso de los tipos genéricos, un valor de campo estático será relativo a una instancia determinada.</span><span class="sxs-lookup"><span data-stu-id="81df8-112">For generic types, a static field value will be relative to a particular instantiation.</span></span> <span data-ttu-id="81df8-113">Además, si el campo estático podría ser relacionado con un subproceso, un contexto o un dominio de aplicación, el marco de pila ayudará al depurador a determinar el valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="81df8-113">Also, if the static field could possibly be relative to a thread, a context, or an application domain, then the stack frame will help the debugger determine the proper value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81df8-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="81df8-114">Remarks</span></span>  
 <span data-ttu-id="81df8-115">`GetStaticFieldValue`solo se puede usar cuando una llamada a `ICorDebugType::GetType` devuelve un valor de ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE.</span><span class="sxs-lookup"><span data-stu-id="81df8-115">`GetStaticFieldValue` can be used only when a call to `ICorDebugType::GetType` returns a value of ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81df8-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="81df8-116">Requirements</span></span>  
 <span data-ttu-id="81df8-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81df8-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81df8-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="81df8-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="81df8-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81df8-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81df8-120">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81df8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

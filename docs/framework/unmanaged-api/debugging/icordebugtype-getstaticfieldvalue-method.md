---
description: 'Más información acerca de: ICorDebugType:: GetStaticFieldValue (método)'
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
ms.openlocfilehash: 378c72f24fedd76f40704ff684781bed124055bb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658235"
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a><span data-ttu-id="19af7-103">ICorDebugType::GetStaticFieldValue (Método)</span><span class="sxs-lookup"><span data-stu-id="19af7-103">ICorDebugType::GetStaticFieldValue Method</span></span>

<span data-ttu-id="19af7-104">Obtiene un puntero de interfaz a un objeto ICorDebugValue que contiene el valor del campo estático al que hace referencia el token de campo especificado en el marco de pila especificado.</span><span class="sxs-lookup"><span data-stu-id="19af7-104">Gets an interface pointer to an ICorDebugValue object that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19af7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="19af7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19af7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="19af7-106">Parameters</span></span>  

 `fieldDef`  
 <span data-ttu-id="19af7-107">de Un `mdFieldDef` token que especifica el campo estático.</span><span class="sxs-lookup"><span data-stu-id="19af7-107">[in] An `mdFieldDef` token that specifies the static field.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="19af7-108">de Un puntero a un ICorDebugFrame que representa el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="19af7-108">[in] A pointer to an ICorDebugFrame that represents the stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="19af7-109">enuncia Un puntero a la dirección de un `ICorDebugValue` que contiene el valor del campo estático.</span><span class="sxs-lookup"><span data-stu-id="19af7-109">[out] A pointer to the address of an `ICorDebugValue` that contains the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19af7-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="19af7-110">Remarks</span></span>  

 <span data-ttu-id="19af7-111">El `GetStaticFieldValue` método solo se puede usar si el tipo es ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, tal y como se indica en el método [ICorDebugType:: GetType](icordebugtype-gettype-method.md) .</span><span class="sxs-lookup"><span data-stu-id="19af7-111">The `GetStaticFieldValue` method may be used only if the type is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, as indicated by the [ICorDebugType::GetType](icordebugtype-gettype-method.md) method.</span></span>  
  
 <span data-ttu-id="19af7-112">En el caso de los tipos no genéricos, la operación realizada por `GetStaticFieldValue` es idéntica a llamar a [ICorDebugClass:: GetStaticFieldValue](icordebugclass-getstaticfieldvalue-method.md) en el objeto ICorDebugClass que devuelve [ICorDebugType:: GetClass](icordebugtype-getclass-method.md).</span><span class="sxs-lookup"><span data-stu-id="19af7-112">For non-generic types, the operation performed by `GetStaticFieldValue` is identical to calling [ICorDebugClass::GetStaticFieldValue](icordebugclass-getstaticfieldvalue-method.md) on the ICorDebugClass object that is returned by [ICorDebugType::GetClass](icordebugtype-getclass-method.md).</span></span>  
  
 <span data-ttu-id="19af7-113">En el caso de los tipos genéricos, un valor de campo estático será relativo a una instancia determinada.</span><span class="sxs-lookup"><span data-stu-id="19af7-113">For generic types, a static field value will be relative to a particular instantiation.</span></span> <span data-ttu-id="19af7-114">Además, si el campo estático podría ser relacionado con un subproceso, un contexto o un dominio de aplicación, el marco de pila ayudará al depurador a determinar el valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="19af7-114">Also, if the static field could possibly be relative to a thread, a context, or an application domain, then the stack frame will help the debugger determine the proper value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19af7-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="19af7-115">Remarks</span></span>  

 <span data-ttu-id="19af7-116">`GetStaticFieldValue` solo se puede usar cuando una llamada a `ICorDebugType::GetType` devuelve un valor de ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE.</span><span class="sxs-lookup"><span data-stu-id="19af7-116">`GetStaticFieldValue` can be used only when a call to `ICorDebugType::GetType` returns a value of ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19af7-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="19af7-117">Requirements</span></span>  

 <span data-ttu-id="19af7-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19af7-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19af7-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="19af7-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19af7-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19af7-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19af7-121">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19af7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

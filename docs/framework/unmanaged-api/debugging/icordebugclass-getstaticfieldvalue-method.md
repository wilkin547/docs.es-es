---
title: ICorDebugClass::GetStaticFieldValue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetStaticFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 56e718b4-fabd-418b-a5b3-3cc33c745683
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b67f5ec233679461f61715d7562b47c2a195fb8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750856"
---
# <a name="icordebugclassgetstaticfieldvalue-method"></a><span data-ttu-id="dcc30-102">ICorDebugClass::GetStaticFieldValue (Método)</span><span class="sxs-lookup"><span data-stu-id="dcc30-102">ICorDebugClass::GetStaticFieldValue Method</span></span>
<span data-ttu-id="dcc30-103">Obtiene el valor del campo estático especificado.</span><span class="sxs-lookup"><span data-stu-id="dcc30-103">Gets the value of the specified static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcc30-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dcc30-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef         fieldDef,  
    [in]  ICorDebugFrame     *pFrame,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dcc30-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dcc30-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="dcc30-106">[in] Un campo `Def` símbolo (token) que hace referencia al campo que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="dcc30-106">[in] A field `Def` token that references the field to be retrieved.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="dcc30-107">[in] Un puntero a un objeto ICorDebugFrame que representa el marco que se usará para eliminar la ambigüedad entre subprocesos, contexto o variables estáticas del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="dcc30-107">[in] A pointer to an ICorDebugFrame object that represents the frame to be used to disambiguate among thread, context, or application domain statics.</span></span>  
  
 <span data-ttu-id="dcc30-108">Si el campo estático es relativo a un subproceso, un contexto o un dominio de aplicación, el marco determinará el valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="dcc30-108">If the static field is relative to a thread, a context, or an application domain, the frame will determine the proper value.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="dcc30-109">[out] Un puntero a la dirección de un objeto ICorDebugValue que representa el valor del campo estático.</span><span class="sxs-lookup"><span data-stu-id="dcc30-109">[out] A pointer to the address of an ICorDebugValue object that represents the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dcc30-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dcc30-110">Remarks</span></span>  
 <span data-ttu-id="dcc30-111">Para tipos parametrizados, el valor de un campo estático es relativo a la creación de instancias concreto.</span><span class="sxs-lookup"><span data-stu-id="dcc30-111">For parameterized types, the value of a static field is relative to the particular instantiation.</span></span> <span data-ttu-id="dcc30-112">Por lo tanto, si el constructor de clase toma los parámetros de tipo <xref:System.Type>, llame a [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md) en lugar de `ICorDebugClass::GetStaticFieldValue`.</span><span class="sxs-lookup"><span data-stu-id="dcc30-112">Therefore, if the class constructor takes parameters of type <xref:System.Type>, call [ICorDebugType::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md) instead of `ICorDebugClass::GetStaticFieldValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcc30-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dcc30-113">Requirements</span></span>  
 <span data-ttu-id="dcc30-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcc30-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcc30-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dcc30-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dcc30-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dcc30-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dcc30-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcc30-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

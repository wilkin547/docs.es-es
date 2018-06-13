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
ms.openlocfilehash: 4d3c3c0c5634653d14577de9a1334048d75216b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405631"
---
# <a name="icordebugclassgetstaticfieldvalue-method"></a><span data-ttu-id="79ef8-102">ICorDebugClass::GetStaticFieldValue (Método)</span><span class="sxs-lookup"><span data-stu-id="79ef8-102">ICorDebugClass::GetStaticFieldValue Method</span></span>
<span data-ttu-id="79ef8-103">Obtiene el valor del campo estático especificado.</span><span class="sxs-lookup"><span data-stu-id="79ef8-103">Gets the value of the specified static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79ef8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="79ef8-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef         fieldDef,  
    [in]  ICorDebugFrame     *pFrame,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="79ef8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="79ef8-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="79ef8-106">[in] Un campo `Def` símbolo (token) que hace referencia al campo que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="79ef8-106">[in] A field `Def` token that references the field to be retrieved.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="79ef8-107">[in] Un puntero a un objeto ICorDebugFrame que representa el marco que se usará para eliminar la ambigüedad entre subprocesos, de contexto o campos estáticos del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="79ef8-107">[in] A pointer to an ICorDebugFrame object that represents the frame to be used to disambiguate among thread, context, or application domain statics.</span></span>  
  
 <span data-ttu-id="79ef8-108">Si el campo estático es relativo a un subproceso, un contexto o un dominio de aplicación, el marco determinará el valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="79ef8-108">If the static field is relative to a thread, a context, or an application domain, the frame will determine the proper value.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="79ef8-109">[out] Un puntero a la dirección de un objeto ICorDebugValue que representa el valor del campo estático.</span><span class="sxs-lookup"><span data-stu-id="79ef8-109">[out] A pointer to the address of an ICorDebugValue object that represents the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79ef8-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="79ef8-110">Remarks</span></span>  
 <span data-ttu-id="79ef8-111">Para tipos parametrizados, el valor de un campo estático es relativo a la creación de instancias determinada.</span><span class="sxs-lookup"><span data-stu-id="79ef8-111">For parameterized types, the value of a static field is relative to the particular instantiation.</span></span> <span data-ttu-id="79ef8-112">Por lo tanto, si el constructor de clase toma parámetros de tipo <xref:System.Type>, llame a [ICorDebugType:: GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md) en lugar de `ICorDebugClass::GetStaticFieldValue`.</span><span class="sxs-lookup"><span data-stu-id="79ef8-112">Therefore, if the class constructor takes parameters of type <xref:System.Type>, call [ICorDebugType::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md) instead of `ICorDebugClass::GetStaticFieldValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79ef8-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="79ef8-113">Requirements</span></span>  
 <span data-ttu-id="79ef8-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79ef8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79ef8-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="79ef8-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="79ef8-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79ef8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79ef8-117">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79ef8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

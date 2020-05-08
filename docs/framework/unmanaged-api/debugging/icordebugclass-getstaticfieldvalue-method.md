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
ms.openlocfilehash: d4a254853256e1a1440f5588418b94e39eabcc9a
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894106"
---
# <a name="icordebugclassgetstaticfieldvalue-method"></a><span data-ttu-id="1f13b-102">ICorDebugClass::GetStaticFieldValue (Método)</span><span class="sxs-lookup"><span data-stu-id="1f13b-102">ICorDebugClass::GetStaticFieldValue Method</span></span>
<span data-ttu-id="1f13b-103">Obtiene el valor del campo estático especificado.</span><span class="sxs-lookup"><span data-stu-id="1f13b-103">Gets the value of the specified static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f13b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1f13b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef         fieldDef,  
    [in]  ICorDebugFrame     *pFrame,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f13b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1f13b-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="1f13b-106">de Símbolo ( `Def` token) de campo que hace referencia al campo que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="1f13b-106">[in] A field `Def` token that references the field to be retrieved.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="1f13b-107">de Un puntero a un objeto ICorDebugFrame que representa el marco que se va a utilizar para eliminar la ambigüedad entre el subproceso, el contexto o los estáticos del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="1f13b-107">[in] A pointer to an ICorDebugFrame object that represents the frame to be used to disambiguate among thread, context, or application domain statics.</span></span>  
  
 <span data-ttu-id="1f13b-108">Si el campo estático es relativo a un subproceso, un contexto o un dominio de aplicación, el marco determinará el valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="1f13b-108">If the static field is relative to a thread, a context, or an application domain, the frame will determine the proper value.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="1f13b-109">enuncia Puntero a la dirección de un objeto ICorDebugValue que representa el valor del campo estático.</span><span class="sxs-lookup"><span data-stu-id="1f13b-109">[out] A pointer to the address of an ICorDebugValue object that represents the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f13b-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1f13b-110">Remarks</span></span>  
 <span data-ttu-id="1f13b-111">En el caso de los tipos parametrizados, el valor de un campo estático es relativo a la creación de instancias concreta.</span><span class="sxs-lookup"><span data-stu-id="1f13b-111">For parameterized types, the value of a static field is relative to the particular instantiation.</span></span> <span data-ttu-id="1f13b-112">Por consiguiente, si el constructor de clase toma parámetros <xref:System.Type>de tipo, llame a [ICorDebugType:: GetStaticFieldValue](icordebugtype-getstaticfieldvalue-method.md) en lugar de `ICorDebugClass::GetStaticFieldValue`a.</span><span class="sxs-lookup"><span data-stu-id="1f13b-112">Therefore, if the class constructor takes parameters of type <xref:System.Type>, call [ICorDebugType::GetStaticFieldValue](icordebugtype-getstaticfieldvalue-method.md) instead of `ICorDebugClass::GetStaticFieldValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f13b-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1f13b-113">Requirements</span></span>  
 <span data-ttu-id="1f13b-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f13b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f13b-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f13b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f13b-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f13b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f13b-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f13b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

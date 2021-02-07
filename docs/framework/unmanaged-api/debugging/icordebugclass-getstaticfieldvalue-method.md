---
description: 'Más información acerca de: ICorDebugClass:: GetStaticFieldValue (método)'
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
ms.openlocfilehash: a5406e44491ce89030731c35752066e4943cebfc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711529"
---
# <a name="icordebugclassgetstaticfieldvalue-method"></a><span data-ttu-id="4f7fa-103">ICorDebugClass::GetStaticFieldValue (Método)</span><span class="sxs-lookup"><span data-stu-id="4f7fa-103">ICorDebugClass::GetStaticFieldValue Method</span></span>

<span data-ttu-id="4f7fa-104">Obtiene el valor del campo estático especificado.</span><span class="sxs-lookup"><span data-stu-id="4f7fa-104">Gets the value of the specified static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f7fa-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f7fa-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef         fieldDef,  
    [in]  ICorDebugFrame     *pFrame,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f7fa-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4f7fa-106">Parameters</span></span>  

 `fieldDef`  
 <span data-ttu-id="4f7fa-107">de `Def` Símbolo (token) de campo que hace referencia al campo que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="4f7fa-107">[in] A field `Def` token that references the field to be retrieved.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="4f7fa-108">de Un puntero a un objeto ICorDebugFrame que representa el marco que se va a utilizar para eliminar la ambigüedad entre el subproceso, el contexto o los estáticos del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f7fa-108">[in] A pointer to an ICorDebugFrame object that represents the frame to be used to disambiguate among thread, context, or application domain statics.</span></span>  
  
 <span data-ttu-id="4f7fa-109">Si el campo estático es relativo a un subproceso, un contexto o un dominio de aplicación, el marco determinará el valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="4f7fa-109">If the static field is relative to a thread, a context, or an application domain, the frame will determine the proper value.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="4f7fa-110">enuncia Puntero a la dirección de un objeto ICorDebugValue que representa el valor del campo estático.</span><span class="sxs-lookup"><span data-stu-id="4f7fa-110">[out] A pointer to the address of an ICorDebugValue object that represents the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f7fa-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4f7fa-111">Remarks</span></span>  

 <span data-ttu-id="4f7fa-112">En el caso de los tipos parametrizados, el valor de un campo estático es relativo a la creación de instancias concreta.</span><span class="sxs-lookup"><span data-stu-id="4f7fa-112">For parameterized types, the value of a static field is relative to the particular instantiation.</span></span> <span data-ttu-id="4f7fa-113">Por consiguiente, si el constructor de clase toma parámetros de tipo <xref:System.Type> , llame a [ICorDebugType:: GetStaticFieldValue](icordebugtype-getstaticfieldvalue-method.md) en lugar de a `ICorDebugClass::GetStaticFieldValue` .</span><span class="sxs-lookup"><span data-stu-id="4f7fa-113">Therefore, if the class constructor takes parameters of type <xref:System.Type>, call [ICorDebugType::GetStaticFieldValue](icordebugtype-getstaticfieldvalue-method.md) instead of `ICorDebugClass::GetStaticFieldValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f7fa-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4f7fa-114">Requirements</span></span>  

 <span data-ttu-id="4f7fa-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f7fa-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f7fa-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f7fa-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f7fa-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f7fa-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f7fa-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f7fa-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

---
title: ICorDebugModule::GetName (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetName
helpviewer_keywords:
- ICorDebugModule::GetName method [.NET Framework debugging]
- GetName method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: db499637-7ba9-421e-b8b1-35856995e80b
topic_type:
- apiref
ms.openlocfilehash: 55342c803756aa10c2e7c835d9e1d58b439bb36c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212547"
---
# <a name="icordebugmodulegetname-method"></a><span data-ttu-id="1968f-102">ICorDebugModule::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="1968f-102">ICorDebugModule::GetName Method</span></span>
<span data-ttu-id="1968f-103">Obtiene el nombre de archivo del módulo.</span><span class="sxs-lookup"><span data-stu-id="1968f-103">Gets the file name of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1968f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1968f-104">Syntax</span></span>  
  
```cpp
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1968f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1968f-105">Parameters</span></span>  
 `cchname`  
 <span data-ttu-id="1968f-106">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="1968f-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="1968f-107">de Puntero a la longitud del nombre devuelto.</span><span class="sxs-lookup"><span data-stu-id="1968f-107">[in] A pointer to the length of the returned name.</span></span>  
  
 `szName`  
 <span data-ttu-id="1968f-108">enuncia Matriz que almacena el nombre devuelto.</span><span class="sxs-lookup"><span data-stu-id="1968f-108">[out] An array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1968f-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1968f-109">Remarks</span></span>  
 <span data-ttu-id="1968f-110">El `GetName` método devuelve un S_OK HRESULT si el nombre de archivo del módulo coincide con el nombre en el disco.</span><span class="sxs-lookup"><span data-stu-id="1968f-110">The `GetName` method returns an S_OK HRESULT if the module's file name matches the name on disk.</span></span> <span data-ttu-id="1968f-111">`GetName`Devuelve un S_FALSE HRESULT si se ha fabricado el nombre, por ejemplo para un módulo dinámico o en memoria.</span><span class="sxs-lookup"><span data-stu-id="1968f-111">`GetName` returns an S_FALSE HRESULT if the name is fabricated, such as for a dynamic or in-memory module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1968f-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1968f-112">Requirements</span></span>  
 <span data-ttu-id="1968f-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1968f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1968f-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1968f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1968f-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1968f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1968f-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1968f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1968f-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1968f-117">See also</span></span>

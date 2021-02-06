---
description: 'Más información acerca de: ICorDebugModule:: GetName (método)'
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
ms.openlocfilehash: 0f81271b2be283621027f4c835b6f220a383d771
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660218"
---
# <a name="icordebugmodulegetname-method"></a><span data-ttu-id="dcf5b-103">ICorDebugModule::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="dcf5b-103">ICorDebugModule::GetName Method</span></span>

<span data-ttu-id="dcf5b-104">Obtiene el nombre de archivo del módulo.</span><span class="sxs-lookup"><span data-stu-id="dcf5b-104">Gets the file name of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcf5b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dcf5b-105">Syntax</span></span>  
  
```cpp
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dcf5b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dcf5b-106">Parameters</span></span>  

 `cchname`  
 <span data-ttu-id="dcf5b-107">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="dcf5b-107">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="dcf5b-108">de Puntero a la longitud del nombre devuelto.</span><span class="sxs-lookup"><span data-stu-id="dcf5b-108">[in] A pointer to the length of the returned name.</span></span>  
  
 `szName`  
 <span data-ttu-id="dcf5b-109">enuncia Matriz que almacena el nombre devuelto.</span><span class="sxs-lookup"><span data-stu-id="dcf5b-109">[out] An array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dcf5b-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dcf5b-110">Remarks</span></span>  

 <span data-ttu-id="dcf5b-111">El `GetName` método devuelve un S_OK HRESULT si el nombre de archivo del módulo coincide con el nombre en el disco.</span><span class="sxs-lookup"><span data-stu-id="dcf5b-111">The `GetName` method returns an S_OK HRESULT if the module's file name matches the name on disk.</span></span> <span data-ttu-id="dcf5b-112">`GetName` Devuelve un S_FALSE HRESULT si se ha fabricado el nombre, por ejemplo para un módulo dinámico o en memoria.</span><span class="sxs-lookup"><span data-stu-id="dcf5b-112">`GetName` returns an S_FALSE HRESULT if the name is fabricated, such as for a dynamic or in-memory module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcf5b-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dcf5b-113">Requirements</span></span>  

 <span data-ttu-id="dcf5b-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcf5b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcf5b-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dcf5b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dcf5b-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dcf5b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dcf5b-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcf5b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcf5b-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="dcf5b-118">See also</span></span>

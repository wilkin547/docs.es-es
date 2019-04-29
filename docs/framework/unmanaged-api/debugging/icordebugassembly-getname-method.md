---
title: ICorDebugAssembly::GetName (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetName
helpviewer_keywords:
- ICorDebugAssembly::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: cdeda721-b214-4503-a291-c70b68b5f36b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3077e0494816a083d97839d66d06b18130e5dac8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645583"
---
# <a name="icordebugassemblygetname-method"></a><span data-ttu-id="abf10-102">ICorDebugAssembly::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="abf10-102">ICorDebugAssembly::GetName Method</span></span>
<span data-ttu-id="abf10-103">Obtiene el nombre del ensamblado que esto `ICorDebugAssembly` representa la instancia.</span><span class="sxs-lookup"><span data-stu-id="abf10-103">Gets the name of the assembly that this `ICorDebugAssembly` instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abf10-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="abf10-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in] ULONG32  cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="abf10-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="abf10-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="abf10-106">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="abf10-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="abf10-107">[out] Un puntero a un entero que especifica la longitud del nombre real.</span><span class="sxs-lookup"><span data-stu-id="abf10-107">[out] A pointer to an integer that specifies the actual length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="abf10-108">[out] Una matriz que almacena el nombre.</span><span class="sxs-lookup"><span data-stu-id="abf10-108">[out] An array that stores the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="abf10-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="abf10-109">Remarks</span></span>  
 <span data-ttu-id="abf10-110">El `GetName` método devuelve la ruta de acceso y el nombre completo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="abf10-110">The `GetName` method returns the full path and file name of the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abf10-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="abf10-111">Requirements</span></span>  
 <span data-ttu-id="abf10-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="abf10-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abf10-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="abf10-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="abf10-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="abf10-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="abf10-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abf10-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

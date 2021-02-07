---
description: 'Más información acerca de: ICorDebugAssembly:: GetName (método)'
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
ms.openlocfilehash: c2ffa910eaf97c5539a33dbcd3486b7dfb117b51
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711991"
---
# <a name="icordebugassemblygetname-method"></a><span data-ttu-id="7d1d6-103">ICorDebugAssembly::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="7d1d6-103">ICorDebugAssembly::GetName Method</span></span>

<span data-ttu-id="7d1d6-104">Obtiene el nombre del ensamblado que esta `ICorDebugAssembly` instancia representa.</span><span class="sxs-lookup"><span data-stu-id="7d1d6-104">Gets the name of the assembly that this `ICorDebugAssembly` instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d1d6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7d1d6-105">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in] ULONG32  cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d1d6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7d1d6-106">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="7d1d6-107">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="7d1d6-107">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="7d1d6-108">enuncia Puntero a un entero que especifica la longitud real del nombre.</span><span class="sxs-lookup"><span data-stu-id="7d1d6-108">[out] A pointer to an integer that specifies the actual length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="7d1d6-109">enuncia Matriz que almacena el nombre.</span><span class="sxs-lookup"><span data-stu-id="7d1d6-109">[out] An array that stores the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d1d6-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7d1d6-110">Remarks</span></span>  

 <span data-ttu-id="7d1d6-111">El `GetName` método devuelve la ruta de acceso completa y el nombre de archivo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7d1d6-111">The `GetName` method returns the full path and file name of the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d1d6-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7d1d6-112">Requirements</span></span>  

 <span data-ttu-id="7d1d6-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d1d6-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d1d6-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7d1d6-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7d1d6-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d1d6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d1d6-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d1d6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

---
title: Método de ICorDebugLoadedModule::GetName
ms.date: 03/30/2017
ms.assetid: 88c304d5-edaa-4c0e-a8e1-144e8a76877e
ms.openlocfilehash: c18af45184f5a9485e13b9d4789bff2c570834cc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731857"
---
# <a name="icordebugloadedmodulegetname-method"></a><span data-ttu-id="cd168-102">Método de ICorDebugLoadedModule::GetName</span><span class="sxs-lookup"><span data-stu-id="cd168-102">ICorDebugLoadedModule::GetName Method</span></span>

<span data-ttu-id="cd168-103">Obtiene el nombre del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="cd168-103">Gets the name of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd168-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cd168-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,  
   [out] ULONG32 *pcchName,  
   [out, size_is(cchName),  
   length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd168-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cd168-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="cd168-106">[in] Número de caracteres del búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="cd168-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="cd168-107">[out] Puntero al número de caracteres escritos realmente en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="cd168-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="cd168-108">[out] Matriz de caracteres que contiene el nombre del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="cd168-108">[out] An array of characters that contain the name of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd168-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cd168-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cd168-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="cd168-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd168-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cd168-111">Requirements</span></span>  

 <span data-ttu-id="cd168-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd168-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd168-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd168-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd168-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd168-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd168-115">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd168-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd168-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cd168-116">See also</span></span>

- [<span data-ttu-id="cd168-117">Interfaz de ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="cd168-117">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="cd168-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="cd168-118">Debugging Interfaces</span></span>](debugging-interfaces.md)

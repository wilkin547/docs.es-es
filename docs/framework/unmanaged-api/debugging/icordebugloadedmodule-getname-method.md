---
description: 'Más información acerca de: ICorDebugLoadedModule:: GetName (método)'
title: Método de ICorDebugLoadedModule::GetName
ms.date: 03/30/2017
ms.assetid: 88c304d5-edaa-4c0e-a8e1-144e8a76877e
ms.openlocfilehash: 40a0715b513115177cabac01727ce9166a40d50b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801259"
---
# <a name="icordebugloadedmodulegetname-method"></a><span data-ttu-id="a83b3-103">Método de ICorDebugLoadedModule::GetName</span><span class="sxs-lookup"><span data-stu-id="a83b3-103">ICorDebugLoadedModule::GetName Method</span></span>

<span data-ttu-id="a83b3-104">Obtiene el nombre del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="a83b3-104">Gets the name of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a83b3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a83b3-105">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,  
   [out] ULONG32 *pcchName,  
   [out, size_is(cchName),  
   length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a83b3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a83b3-106">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="a83b3-107">[in] Número de caracteres del búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="a83b3-107">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="a83b3-108">[out] Puntero al número de caracteres escritos realmente en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="a83b3-108">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="a83b3-109">[out] Matriz de caracteres que contiene el nombre del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="a83b3-109">[out] An array of characters that contain the name of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a83b3-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a83b3-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a83b3-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a83b3-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a83b3-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a83b3-112">Requirements</span></span>  

 <span data-ttu-id="a83b3-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a83b3-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a83b3-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a83b3-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a83b3-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a83b3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a83b3-116">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a83b3-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a83b3-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="a83b3-117">See also</span></span>

- [<span data-ttu-id="a83b3-118">Interfaz de ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="a83b3-118">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="a83b3-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a83b3-119">Debugging Interfaces</span></span>](debugging-interfaces.md)

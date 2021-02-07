---
description: 'Más información sobre: método icordebugdatatarget2:: GetImageLocation (método)'
title: Método ICorDebugDataTarget2::GetImageLocation
ms.date: 03/30/2017
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
ms.openlocfilehash: f79ba89d3ba467c2e81224d64147c2b5dd5db079
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710496"
---
# <a name="icordebugdatatarget2getimagelocation-method"></a><span data-ttu-id="2c402-103">Método ICorDebugDataTarget2::GetImageLocation</span><span class="sxs-lookup"><span data-stu-id="2c402-103">ICorDebugDataTarget2::GetImageLocation Method</span></span>

<span data-ttu-id="2c402-104">Devuelve la ruta de acceso de un módulo a partir de la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="2c402-104">Returns the path of a module from the module's base address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c402-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2c402-105">Syntax</span></span>  
  
```cpp  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c402-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2c402-106">Parameters</span></span>  

 `baseAddress`  
 <span data-ttu-id="2c402-107">de [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) valor que representa la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="2c402-107">[in] A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `cchName`  
 <span data-ttu-id="2c402-108">[in] Número de caracteres en el búfer que va a recibir la ruta de acceso del módulo.</span><span class="sxs-lookup"><span data-stu-id="2c402-108">[in] The number of characters in the buffer that is to receive the module path.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="2c402-109">[out] Puntero al número de caracteres escritos en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="2c402-109">[out] A pointer to the number of characters written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="2c402-110">[out] Ruta de acceso del módulo.</span><span class="sxs-lookup"><span data-stu-id="2c402-110">[out] The path of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c402-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2c402-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2c402-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="2c402-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c402-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2c402-113">Requirements</span></span>  

 <span data-ttu-id="2c402-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c402-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c402-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c402-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c402-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c402-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c402-117">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c402-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c402-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c402-118">See also</span></span>

- [<span data-ttu-id="2c402-119">Interfaz ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="2c402-119">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="2c402-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="2c402-120">Debugging Interfaces</span></span>](debugging-interfaces.md)

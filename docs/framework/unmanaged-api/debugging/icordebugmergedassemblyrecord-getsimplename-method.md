---
description: 'Más información sobre: ICorDebugMergedAssemblyRecord:: GetSimpleName (método)'
title: ICorDebugMergedAssemblyRecord::GetSimpleNam (método)
ms.date: 03/30/2017
ms.assetid: bc3410f6-ebca-4bca-9b45-fc38c74fa9cb
ms.openlocfilehash: e77a5cc7df009a5bc55a7eb952ead80e5f81f271
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650396"
---
# <a name="icordebugmergedassemblyrecordgetsimplename-method"></a><span data-ttu-id="55861-103">ICorDebugMergedAssemblyRecord::GetSimpleNam (método)</span><span class="sxs-lookup"><span data-stu-id="55861-103">ICorDebugMergedAssemblyRecord::GetSimpleName Method</span></span>

<span data-ttu-id="55861-104">Obtiene el nombre simple del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="55861-104">Gets the simple name of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55861-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="55861-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSimpleName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55861-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="55861-106">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="55861-107">[in] Número de caracteres del búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="55861-107">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="55861-108">[out] Puntero al número de caracteres escritos realmente en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="55861-108">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="55861-109">Puntero a una matriz de caracteres.</span><span class="sxs-lookup"><span data-stu-id="55861-109">A pointer to a character array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55861-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="55861-110">Remarks</span></span>  

 <span data-ttu-id="55861-111">Este método recupera el nombre sencillo de un ensamblado (por ejemplo, "System.Collections"), sin una extensión de archivo, versión, referencia cultural o el token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="55861-111">This method retrieves the simple name of an assembly (such as "System.Collections"), without a file extension, version, culture, or public key token.</span></span> <span data-ttu-id="55861-112">Se corresponde con la propiedad <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> en código administrado.</span><span class="sxs-lookup"><span data-stu-id="55861-112">It corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property in managed code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="55861-113">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="55861-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55861-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="55861-114">Requirements</span></span>  

 <span data-ttu-id="55861-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55861-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55861-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="55861-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55861-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55861-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55861-118">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55861-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55861-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="55861-119">See also</span></span>

- [<span data-ttu-id="55861-120">Interfaz ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="55861-120">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="55861-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="55861-121">Debugging Interfaces</span></span>](debugging-interfaces.md)

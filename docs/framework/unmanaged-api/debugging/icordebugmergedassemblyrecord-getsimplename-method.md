---
title: ICorDebugMergedAssemblyRecord::GetSimpleNam (método)
ms.date: 03/30/2017
ms.assetid: bc3410f6-ebca-4bca-9b45-fc38c74fa9cb
ms.openlocfilehash: 99ba27171e129e8725c3e0555a6991ef08b893da
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178715"
---
# <a name="icordebugmergedassemblyrecordgetsimplename-method"></a><span data-ttu-id="7793f-102">ICorDebugMergedAssemblyRecord::GetSimpleNam (método)</span><span class="sxs-lookup"><span data-stu-id="7793f-102">ICorDebugMergedAssemblyRecord::GetSimpleName Method</span></span>
<span data-ttu-id="7793f-103">Obtiene el nombre simple del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7793f-103">Gets the simple name of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7793f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7793f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSimpleName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7793f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7793f-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="7793f-106">[in] Número de caracteres del búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="7793f-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="7793f-107">[out] Puntero al número de caracteres escritos realmente en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="7793f-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="7793f-108">Puntero a una matriz de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7793f-108">A pointer to a character array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7793f-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7793f-109">Remarks</span></span>  
 <span data-ttu-id="7793f-110">Este método recupera el nombre sencillo de un ensamblado (por ejemplo, "System.Collections"), sin una extensión de archivo, versión, referencia cultural o el token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="7793f-110">This method retrieves the simple name of an assembly (such as "System.Collections"), without a file extension, version, culture, or public key token.</span></span> <span data-ttu-id="7793f-111">Se corresponde con la propiedad <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> en código administrado.</span><span class="sxs-lookup"><span data-stu-id="7793f-111">It corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property in managed code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7793f-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7793f-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7793f-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7793f-113">Requirements</span></span>  
 <span data-ttu-id="7793f-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7793f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7793f-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7793f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7793f-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7793f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7793f-117">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7793f-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7793f-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7793f-118">See also</span></span>

- [<span data-ttu-id="7793f-119">Interfaz ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="7793f-119">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="7793f-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="7793f-120">Debugging Interfaces</span></span>](debugging-interfaces.md)

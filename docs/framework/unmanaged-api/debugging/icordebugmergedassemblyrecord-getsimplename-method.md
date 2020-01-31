---
title: ICorDebugMergedAssemblyRecord::GetSimpleNam (método)
ms.date: 03/30/2017
ms.assetid: bc3410f6-ebca-4bca-9b45-fc38c74fa9cb
ms.openlocfilehash: 21e8ebeabd3b082361ca3307240cfca58835b066
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793095"
---
# <a name="icordebugmergedassemblyrecordgetsimplename-method"></a><span data-ttu-id="9d259-102">ICorDebugMergedAssemblyRecord::GetSimpleNam (método)</span><span class="sxs-lookup"><span data-stu-id="9d259-102">ICorDebugMergedAssemblyRecord::GetSimpleName Method</span></span>
<span data-ttu-id="9d259-103">Obtiene el nombre simple del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9d259-103">Gets the simple name of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d259-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9d259-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSimpleName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d259-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="9d259-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="9d259-106">[in] Número de caracteres del búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="9d259-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="9d259-107">[out] Puntero al número de caracteres escritos realmente en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="9d259-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="9d259-108">Puntero a una matriz de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9d259-108">A pointer to a character array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d259-109">Notas</span><span class="sxs-lookup"><span data-stu-id="9d259-109">Remarks</span></span>  
 <span data-ttu-id="9d259-110">Este método recupera el nombre sencillo de un ensamblado (por ejemplo, "System.Collections"), sin una extensión de archivo, versión, referencia cultural o el token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="9d259-110">This method retrieves the simple name of an assembly (such as "System.Collections"), without a file extension, version, culture, or public key token.</span></span> <span data-ttu-id="9d259-111">Se corresponde con la propiedad <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> en código administrado.</span><span class="sxs-lookup"><span data-stu-id="9d259-111">It corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property in managed code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9d259-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9d259-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d259-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="9d259-113">Requirements</span></span>  
 <span data-ttu-id="9d259-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d259-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d259-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d259-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d259-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d259-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d259-117">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d259-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d259-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d259-118">See also</span></span>

- [<span data-ttu-id="9d259-119">ICorDebugMergedAssemblyRecord (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9d259-119">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="9d259-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="9d259-120">Debugging Interfaces</span></span>](debugging-interfaces.md)

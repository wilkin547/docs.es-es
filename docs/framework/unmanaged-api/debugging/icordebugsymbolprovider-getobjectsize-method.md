---
title: ICorDebugSymbolProvider::GetObjectSize (método)
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
ms.openlocfilehash: fce7410b5ae9571af0c8a5963596e2af41737798
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791567"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="17ffe-102">ICorDebugSymbolProvider::GetObjectSize (método)</span><span class="sxs-lookup"><span data-stu-id="17ffe-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>
<span data-ttu-id="17ffe-103">Devuelve el tamaño del objeto para un objeto basado en su firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="17ffe-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17ffe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="17ffe-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17ffe-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="17ffe-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="17ffe-106">[in] Número de bytes de la firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="17ffe-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="17ffe-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="17ffe-107">typeSig</span></span>  
 <span data-ttu-id="17ffe-108">[in] Firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="17ffe-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="17ffe-109">[out] Puntero al tamaño del objeto.</span><span class="sxs-lookup"><span data-stu-id="17ffe-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17ffe-110">Notas</span><span class="sxs-lookup"><span data-stu-id="17ffe-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="17ffe-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="17ffe-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17ffe-112">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="17ffe-112">Requirements</span></span>  
 <span data-ttu-id="17ffe-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17ffe-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17ffe-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="17ffe-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="17ffe-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17ffe-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17ffe-116">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17ffe-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17ffe-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="17ffe-117">See also</span></span>

- [<span data-ttu-id="17ffe-118">ICorDebugSymbolProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="17ffe-118">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="17ffe-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="17ffe-119">Debugging Interfaces</span></span>](debugging-interfaces.md)

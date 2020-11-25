---
title: ICorDebugSymbolProvider::GetObjectSize (método)
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
ms.openlocfilehash: 4937ff1be7736f98be9efb9b01bdb322bf33e037
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730813"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="d6df5-102">ICorDebugSymbolProvider::GetObjectSize (método)</span><span class="sxs-lookup"><span data-stu-id="d6df5-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>

<span data-ttu-id="d6df5-103">Devuelve el tamaño del objeto para un objeto basado en su firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="d6df5-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6df5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6df5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6df5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d6df5-105">Parameters</span></span>  

 `cbSignature`  
 <span data-ttu-id="d6df5-106">[in] Número de bytes de la firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="d6df5-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="d6df5-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="d6df5-107">typeSig</span></span>  
 <span data-ttu-id="d6df5-108">[in] Firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="d6df5-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="d6df5-109">[out] Puntero al tamaño del objeto.</span><span class="sxs-lookup"><span data-stu-id="d6df5-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6df5-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d6df5-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d6df5-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d6df5-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6df5-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d6df5-112">Requirements</span></span>  

 <span data-ttu-id="d6df5-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6df5-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6df5-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6df5-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6df5-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6df5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6df5-116">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6df5-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6df5-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d6df5-117">See also</span></span>

- [<span data-ttu-id="d6df5-118">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="d6df5-118">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="d6df5-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="d6df5-119">Debugging Interfaces</span></span>](debugging-interfaces.md)

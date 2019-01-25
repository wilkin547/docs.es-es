---
title: ICorDebugSymbolProvider::GetObjectSize (método)
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99714a50d0b3966476cea2f7ed02f04a2ebf6cea
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512416"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="bdcaf-102">ICorDebugSymbolProvider::GetObjectSize (método)</span><span class="sxs-lookup"><span data-stu-id="bdcaf-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>
<span data-ttu-id="bdcaf-103">Devuelve el tamaño del objeto para un objeto basado en su firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="bdcaf-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdcaf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bdcaf-104">Syntax</span></span>  
  
```  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bdcaf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bdcaf-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="bdcaf-106">[in] Número de bytes de la firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="bdcaf-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="bdcaf-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="bdcaf-107">typeSig</span></span>  
 <span data-ttu-id="bdcaf-108">[in] Firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="bdcaf-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="bdcaf-109">[out] Puntero al tamaño del objeto.</span><span class="sxs-lookup"><span data-stu-id="bdcaf-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bdcaf-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bdcaf-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bdcaf-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="bdcaf-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdcaf-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bdcaf-112">Requirements</span></span>  
 <span data-ttu-id="bdcaf-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdcaf-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdcaf-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bdcaf-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bdcaf-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bdcaf-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bdcaf-116">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdcaf-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdcaf-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="bdcaf-117">See also</span></span>
- [<span data-ttu-id="bdcaf-118">ICorDebugSymbolProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bdcaf-118">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="bdcaf-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="bdcaf-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

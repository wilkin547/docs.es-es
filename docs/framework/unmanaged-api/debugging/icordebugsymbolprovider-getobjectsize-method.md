---
title: ICorDebugSymbolProvider::GetObjectSize (método)
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbcdb5541fdd49944f462321dc24131a32a42391
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107294"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="8af9d-102">ICorDebugSymbolProvider::GetObjectSize (método)</span><span class="sxs-lookup"><span data-stu-id="8af9d-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>
<span data-ttu-id="8af9d-103">Devuelve el tamaño del objeto para un objeto basado en su firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="8af9d-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8af9d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8af9d-104">Syntax</span></span>  
  
```  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8af9d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8af9d-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="8af9d-106">[in] Número de bytes de la firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="8af9d-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="8af9d-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="8af9d-107">typeSig</span></span>  
 <span data-ttu-id="8af9d-108">[in] Firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="8af9d-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="8af9d-109">[out] Puntero al tamaño del objeto.</span><span class="sxs-lookup"><span data-stu-id="8af9d-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8af9d-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8af9d-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8af9d-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="8af9d-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8af9d-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8af9d-112">Requirements</span></span>  
 <span data-ttu-id="8af9d-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8af9d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8af9d-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8af9d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8af9d-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8af9d-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="8af9d-116">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="8af9d-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8af9d-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="8af9d-117">See also</span></span>

- [<span data-ttu-id="8af9d-118">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="8af9d-118">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="8af9d-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="8af9d-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

---
title: ICorDebugSymbolProvider::GetObjectSize (método)
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 59054d7b939ab29cb08c30961601a323529ce06b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955628"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="380ad-102">ICorDebugSymbolProvider::GetObjectSize (método)</span><span class="sxs-lookup"><span data-stu-id="380ad-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>
<span data-ttu-id="380ad-103">Devuelve el tamaño del objeto para un objeto basado en su firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="380ad-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="380ad-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="380ad-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="380ad-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="380ad-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="380ad-106">[in] Número de bytes de la firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="380ad-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="380ad-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="380ad-107">typeSig</span></span>  
 <span data-ttu-id="380ad-108">[in] Firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="380ad-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="380ad-109">[out] Puntero al tamaño del objeto.</span><span class="sxs-lookup"><span data-stu-id="380ad-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="380ad-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="380ad-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="380ad-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="380ad-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="380ad-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="380ad-112">Requirements</span></span>  
 <span data-ttu-id="380ad-113">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="380ad-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="380ad-114">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="380ad-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="380ad-115">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="380ad-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="380ad-116">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="380ad-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="380ad-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="380ad-117">See also</span></span>

- [<span data-ttu-id="380ad-118">ICorDebugSymbolProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="380ad-118">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="380ad-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="380ad-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

---
title: ICorDebugSymbolProvider::GetObjectSize (método)
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1da526ac133604fa43081f86988459c4238517c9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421508"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="6ad78-102">ICorDebugSymbolProvider::GetObjectSize (método)</span><span class="sxs-lookup"><span data-stu-id="6ad78-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>
<span data-ttu-id="6ad78-103">Devuelve el tamaño del objeto para un objeto basado en su firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="6ad78-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ad78-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6ad78-104">Syntax</span></span>  
  
```  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6ad78-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6ad78-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="6ad78-106">[in] Número de bytes de la firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="6ad78-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="6ad78-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="6ad78-107">typeSig</span></span>  
 <span data-ttu-id="6ad78-108">[in] Firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="6ad78-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="6ad78-109">[out] Puntero al tamaño del objeto.</span><span class="sxs-lookup"><span data-stu-id="6ad78-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ad78-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6ad78-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ad78-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="6ad78-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ad78-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6ad78-112">Requirements</span></span>  
 <span data-ttu-id="6ad78-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ad78-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ad78-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6ad78-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ad78-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ad78-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ad78-116">**Versiones de .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ad78-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ad78-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ad78-117">See Also</span></span>  
 [<span data-ttu-id="6ad78-118">ICorDebugSymbolProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6ad78-118">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="6ad78-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="6ad78-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

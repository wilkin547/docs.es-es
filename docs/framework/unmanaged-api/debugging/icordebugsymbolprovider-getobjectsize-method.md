---
title: "ICorDebugSymbolProvider::GetObjectSize (método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ea9e0fcae9f98869884ad887a6c24de342512b87
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="d1e69-102">ICorDebugSymbolProvider::GetObjectSize (método)</span><span class="sxs-lookup"><span data-stu-id="d1e69-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>
<span data-ttu-id="d1e69-103">Devuelve el tamaño del objeto para un objeto basado en su firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="d1e69-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1e69-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d1e69-104">Syntax</span></span>  
  
```  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d1e69-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d1e69-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="d1e69-106">[in] Número de bytes de la firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="d1e69-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="d1e69-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="d1e69-107">typeSig</span></span>  
 <span data-ttu-id="d1e69-108">[in] Firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="d1e69-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="d1e69-109">[out] Puntero al tamaño del objeto.</span><span class="sxs-lookup"><span data-stu-id="d1e69-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1e69-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d1e69-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d1e69-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d1e69-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1e69-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d1e69-112">Requirements</span></span>  
 <span data-ttu-id="d1e69-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1e69-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1e69-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1e69-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1e69-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1e69-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1e69-116">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1e69-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1e69-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1e69-117">See Also</span></span>  
 [<span data-ttu-id="d1e69-118">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="d1e69-118">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="d1e69-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="d1e69-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

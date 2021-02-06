---
description: 'Más información sobre: ICorDebugSymbolProvider:: GetObjectSize ((método)'
title: ICorDebugSymbolProvider::GetObjectSize (método)
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
ms.openlocfilehash: 72720a1af9958fd0ab91276b3967733cec77fee7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659715"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="4f274-103">ICorDebugSymbolProvider::GetObjectSize (método)</span><span class="sxs-lookup"><span data-stu-id="4f274-103">ICorDebugSymbolProvider::GetObjectSize Method</span></span>

<span data-ttu-id="4f274-104">Devuelve el tamaño del objeto para un objeto basado en su firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="4f274-104">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f274-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f274-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f274-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4f274-106">Parameters</span></span>  

 `cbSignature`  
 <span data-ttu-id="4f274-107">[in] Número de bytes de la firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="4f274-107">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="4f274-108">typeSig</span><span class="sxs-lookup"><span data-stu-id="4f274-108">typeSig</span></span>  
 <span data-ttu-id="4f274-109">[in] Firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="4f274-109">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="4f274-110">[out] Puntero al tamaño del objeto.</span><span class="sxs-lookup"><span data-stu-id="4f274-110">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f274-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4f274-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4f274-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="4f274-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f274-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4f274-113">Requirements</span></span>  

 <span data-ttu-id="4f274-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f274-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f274-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f274-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f274-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f274-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f274-117">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f274-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f274-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f274-118">See also</span></span>

- [<span data-ttu-id="4f274-119">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="4f274-119">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="4f274-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="4f274-120">Debugging Interfaces</span></span>](debugging-interfaces.md)

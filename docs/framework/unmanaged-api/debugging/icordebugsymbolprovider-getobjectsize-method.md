---
title: ICorDebugSymbolProvider::GetObjectSize (método)
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
ms.openlocfilehash: 64324df49ad0b5dfa3c25455950bddc3d687b178
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379554"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="3ab04-102">ICorDebugSymbolProvider::GetObjectSize (método)</span><span class="sxs-lookup"><span data-stu-id="3ab04-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>
<span data-ttu-id="3ab04-103">Devuelve el tamaño del objeto para un objeto basado en su firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="3ab04-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ab04-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3ab04-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ab04-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3ab04-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="3ab04-106">[in] Número de bytes de la firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="3ab04-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="3ab04-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="3ab04-107">typeSig</span></span>  
 <span data-ttu-id="3ab04-108">[in] Firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="3ab04-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="3ab04-109">[out] Puntero al tamaño del objeto.</span><span class="sxs-lookup"><span data-stu-id="3ab04-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ab04-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3ab04-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3ab04-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="3ab04-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ab04-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3ab04-112">Requirements</span></span>  
 <span data-ttu-id="3ab04-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ab04-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ab04-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3ab04-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3ab04-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ab04-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ab04-116">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ab04-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ab04-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3ab04-117">See also</span></span>

- [<span data-ttu-id="3ab04-118">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="3ab04-118">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="3ab04-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="3ab04-119">Debugging Interfaces</span></span>](debugging-interfaces.md)

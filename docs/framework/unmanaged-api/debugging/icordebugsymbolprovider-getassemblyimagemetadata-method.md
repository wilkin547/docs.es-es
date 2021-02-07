---
description: 'Más información sobre: ICorDebugSymbolProvider:: Getassemblyimagemetadata ((método)'
title: ICorDebugSymbolProvider::GetAssemblyImageMetadata (método)
ms.date: 03/30/2017
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
ms.openlocfilehash: 4abe5cc2b2a31f89e6ca4f8fc643f26eac276515
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717191"
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="a88b3-103">ICorDebugSymbolProvider::GetAssemblyImageMetadata (método)</span><span class="sxs-lookup"><span data-stu-id="a88b3-103">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>

<span data-ttu-id="a88b3-104">Devuelve los metadatos desde un ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="a88b3-104">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a88b3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a88b3-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a88b3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a88b3-106">Parameters</span></span>  

 `ppMemoryBuffer`  
 <span data-ttu-id="a88b3-107">enuncia Puntero a la dirección de un objeto [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) que contiene información sobre el tamaño y la dirección de los metadatos del ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="a88b3-107">[out] A pointer to the address of an [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a88b3-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a88b3-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a88b3-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a88b3-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a88b3-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a88b3-110">Requirements</span></span>  

 <span data-ttu-id="a88b3-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a88b3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a88b3-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a88b3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a88b3-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a88b3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a88b3-114">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a88b3-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a88b3-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a88b3-115">See also</span></span>

- [<span data-ttu-id="a88b3-116">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="a88b3-116">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="a88b3-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a88b3-117">Debugging Interfaces</span></span>](debugging-interfaces.md)

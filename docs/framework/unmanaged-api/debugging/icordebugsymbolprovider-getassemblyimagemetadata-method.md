---
title: ICorDebugSymbolProvider::GetAssemblyImageMetadata (método)
ms.date: 03/30/2017
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
ms.openlocfilehash: 9644d1323660730d210bd0305c2785fce4174455
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709146"
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="4be1e-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata (método)</span><span class="sxs-lookup"><span data-stu-id="4be1e-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>

<span data-ttu-id="4be1e-103">Devuelve los metadatos desde un ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="4be1e-103">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4be1e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4be1e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4be1e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4be1e-105">Parameters</span></span>  

 `ppMemoryBuffer`  
 <span data-ttu-id="4be1e-106">enuncia Puntero a la dirección de un objeto [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) que contiene información sobre el tamaño y la dirección de los metadatos del ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="4be1e-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4be1e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4be1e-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4be1e-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="4be1e-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4be1e-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4be1e-109">Requirements</span></span>  

 <span data-ttu-id="4be1e-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4be1e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4be1e-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4be1e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4be1e-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4be1e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4be1e-113">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4be1e-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4be1e-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4be1e-114">See also</span></span>

- [<span data-ttu-id="4be1e-115">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="4be1e-115">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="4be1e-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="4be1e-116">Debugging Interfaces</span></span>](debugging-interfaces.md)

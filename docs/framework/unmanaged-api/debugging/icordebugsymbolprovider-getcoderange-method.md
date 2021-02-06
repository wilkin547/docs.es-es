---
description: 'Más información sobre: ICorDebugSymbolProvider:: Getcoderange ((método)'
title: ICorDebugSymbolProvider::GetCodeRange (método)
ms.date: 03/30/2017
ms.assetid: 49a2451f-d250-4e73-aa96-9ff49d9f11c6
ms.openlocfilehash: 98b228be7483e6365815f6b783167b20fb3bcc48
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659912"
---
# <a name="icordebugsymbolprovidergetcoderange-method"></a><span data-ttu-id="8d8bf-103">ICorDebugSymbolProvider::GetCodeRange (método)</span><span class="sxs-lookup"><span data-stu-id="8d8bf-103">ICorDebugSymbolProvider::GetCodeRange Method</span></span>

<span data-ttu-id="8d8bf-104">Obtiene el tamaño y la dirección de inicio del método a partir de una dirección virtual relativa (RVA) en un método.</span><span class="sxs-lookup"><span data-stu-id="8d8bf-104">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d8bf-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8d8bf-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeRange(  
   [in] ULONG32 codeRva,
   [out] ULONG32* pCodeStartAddress,
   [out] ULONG32* pCodeSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d8bf-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8d8bf-106">Parameters</span></span>  

 `codeRva`  
 <span data-ttu-id="8d8bf-107">[in] Dirección virtual relativa (RVA) en un método.</span><span class="sxs-lookup"><span data-stu-id="8d8bf-107">[in] The relative virtual address (RVA) in a method.</span></span>  
  
 `pCodeStartAddress`  
 <span data-ttu-id="8d8bf-108">[out] Puntero a la dirección de inicio del método.</span><span class="sxs-lookup"><span data-stu-id="8d8bf-108">[out] A pointer to the starting address of the method.</span></span>  
  
 `pCodeSize`  
 <span data-ttu-id="8d8bf-109">Puntero al tamaño del código del método (número de bytes del código del método).</span><span class="sxs-lookup"><span data-stu-id="8d8bf-109">A pointer to the method code size (the number of bytes of the method's code).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d8bf-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8d8bf-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8d8bf-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="8d8bf-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d8bf-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8d8bf-112">Requirements</span></span>  

 <span data-ttu-id="8d8bf-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d8bf-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d8bf-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d8bf-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d8bf-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d8bf-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d8bf-116">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d8bf-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d8bf-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d8bf-117">See also</span></span>

- [<span data-ttu-id="8d8bf-118">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="8d8bf-118">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="8d8bf-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="8d8bf-119">Debugging Interfaces</span></span>](debugging-interfaces.md)

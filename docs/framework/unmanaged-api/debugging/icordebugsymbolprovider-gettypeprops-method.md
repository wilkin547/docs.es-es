---
description: 'Más información sobre: ICorDebugSymbolProvider:: Gettypeprops ((método)'
title: ICorDebugSymbolProvider::GetTypeProps (método)
ms.date: 03/30/2017
ms.assetid: 35ac4140-91ea-4c77-b1c4-1daf41986ca5
ms.openlocfilehash: b6a4a5a68e1e377fa839940832dfc49574009641
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659665"
---
# <a name="icordebugsymbolprovidergettypeprops-method"></a><span data-ttu-id="ef9d9-103">ICorDebugSymbolProvider::GetTypeProps (método)</span><span class="sxs-lookup"><span data-stu-id="ef9d9-103">ICorDebugSymbolProvider::GetTypeProps Method</span></span>

<span data-ttu-id="ef9d9-104">Devuelve información acerca de las propiedades de un tipo, como el número de firmas de sus parámetros genéricos, dada una dirección virtual relativa (RVA) en una tabla virtual.</span><span class="sxs-lookup"><span data-stu-id="ef9d9-104">Returns information about a type's properties, such as the number of signature of its generic parameters, given a relative virtual address (RVA) in a vtable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef9d9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef9d9-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeProps(  
   [in]  ULONG32 vtableRva,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef9d9-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ef9d9-106">Parameters</span></span>  

 `tableRva`  
 <span data-ttu-id="ef9d9-107">[in] Dirección virtual relativa (RVA) en una tabla virtual.</span><span class="sxs-lookup"><span data-stu-id="ef9d9-107">[in] A relative virtual address (RVA) in a vtable.</span></span>  
  
 `cbSignature`  
 <span data-ttu-id="ef9d9-108">[in] Tamaño de la matriz `signature`.</span><span class="sxs-lookup"><span data-stu-id="ef9d9-108">[in] The size of the `signature` array.</span></span> <span data-ttu-id="ef9d9-109">Consulte la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="ef9d9-109">See the Remarks section.</span></span>  
  
 `pcbSignature`  
 <span data-ttu-id="ef9d9-110">[out] [out] Puntero al tamaño de la matriz `signature` devuelta.</span><span class="sxs-lookup"><span data-stu-id="ef9d9-110">[out] [out] A pointer to the size of the returned `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="ef9d9-111">[out] Búfer que contiene las firmas de Typespec de todos los parámetros genéricos.</span><span class="sxs-lookup"><span data-stu-id="ef9d9-111">[out] A buffer that holds the typespec signatures of all generic parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef9d9-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ef9d9-112">Remarks</span></span>  

 <span data-ttu-id="ef9d9-113">Para obtener el tamaño necesario de la matriz del tipo `signature` , establezca el `cbSignature` argumento en 0 y `signature` en **null**.</span><span class="sxs-lookup"><span data-stu-id="ef9d9-113">To get the required size of the type's `signature` array, set the `cbSignature` argument to 0 and `signature` to **null**.</span></span> <span data-ttu-id="ef9d9-114">Con la devolución del método, `pcbSignature` contendrá el número de bytes necesarios para la matriz `signature`.</span><span class="sxs-lookup"><span data-stu-id="ef9d9-114">When the method returns, `pcbSignature` will contain the number of bytes required for the `signature` array.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ef9d9-115">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="ef9d9-115">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef9d9-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ef9d9-116">Requirements</span></span>  

 <span data-ttu-id="ef9d9-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef9d9-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef9d9-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ef9d9-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef9d9-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef9d9-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef9d9-120">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef9d9-120">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef9d9-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef9d9-121">See also</span></span>

- [<span data-ttu-id="ef9d9-122">GetMethodProps (Método)</span><span class="sxs-lookup"><span data-stu-id="ef9d9-122">GetMethodProps Method</span></span>](icordebugsymbolprovider-getmethodprops-method.md)
- [<span data-ttu-id="ef9d9-123">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="ef9d9-123">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="ef9d9-124">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="ef9d9-124">Debugging Interfaces</span></span>](debugging-interfaces.md)

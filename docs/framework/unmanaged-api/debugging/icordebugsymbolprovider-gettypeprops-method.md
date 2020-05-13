---
title: ICorDebugSymbolProvider::GetTypeProps (método)
ms.date: 03/30/2017
ms.assetid: 35ac4140-91ea-4c77-b1c4-1daf41986ca5
ms.openlocfilehash: e116716284bb2081edb669e7fc9083cde10f6457
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379360"
---
# <a name="icordebugsymbolprovidergettypeprops-method"></a><span data-ttu-id="099af-102">ICorDebugSymbolProvider::GetTypeProps (método)</span><span class="sxs-lookup"><span data-stu-id="099af-102">ICorDebugSymbolProvider::GetTypeProps Method</span></span>
<span data-ttu-id="099af-103">Devuelve información acerca de las propiedades de un tipo, como el número de firmas de sus parámetros genéricos, dada una dirección virtual relativa (RVA) en una tabla virtual.</span><span class="sxs-lookup"><span data-stu-id="099af-103">Returns information about a type's properties, such as the number of signature of its generic parameters, given a relative virtual address (RVA) in a vtable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="099af-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="099af-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeProps(  
   [in]  ULONG32 vtableRva,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="099af-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="099af-105">Parameters</span></span>  
 `tableRva`  
 <span data-ttu-id="099af-106">[in] Dirección virtual relativa (RVA) en una tabla virtual.</span><span class="sxs-lookup"><span data-stu-id="099af-106">[in] A relative virtual address (RVA) in a vtable.</span></span>  
  
 `cbSignature`  
 <span data-ttu-id="099af-107">[in] Tamaño de la matriz `signature`.</span><span class="sxs-lookup"><span data-stu-id="099af-107">[in] The size of the `signature` array.</span></span> <span data-ttu-id="099af-108">Consulte la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="099af-108">See the Remarks section.</span></span>  
  
 `pcbSignature`  
 <span data-ttu-id="099af-109">[out] [out] Puntero al tamaño de la matriz `signature` devuelta.</span><span class="sxs-lookup"><span data-stu-id="099af-109">[out] [out] A pointer to the size of the returned `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="099af-110">[out] Búfer que contiene las firmas de Typespec de todos los parámetros genéricos.</span><span class="sxs-lookup"><span data-stu-id="099af-110">[out] A buffer that holds the typespec signatures of all generic parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="099af-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="099af-111">Remarks</span></span>  
 <span data-ttu-id="099af-112">Para obtener el tamaño necesario de la matriz del tipo `signature` , establezca el `cbSignature` argumento en 0 y `signature` en **null**.</span><span class="sxs-lookup"><span data-stu-id="099af-112">To get the required size of the type's `signature` array, set the `cbSignature` argument to 0 and `signature` to **null**.</span></span> <span data-ttu-id="099af-113">Con la devolución del método, `pcbSignature` contendrá el número de bytes necesarios para la matriz `signature`.</span><span class="sxs-lookup"><span data-stu-id="099af-113">When the method returns, `pcbSignature` will contain the number of bytes required for the `signature` array.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="099af-114">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="099af-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="099af-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="099af-115">Requirements</span></span>  
 <span data-ttu-id="099af-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="099af-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="099af-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="099af-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="099af-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="099af-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="099af-119">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="099af-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="099af-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="099af-120">See also</span></span>

- [<span data-ttu-id="099af-121">GetMethodProps (Método)</span><span class="sxs-lookup"><span data-stu-id="099af-121">GetMethodProps Method</span></span>](icordebugsymbolprovider-getmethodprops-method.md)
- [<span data-ttu-id="099af-122">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="099af-122">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="099af-123">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="099af-123">Debugging Interfaces</span></span>](debugging-interfaces.md)

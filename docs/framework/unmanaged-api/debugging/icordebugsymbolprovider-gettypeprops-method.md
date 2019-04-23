---
title: Gettypeprops (método)
ms.date: 03/30/2017
ms.assetid: 35ac4140-91ea-4c77-b1c4-1daf41986ca5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5f9867dbdc244ed22948dbe9a07a7ea06292d6a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079089"
---
# <a name="icordebugsymbolprovidergettypeprops-method"></a><span data-ttu-id="f94a3-102">Gettypeprops (método)</span><span class="sxs-lookup"><span data-stu-id="f94a3-102">ICorDebugSymbolProvider::GetTypeProps Method</span></span>
<span data-ttu-id="f94a3-103">Devuelve información acerca de las propiedades de un tipo, como el número de firmas de sus parámetros genéricos, dada una dirección virtual relativa (RVA) en una tabla virtual.</span><span class="sxs-lookup"><span data-stu-id="f94a3-103">Returns information about a type's properties, such as the number of signature of its generic parameters, given a relative virtual address (RVA) in a vtable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f94a3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f94a3-104">Syntax</span></span>  
  
```  
HRESULT GetTypeProps(  
   [in]  ULONG32 vtableRva,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f94a3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f94a3-105">Parameters</span></span>  
 `tableRva`  
 <span data-ttu-id="f94a3-106">[in] Dirección virtual relativa (RVA) en una tabla virtual.</span><span class="sxs-lookup"><span data-stu-id="f94a3-106">[in] A relative virtual address (RVA) in a vtable.</span></span>  
  
 `cbSignature`  
 <span data-ttu-id="f94a3-107">[in] Tamaño de la matriz `signature`.</span><span class="sxs-lookup"><span data-stu-id="f94a3-107">[in] The size of the `signature` array.</span></span> <span data-ttu-id="f94a3-108">Vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="f94a3-108">See the Remarks section.</span></span>  
  
 `pcbSignature`  
 <span data-ttu-id="f94a3-109">[out] [out] Puntero al tamaño de la matriz `signature` devuelta.</span><span class="sxs-lookup"><span data-stu-id="f94a3-109">[out] [out] A pointer to the size of the returned `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="f94a3-110">[out] Búfer que contiene las firmas de Typespec de todos los parámetros genéricos.</span><span class="sxs-lookup"><span data-stu-id="f94a3-110">[out] A buffer that holds the typespec signatures of all generic parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f94a3-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f94a3-111">Remarks</span></span>  
 <span data-ttu-id="f94a3-112">Para obtener el tamaño necesario del tipo `signature` de matriz, establezca el `cbSignature` argumento en 0 y `signature` a **null**.</span><span class="sxs-lookup"><span data-stu-id="f94a3-112">To get the required size of the type's `signature` array, set the `cbSignature` argument to 0 and `signature` to **null**.</span></span> <span data-ttu-id="f94a3-113">Con la devolución del método, `pcbSignature` contendrá el número de bytes necesarios para la matriz `signature`.</span><span class="sxs-lookup"><span data-stu-id="f94a3-113">When the method returns, `pcbSignature` will contain the number of bytes required for the `signature` array.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f94a3-114">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f94a3-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f94a3-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f94a3-115">Requirements</span></span>  
 <span data-ttu-id="f94a3-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f94a3-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f94a3-117">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f94a3-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f94a3-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f94a3-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f94a3-119">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f94a3-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f94a3-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="f94a3-120">See also</span></span>

- [<span data-ttu-id="f94a3-121">GetMethodProps (método)</span><span class="sxs-lookup"><span data-stu-id="f94a3-121">GetMethodProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodprops-method.md)
- [<span data-ttu-id="f94a3-122">ICorDebugSymbolProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f94a3-122">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="f94a3-123">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f94a3-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

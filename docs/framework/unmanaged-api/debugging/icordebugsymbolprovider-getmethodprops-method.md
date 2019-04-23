---
title: ICorDebugSymbolProvider::GetMethodProps (método)
ms.date: 03/30/2017
ms.assetid: 8f836b80-b7a5-460b-bf76-5f0e45652aea
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 784fcb10e9c0c3c6ff50c25d47bb4fb3fd5762ba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59161114"
---
# <a name="icordebugsymbolprovidergetmethodprops-method"></a><span data-ttu-id="702d8-102">ICorDebugSymbolProvider::GetMethodProps (método)</span><span class="sxs-lookup"><span data-stu-id="702d8-102">ICorDebugSymbolProvider::GetMethodProps Method</span></span>
<span data-ttu-id="702d8-103">Devuelve información acerca de las propiedades del método, como el token de metadatos del método e información acerca de sus parámetros genéricos, a partir de una dirección virtual relativa (RVA) en ese método.</span><span class="sxs-lookup"><span data-stu-id="702d8-103">Returns information about method properties, such as the method's metadata token and information about its generic parameters, given a relative virtual address (RVA) in that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="702d8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="702d8-104">Syntax</span></span>  
  
```  
HRESULT GetMethodProps(  
   [in]  ULONG32 codeRva,  
   [out] mdToken *pMethodToken,  
   [out] ULONG32 *pcGenericParams,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="702d8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="702d8-105">Parameters</span></span>  
 `codeRVA`  
 <span data-ttu-id="702d8-106">[in] Dirección virtual relativa del método acerca de qué información se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="702d8-106">[in] A relative virtual address in the method about which information is to be retrieved.</span></span>  
  
 `pMethodToken`  
 <span data-ttu-id="702d8-107">[out] Puntero al token de metadatos del método.</span><span class="sxs-lookup"><span data-stu-id="702d8-107">[out] A pointer to the method's metadata token.</span></span>  
  
 `pcGenericParams`  
 <span data-ttu-id="702d8-108">[out] Puntero al número de parámetros genéricos asociados a este método.</span><span class="sxs-lookup"><span data-stu-id="702d8-108">[out] A pointer to the number of generic parameters associated with this method.</span></span>  
  
 `cbSignature`  
 <span data-ttu-id="702d8-109">[in] Tamaño de la matriz `signature`.</span><span class="sxs-lookup"><span data-stu-id="702d8-109">[in] The size of the `signature` array.</span></span> <span data-ttu-id="702d8-110">Vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="702d8-110">See the Remarks section.</span></span>  
  
 `pcbSignature`  
 <span data-ttu-id="702d8-111">[out] Puntero al tamaño de la matriz `signature` devuelta.</span><span class="sxs-lookup"><span data-stu-id="702d8-111">[out] A pointer to the size of the returned `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="702d8-112">[out] Búfer que contiene las firmas de Typespec de todos los parámetros genéricos.</span><span class="sxs-lookup"><span data-stu-id="702d8-112">[out] A buffer that holds the typespec signatures of all generic parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="702d8-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="702d8-113">Remarks</span></span>  
 <span data-ttu-id="702d8-114">Para obtener el tamaño necesario del método `signature` de matriz, establezca el `cbSignature` argumento en 0 y `signature` a **null**.</span><span class="sxs-lookup"><span data-stu-id="702d8-114">To get the required size of the method's `signature` array, set the `cbSignature` argument to 0 and `signature` to **null**.</span></span> <span data-ttu-id="702d8-115">Con la devolución del método, `pcbSignature` contendrá el número de bytes necesarios para la matriz `signature`.</span><span class="sxs-lookup"><span data-stu-id="702d8-115">When the method returns, `pcbSignature` will contain the number of bytes required for the `signature` array.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="702d8-116">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="702d8-116">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="702d8-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="702d8-117">Requirements</span></span>  
 <span data-ttu-id="702d8-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="702d8-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="702d8-119">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="702d8-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="702d8-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="702d8-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="702d8-121">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="702d8-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="702d8-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="702d8-122">See also</span></span>

- [<span data-ttu-id="702d8-123">GetTypeProps (método)</span><span class="sxs-lookup"><span data-stu-id="702d8-123">GetTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-gettypeprops-method.md)
- [<span data-ttu-id="702d8-124">ICorDebugSymbolProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="702d8-124">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="702d8-125">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="702d8-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

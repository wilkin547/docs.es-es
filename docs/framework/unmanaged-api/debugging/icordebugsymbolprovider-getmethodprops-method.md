---
description: 'Más información sobre: ICorDebugSymbolProvider:: GetMethodProps ((método)'
title: ICorDebugSymbolProvider::GetMethodProps (método)
ms.date: 03/30/2017
ms.assetid: 8f836b80-b7a5-460b-bf76-5f0e45652aea
ms.openlocfilehash: 53a329426ecadfe5559c0e6a08ffbd250163e177
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659730"
---
# <a name="icordebugsymbolprovidergetmethodprops-method"></a><span data-ttu-id="af335-103">ICorDebugSymbolProvider::GetMethodProps (método)</span><span class="sxs-lookup"><span data-stu-id="af335-103">ICorDebugSymbolProvider::GetMethodProps Method</span></span>

<span data-ttu-id="af335-104">Devuelve información acerca de las propiedades del método, como el token de metadatos del método e información acerca de sus parámetros genéricos, a partir de una dirección virtual relativa (RVA) en ese método.</span><span class="sxs-lookup"><span data-stu-id="af335-104">Returns information about method properties, such as the method's metadata token and information about its generic parameters, given a relative virtual address (RVA) in that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af335-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af335-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodProps(  
   [in]  ULONG32 codeRva,  
   [out] mdToken *pMethodToken,  
   [out] ULONG32 *pcGenericParams,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af335-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="af335-106">Parameters</span></span>  

 `codeRVA`  
 <span data-ttu-id="af335-107">[in] Dirección virtual relativa del método acerca de qué información se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="af335-107">[in] A relative virtual address in the method about which information is to be retrieved.</span></span>  
  
 `pMethodToken`  
 <span data-ttu-id="af335-108">[out] Puntero al token de metadatos del método.</span><span class="sxs-lookup"><span data-stu-id="af335-108">[out] A pointer to the method's metadata token.</span></span>  
  
 `pcGenericParams`  
 <span data-ttu-id="af335-109">[out] Puntero al número de parámetros genéricos asociados a este método.</span><span class="sxs-lookup"><span data-stu-id="af335-109">[out] A pointer to the number of generic parameters associated with this method.</span></span>  
  
 `cbSignature`  
 <span data-ttu-id="af335-110">[in] Tamaño de la matriz `signature`.</span><span class="sxs-lookup"><span data-stu-id="af335-110">[in] The size of the `signature` array.</span></span> <span data-ttu-id="af335-111">Consulte la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="af335-111">See the Remarks section.</span></span>  
  
 `pcbSignature`  
 <span data-ttu-id="af335-112">[out] Puntero al tamaño de la matriz `signature` devuelta.</span><span class="sxs-lookup"><span data-stu-id="af335-112">[out] A pointer to the size of the returned `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="af335-113">[out] Búfer que contiene las firmas de Typespec de todos los parámetros genéricos.</span><span class="sxs-lookup"><span data-stu-id="af335-113">[out] A buffer that holds the typespec signatures of all generic parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af335-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="af335-114">Remarks</span></span>  

 <span data-ttu-id="af335-115">Para obtener el tamaño necesario de la matriz del método `signature` , establezca el `cbSignature` argumento en 0 y `signature` en **null**.</span><span class="sxs-lookup"><span data-stu-id="af335-115">To get the required size of the method's `signature` array, set the `cbSignature` argument to 0 and `signature` to **null**.</span></span> <span data-ttu-id="af335-116">Con la devolución del método, `pcbSignature` contendrá el número de bytes necesarios para la matriz `signature`.</span><span class="sxs-lookup"><span data-stu-id="af335-116">When the method returns, `pcbSignature` will contain the number of bytes required for the `signature` array.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="af335-117">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="af335-117">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af335-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="af335-118">Requirements</span></span>  

 <span data-ttu-id="af335-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af335-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af335-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af335-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af335-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af335-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af335-122">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af335-122">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af335-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="af335-123">See also</span></span>

- [<span data-ttu-id="af335-124">Método GetTypeProps</span><span class="sxs-lookup"><span data-stu-id="af335-124">GetTypeProps Method</span></span>](icordebugsymbolprovider-gettypeprops-method.md)
- [<span data-ttu-id="af335-125">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="af335-125">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="af335-126">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="af335-126">Debugging Interfaces</span></span>](debugging-interfaces.md)

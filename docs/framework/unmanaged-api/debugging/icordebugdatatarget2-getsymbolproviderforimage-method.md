---
description: 'Más información sobre: método icordebugdatatarget2:: GetSymbolProviderForImage (método)'
title: Método ICorDebugDataTarget2::GetSymbolProviderForImage
ms.date: 03/30/2017
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
ms.openlocfilehash: 7b4493b6c0959dc39d955d7691a22ac6905034b1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764390"
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a><span data-ttu-id="02d94-103">Método ICorDebugDataTarget2::GetSymbolProviderForImage</span><span class="sxs-lookup"><span data-stu-id="02d94-103">ICorDebugDataTarget2::GetSymbolProviderForImage Method</span></span>

<span data-ttu-id="02d94-104">Devuelve el proveedor de símbolos de un módulo a partir de la dirección base de ese módulo.</span><span class="sxs-lookup"><span data-stu-id="02d94-104">Returns the symbol-provider for a module from the base address of that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02d94-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02d94-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02d94-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="02d94-106">Parameters</span></span>  

 `imageBaseAddress`  
 <span data-ttu-id="02d94-107">de [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) valor que representa la dirección base de un módulo.</span><span class="sxs-lookup"><span data-stu-id="02d94-107">[in] A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents the base address of a module.</span></span>  
  
 `ppSymProvider`  
 <span data-ttu-id="02d94-108">enuncia Puntero a la dirección de un objeto [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="02d94-108">[out] A pointer to the address of an [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02d94-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="02d94-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="02d94-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="02d94-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02d94-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="02d94-111">Requirements</span></span>  

 <span data-ttu-id="02d94-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02d94-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02d94-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02d94-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02d94-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02d94-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02d94-115">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02d94-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02d94-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="02d94-116">See also</span></span>

- [<span data-ttu-id="02d94-117">Interfaz ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="02d94-117">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="02d94-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="02d94-118">Debugging Interfaces</span></span>](debugging-interfaces.md)

---
title: Método ICorDebugDataTarget2::GetSymbolProviderForImage
ms.date: 03/30/2017
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
ms.openlocfilehash: 5a5ccaeb36dcda82c0189026e19c6a7c023f3e1c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713774"
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a><span data-ttu-id="6fa0b-102">Método ICorDebugDataTarget2::GetSymbolProviderForImage</span><span class="sxs-lookup"><span data-stu-id="6fa0b-102">ICorDebugDataTarget2::GetSymbolProviderForImage Method</span></span>

<span data-ttu-id="6fa0b-103">Devuelve el proveedor de símbolos de un módulo a partir de la dirección base de ese módulo.</span><span class="sxs-lookup"><span data-stu-id="6fa0b-103">Returns the symbol-provider for a module from the base address of that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fa0b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6fa0b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fa0b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6fa0b-105">Parameters</span></span>  

 `imageBaseAddress`  
 <span data-ttu-id="6fa0b-106">de [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) valor que representa la dirección base de un módulo.</span><span class="sxs-lookup"><span data-stu-id="6fa0b-106">[in] A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents the base address of a module.</span></span>  
  
 `ppSymProvider`  
 <span data-ttu-id="6fa0b-107">enuncia Puntero a la dirección de un objeto [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="6fa0b-107">[out] A pointer to the address of an [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6fa0b-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6fa0b-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6fa0b-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="6fa0b-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fa0b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6fa0b-110">Requirements</span></span>  

 <span data-ttu-id="6fa0b-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fa0b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fa0b-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6fa0b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6fa0b-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6fa0b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6fa0b-114">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fa0b-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fa0b-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6fa0b-115">See also</span></span>

- [<span data-ttu-id="6fa0b-116">Interfaz ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="6fa0b-116">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="6fa0b-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="6fa0b-117">Debugging Interfaces</span></span>](debugging-interfaces.md)

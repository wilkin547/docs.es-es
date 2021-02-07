---
description: 'Más información sobre: método icordebugdatatarget2:: GetImageFromPointer (método)'
title: Método ICorDebugDataTarget2::GetImageFromPointer
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
ms.openlocfilehash: bcf73fa522072707a7b08d90965fcd38188c2bb5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764403"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="457ba-103">Método ICorDebugDataTarget2::GetImageFromPointer</span><span class="sxs-lookup"><span data-stu-id="457ba-103">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>

<span data-ttu-id="457ba-104">Devuelve el tamaño y dirección base del módulo a partir de una dirección de ese módulo.</span><span class="sxs-lookup"><span data-stu-id="457ba-104">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="457ba-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="457ba-105">Syntax</span></span>  
  
```cpp  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,
   [out] CORDB_ADDRESS *pImageBase,
   [out] ULONG32 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="457ba-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="457ba-106">Parameters</span></span>  

 `addr`  
 <span data-ttu-id="457ba-107">[CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) valor que representa una dirección de un módulo.</span><span class="sxs-lookup"><span data-stu-id="457ba-107">A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="457ba-108">enuncia [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) valor que representa la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="457ba-108">[out] A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="457ba-109">Puntero al tamaño del módulo.</span><span class="sxs-lookup"><span data-stu-id="457ba-109">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="457ba-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="457ba-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="457ba-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="457ba-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="457ba-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="457ba-112">Requirements</span></span>  

 <span data-ttu-id="457ba-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="457ba-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="457ba-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="457ba-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="457ba-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="457ba-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="457ba-116">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="457ba-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="457ba-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="457ba-117">See also</span></span>

- [<span data-ttu-id="457ba-118">Interfaz ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="457ba-118">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="457ba-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="457ba-119">Debugging Interfaces</span></span>](debugging-interfaces.md)

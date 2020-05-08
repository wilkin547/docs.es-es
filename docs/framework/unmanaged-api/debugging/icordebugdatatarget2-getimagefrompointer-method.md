---
title: Método ICorDebugDataTarget2::GetImageFromPointer
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
ms.openlocfilehash: f316ddb04cdaad2f528e8fac0a970ca6263ebd8f
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976478"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="55267-102">Método ICorDebugDataTarget2::GetImageFromPointer</span><span class="sxs-lookup"><span data-stu-id="55267-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>
<span data-ttu-id="55267-103">Devuelve el tamaño y dirección base del módulo a partir de una dirección de ese módulo.</span><span class="sxs-lookup"><span data-stu-id="55267-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55267-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="55267-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,
   [out] CORDB_ADDRESS *pImageBase,
   [out] ULONG32 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55267-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="55267-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="55267-106">[CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) valor que representa una dirección de un módulo.</span><span class="sxs-lookup"><span data-stu-id="55267-106">A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="55267-107">enuncia [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) valor que representa la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="55267-107">[out] A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="55267-108">Puntero al tamaño del módulo.</span><span class="sxs-lookup"><span data-stu-id="55267-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55267-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="55267-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="55267-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="55267-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55267-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="55267-111">Requirements</span></span>  
 <span data-ttu-id="55267-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55267-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55267-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="55267-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55267-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55267-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55267-115">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55267-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55267-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="55267-116">See also</span></span>

- [<span data-ttu-id="55267-117">Interfaz ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="55267-117">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="55267-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="55267-118">Debugging Interfaces</span></span>](debugging-interfaces.md)

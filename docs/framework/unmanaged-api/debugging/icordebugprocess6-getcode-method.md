---
title: Método ICorDebugProcess6::GetCode
ms.date: 03/30/2017
ms.assetid: faa538c2-60c9-4064-b996-1b4c24ebd751
ms.openlocfilehash: 1588728f486ffb3db583439de05aff34e3dc59f8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792266"
---
# <a name="icordebugprocess6getcode-method"></a><span data-ttu-id="f062a-102">Método ICorDebugProcess6::GetCode</span><span class="sxs-lookup"><span data-stu-id="f062a-102">ICorDebugProcess6::GetCode Method</span></span>
<span data-ttu-id="f062a-103">Obtiene información sobre el código administrado en una dirección de código determinado.</span><span class="sxs-lookup"><span data-stu-id="f062a-103">Gets information about the managed code at a particular code address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f062a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f062a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [in] CORDB_ADDRESS codeAddress,   
    [out] ICorDebugCode **ppCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f062a-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="f062a-105">Parameters</span></span>  
 `codeAddress`  
 <span data-ttu-id="f062a-106">de Un valor [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) que especifica la dirección de inicio del segmento de código administrado.</span><span class="sxs-lookup"><span data-stu-id="f062a-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that specifies the starting address of the managed code segment.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="f062a-107">enuncia Puntero a la dirección de un objeto "ICorDebugCode" que representa un segmento de código administrado.</span><span class="sxs-lookup"><span data-stu-id="f062a-107">[out] A pointer to the address of an "ICorDebugCode" object that represents a segment of managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f062a-108">Notas</span><span class="sxs-lookup"><span data-stu-id="f062a-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f062a-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f062a-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f062a-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="f062a-110">Requirements</span></span>  
 <span data-ttu-id="f062a-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f062a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f062a-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f062a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f062a-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f062a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f062a-114">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f062a-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f062a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f062a-115">See also</span></span>

- [<span data-ttu-id="f062a-116">ICorDebugProcess6 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f062a-116">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="f062a-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f062a-117">Debugging Interfaces</span></span>](debugging-interfaces.md)

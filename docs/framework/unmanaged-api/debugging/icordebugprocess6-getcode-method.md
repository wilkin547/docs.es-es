---
title: Método ICorDebugProcess6::GetCode
ms.date: 03/30/2017
ms.assetid: faa538c2-60c9-4064-b996-1b4c24ebd751
ms.openlocfilehash: 94882c67752705f9f13b858ae3b386a19dc103a6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178555"
---
# <a name="icordebugprocess6getcode-method"></a><span data-ttu-id="6bd51-102">Método ICorDebugProcess6::GetCode</span><span class="sxs-lookup"><span data-stu-id="6bd51-102">ICorDebugProcess6::GetCode Method</span></span>
<span data-ttu-id="6bd51-103">Obtiene información sobre el código administrado en una dirección de código determinado.</span><span class="sxs-lookup"><span data-stu-id="6bd51-103">Gets information about the managed code at a particular code address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bd51-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6bd51-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [in] CORDB_ADDRESS codeAddress,
    [out] ICorDebugCode **ppCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6bd51-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6bd51-105">Parameters</span></span>  
 `codeAddress`  
 <span data-ttu-id="6bd51-106">[en] Un [valor de CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) que especifica la dirección inicial del segmento de código administrado.</span><span class="sxs-lookup"><span data-stu-id="6bd51-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that specifies the starting address of the managed code segment.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="6bd51-107">[fuera] Puntero a la dirección de un objeto "ICorDebugCode" que representa un segmento de código administrado.</span><span class="sxs-lookup"><span data-stu-id="6bd51-107">[out] A pointer to the address of an "ICorDebugCode" object that represents a segment of managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6bd51-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6bd51-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6bd51-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="6bd51-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bd51-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6bd51-110">Requirements</span></span>  
 <span data-ttu-id="6bd51-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6bd51-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bd51-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6bd51-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6bd51-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6bd51-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6bd51-114">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bd51-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bd51-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6bd51-115">See also</span></span>

- [<span data-ttu-id="6bd51-116">ICorDebugProcess6 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6bd51-116">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="6bd51-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="6bd51-117">Debugging Interfaces</span></span>](debugging-interfaces.md)

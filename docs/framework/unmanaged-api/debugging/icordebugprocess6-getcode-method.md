---
title: Método ICorDebugProcess6::GetCode
ms.date: 03/30/2017
ms.assetid: faa538c2-60c9-4064-b996-1b4c24ebd751
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7349a20da35eb0b87894440026a0974d49ae2aa0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097302"
---
# <a name="icordebugprocess6getcode-method"></a><span data-ttu-id="70cec-102">Método ICorDebugProcess6::GetCode</span><span class="sxs-lookup"><span data-stu-id="70cec-102">ICorDebugProcess6::GetCode Method</span></span>
<span data-ttu-id="70cec-103">Obtiene información sobre el código administrado en una dirección de código determinado.</span><span class="sxs-lookup"><span data-stu-id="70cec-103">Gets information about the managed code at a particular code address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70cec-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="70cec-104">Syntax</span></span>  
  
```  
HRESULT GetCode(  
    [in] CORDB_ADDRESS codeAddress,   
    [out] ICorDebugCode **ppCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70cec-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="70cec-105">Parameters</span></span>  
 `codeAddress`  
 <span data-ttu-id="70cec-106">[in] Un [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) valor que especifica la dirección inicial del segmento de código administrado.</span><span class="sxs-lookup"><span data-stu-id="70cec-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that specifies the starting address of the managed code segment.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="70cec-107">[out] Un puntero a la dirección de un objeto "ICorDebugCode" que representa un segmento de código administrado.</span><span class="sxs-lookup"><span data-stu-id="70cec-107">[out] A pointer to the address of an "ICorDebugCode" object that represents a segment of managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70cec-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="70cec-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70cec-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="70cec-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70cec-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="70cec-110">Requirements</span></span>  
 <span data-ttu-id="70cec-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70cec-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70cec-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="70cec-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="70cec-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70cec-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="70cec-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="70cec-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="70cec-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="70cec-115">See also</span></span>

- [<span data-ttu-id="70cec-116">Interfaz ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="70cec-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="70cec-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="70cec-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

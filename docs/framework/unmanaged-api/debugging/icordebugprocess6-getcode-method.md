---
title: Método ICorDebugProcess6::GetCode
ms.date: 03/30/2017
ms.assetid: faa538c2-60c9-4064-b996-1b4c24ebd751
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 572b279ddfdb1fb0eb9da4b0d1f8c2cb12c8a46b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420168"
---
# <a name="icordebugprocess6getcode-method"></a><span data-ttu-id="4598e-102">Método ICorDebugProcess6::GetCode</span><span class="sxs-lookup"><span data-stu-id="4598e-102">ICorDebugProcess6::GetCode Method</span></span>
<span data-ttu-id="4598e-103">Obtiene información sobre el código administrado en una dirección de código determinado.</span><span class="sxs-lookup"><span data-stu-id="4598e-103">Gets information about the managed code at a particular code address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4598e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4598e-104">Syntax</span></span>  
  
```  
HRESULT GetCode(  
    [in] CORDB_ADDRESS codeAddress,   
    [out] ICorDebugCode **ppCode);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4598e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4598e-105">Parameters</span></span>  
 `codeAddress`  
 <span data-ttu-id="4598e-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) valor que especifica la dirección inicial del segmento de código administrado.</span><span class="sxs-lookup"><span data-stu-id="4598e-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that specifies the starting address of the managed code segment.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="4598e-107">[out] Un puntero a la dirección de un objeto de "ICorDebugCode" que representa un segmento de código administrado.</span><span class="sxs-lookup"><span data-stu-id="4598e-107">[out] A pointer to the address of an "ICorDebugCode" object that represents a segment of managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4598e-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4598e-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4598e-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="4598e-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4598e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4598e-110">Requirements</span></span>  
 <span data-ttu-id="4598e-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4598e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4598e-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4598e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4598e-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4598e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4598e-114">**Versiones de .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4598e-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4598e-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="4598e-115">See Also</span></span>  
 [<span data-ttu-id="4598e-116">ICorDebugProcess6 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4598e-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [<span data-ttu-id="4598e-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="4598e-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

---
description: 'Más información sobre: método icordebugprocess6:: GetCode (método)'
title: Método ICorDebugProcess6::GetCode
ms.date: 03/30/2017
ms.assetid: faa538c2-60c9-4064-b996-1b4c24ebd751
ms.openlocfilehash: a7cb71ddb1e65cda37d762a0fba958d413145138
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649668"
---
# <a name="icordebugprocess6getcode-method"></a><span data-ttu-id="2806c-103">Método ICorDebugProcess6::GetCode</span><span class="sxs-lookup"><span data-stu-id="2806c-103">ICorDebugProcess6::GetCode Method</span></span>

<span data-ttu-id="2806c-104">Obtiene información sobre el código administrado en una dirección de código determinado.</span><span class="sxs-lookup"><span data-stu-id="2806c-104">Gets information about the managed code at a particular code address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2806c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2806c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [in] CORDB_ADDRESS codeAddress,
    [out] ICorDebugCode **ppCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2806c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2806c-106">Parameters</span></span>  

 `codeAddress`  
 <span data-ttu-id="2806c-107">de Un valor [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) que especifica la dirección de inicio del segmento de código administrado.</span><span class="sxs-lookup"><span data-stu-id="2806c-107">[in] A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that specifies the starting address of the managed code segment.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="2806c-108">enuncia Puntero a la dirección de un objeto "ICorDebugCode" que representa un segmento de código administrado.</span><span class="sxs-lookup"><span data-stu-id="2806c-108">[out] A pointer to the address of an "ICorDebugCode" object that represents a segment of managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2806c-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2806c-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2806c-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="2806c-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2806c-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2806c-111">Requirements</span></span>  

 <span data-ttu-id="2806c-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2806c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2806c-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2806c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2806c-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2806c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2806c-115">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2806c-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2806c-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="2806c-116">See also</span></span>

- [<span data-ttu-id="2806c-117">Interfaz ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="2806c-117">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="2806c-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="2806c-118">Debugging Interfaces</span></span>](debugging-interfaces.md)

---
description: 'Más información sobre: ICorDebugMergedAssemblyRecord:: GetPublicKey ((método)'
title: ICorDebugMergedAssemblyRecord::GetPublicKey (método)
ms.date: 03/30/2017
ms.assetid: 6f4e78ba-082b-489d-8b58-4c35fbcc7a5b
ms.openlocfilehash: 15175b0d02773bcbce46bfaec9ce1de3021b7dde
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801103"
---
# <a name="icordebugmergedassemblyrecordgetpublickey-method"></a><span data-ttu-id="ef6fa-103">ICorDebugMergedAssemblyRecord::GetPublicKey (método)</span><span class="sxs-lookup"><span data-stu-id="ef6fa-103">ICorDebugMergedAssemblyRecord::GetPublicKey Method</span></span>

<span data-ttu-id="ef6fa-104">Obtiene la clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ef6fa-104">Gets the assembly's public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef6fa-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef6fa-105">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKey(  
   [in] ULONG32 cbPublicKey,
   [out] ULONG32 *pcbPublicKey,
   [out, size_is(cbPublicKey), length_is(*pcbPublicKey)] BYTE pbPublicKey[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef6fa-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ef6fa-106">Parameters</span></span>  

 `cbPublicKey`  
 <span data-ttu-id="ef6fa-107">[in] Número máximo de bytes en la matriz `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="ef6fa-107">[in] The maximum number of bytes in the `pbPublicKey` array.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="ef6fa-108">[out] Puntero al número real de bytes escritos en la matriz `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="ef6fa-108">[out] A pointer to the actual number of bytes written to the `pbPublicKey` array.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="ef6fa-109">[out] Puntero a una matriz de bytes que contiene la clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ef6fa-109">[out] A pointer to a byte array that contains the assembly's public key.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef6fa-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ef6fa-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ef6fa-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="ef6fa-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef6fa-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ef6fa-112">Requirements</span></span>  

 <span data-ttu-id="ef6fa-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef6fa-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef6fa-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ef6fa-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef6fa-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef6fa-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef6fa-116">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef6fa-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef6fa-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef6fa-117">See also</span></span>

- [<span data-ttu-id="ef6fa-118">Interfaz ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="ef6fa-118">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="ef6fa-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="ef6fa-119">Debugging Interfaces</span></span>](debugging-interfaces.md)

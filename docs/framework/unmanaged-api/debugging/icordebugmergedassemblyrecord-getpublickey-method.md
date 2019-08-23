---
title: 'ICorDebugMergedAssemblyRecord:: GetPublicKey ((método)'
ms.date: 03/30/2017
ms.assetid: 6f4e78ba-082b-489d-8b58-4c35fbcc7a5b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e08b1edcef3e93caa82be3a4342c6a0264734bea
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940015"
---
# <a name="icordebugmergedassemblyrecordgetpublickey-method"></a><span data-ttu-id="66582-102">ICorDebugMergedAssemblyRecord:: GetPublicKey ((método)</span><span class="sxs-lookup"><span data-stu-id="66582-102">ICorDebugMergedAssemblyRecord::GetPublicKey Method</span></span>
<span data-ttu-id="66582-103">Obtiene la clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="66582-103">Gets the assembly's public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66582-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="66582-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKey(  
   [in] ULONG32 cbPublicKey,   
   [out] ULONG32 *pcbPublicKey,   
   [out, size_is(cbPublicKey), length_is(*pcbPublicKey)] BYTE pbPublicKey[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66582-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="66582-105">Parameters</span></span>  
 `cbPublicKey`  
 <span data-ttu-id="66582-106">[in] Número máximo de bytes en la matriz `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="66582-106">[in] The maximum number of bytes in the `pbPublicKey` array.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="66582-107">[out] Puntero al número real de bytes escritos en la matriz `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="66582-107">[out] A pointer to the actual number of bytes written to the `pbPublicKey` array.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="66582-108">[out] Puntero a una matriz de bytes que contiene la clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="66582-108">[out] A pointer to a byte array that contains the assembly's public key.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66582-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="66582-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="66582-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="66582-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66582-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="66582-111">Requirements</span></span>  
 <span data-ttu-id="66582-112">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66582-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66582-113">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="66582-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66582-114">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66582-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66582-115">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66582-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66582-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="66582-116">See also</span></span>

- [<span data-ttu-id="66582-117">ICorDebugMergedAssemblyRecord (interfaz)</span><span class="sxs-lookup"><span data-stu-id="66582-117">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="66582-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="66582-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

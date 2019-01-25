---
title: ICorDebugMergedAssemblyRecord::GetPublicKey (método)
ms.date: 03/30/2017
ms.assetid: 6f4e78ba-082b-489d-8b58-4c35fbcc7a5b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c2b7c2f70b4776c5448d23f37c520bb5b07c051e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54541656"
---
# <a name="icordebugmergedassemblyrecordgetpublickey-method"></a><span data-ttu-id="66383-102">ICorDebugMergedAssemblyRecord::GetPublicKey (método)</span><span class="sxs-lookup"><span data-stu-id="66383-102">ICorDebugMergedAssemblyRecord::GetPublicKey Method</span></span>
<span data-ttu-id="66383-103">Obtiene la clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="66383-103">Gets the assembly's public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66383-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="66383-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKey(  
   [in] ULONG32 cbPublicKey,   
   [out] ULONG32 *pcbPublicKey,   
   [out, size_is(cbPublicKey), length_is(*pcbPublicKey)] BYTE pbPublicKey[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="66383-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="66383-105">Parameters</span></span>  
 `cbPublicKey`  
 <span data-ttu-id="66383-106">[in] Número máximo de bytes en la matriz `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="66383-106">[in] The maximum number of bytes in the `pbPublicKey` array.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="66383-107">[out] Puntero al número real de bytes escritos en la matriz `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="66383-107">[out] A pointer to the actual number of bytes written to the `pbPublicKey` array.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="66383-108">[out] Puntero a una matriz de bytes que contiene la clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="66383-108">[out] A pointer to a byte array that contains the assembly's public key.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66383-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="66383-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66383-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="66383-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66383-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="66383-111">Requirements</span></span>  
 <span data-ttu-id="66383-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66383-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66383-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66383-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66383-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66383-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66383-115">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66383-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66383-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="66383-116">See also</span></span>
- [<span data-ttu-id="66383-117">ICorDebugMergedAssemblyRecord (interfaz)</span><span class="sxs-lookup"><span data-stu-id="66383-117">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="66383-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="66383-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

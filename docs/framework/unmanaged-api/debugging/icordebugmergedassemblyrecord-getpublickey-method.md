---
title: ICorDebugMergedAssemblyRecord::GetPublicKey (método)
ms.date: 03/30/2017
ms.assetid: 6f4e78ba-082b-489d-8b58-4c35fbcc7a5b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 743772b3578cdbd92f66a58d2599a97c896e8172
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413740"
---
# <a name="icordebugmergedassemblyrecordgetpublickey-method"></a><span data-ttu-id="db896-102">ICorDebugMergedAssemblyRecord::GetPublicKey (método)</span><span class="sxs-lookup"><span data-stu-id="db896-102">ICorDebugMergedAssemblyRecord::GetPublicKey Method</span></span>
<span data-ttu-id="db896-103">Obtiene la clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="db896-103">Gets the assembly's public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db896-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db896-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKey(  
   [in] ULONG32 cbPublicKey,   
   [out] ULONG32 *pcbPublicKey,   
   [out, size_is(cbPublicKey), length_is(*pcbPublicKey)] BYTE pbPublicKey[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="db896-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="db896-105">Parameters</span></span>  
 `cbPublicKey`  
 <span data-ttu-id="db896-106">[in] Número máximo de bytes en la matriz `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="db896-106">[in] The maximum number of bytes in the `pbPublicKey` array.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="db896-107">[out] Puntero al número real de bytes escritos en la matriz `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="db896-107">[out] A pointer to the actual number of bytes written to the `pbPublicKey` array.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="db896-108">[out] Puntero a una matriz de bytes que contiene la clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="db896-108">[out] A pointer to a byte array that contains the assembly's public key.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db896-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="db896-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db896-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="db896-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db896-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="db896-111">Requirements</span></span>  
 <span data-ttu-id="db896-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db896-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db896-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db896-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db896-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db896-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db896-115">**Versiones de .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db896-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db896-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="db896-116">See Also</span></span>  
 [<span data-ttu-id="db896-117">ICorDebugMergedAssemblyRecord (interfaz)</span><span class="sxs-lookup"><span data-stu-id="db896-117">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [<span data-ttu-id="db896-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="db896-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

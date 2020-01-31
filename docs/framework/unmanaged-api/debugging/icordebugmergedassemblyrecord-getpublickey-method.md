---
title: ICorDebugMergedAssemblyRecord::GetPublicKey (método)
ms.date: 03/30/2017
ms.assetid: 6f4e78ba-082b-489d-8b58-4c35fbcc7a5b
ms.openlocfilehash: c8c6e9adcb9d29f5e234dd1b8dfd351fac575301
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793116"
---
# <a name="icordebugmergedassemblyrecordgetpublickey-method"></a><span data-ttu-id="27421-102">ICorDebugMergedAssemblyRecord::GetPublicKey (método)</span><span class="sxs-lookup"><span data-stu-id="27421-102">ICorDebugMergedAssemblyRecord::GetPublicKey Method</span></span>
<span data-ttu-id="27421-103">Obtiene la clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="27421-103">Gets the assembly's public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27421-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="27421-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKey(  
   [in] ULONG32 cbPublicKey,   
   [out] ULONG32 *pcbPublicKey,   
   [out, size_is(cbPublicKey), length_is(*pcbPublicKey)] BYTE pbPublicKey[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27421-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="27421-105">Parameters</span></span>  
 `cbPublicKey`  
 <span data-ttu-id="27421-106">[in] Número máximo de bytes en la matriz `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="27421-106">[in] The maximum number of bytes in the `pbPublicKey` array.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="27421-107">[out] Puntero al número real de bytes escritos en la matriz `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="27421-107">[out] A pointer to the actual number of bytes written to the `pbPublicKey` array.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="27421-108">[out] Puntero a una matriz de bytes que contiene la clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="27421-108">[out] A pointer to a byte array that contains the assembly's public key.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27421-109">Notas</span><span class="sxs-lookup"><span data-stu-id="27421-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="27421-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="27421-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27421-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="27421-111">Requirements</span></span>  
 <span data-ttu-id="27421-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27421-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27421-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="27421-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27421-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27421-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27421-115">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27421-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27421-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="27421-116">See also</span></span>

- [<span data-ttu-id="27421-117">ICorDebugMergedAssemblyRecord (interfaz)</span><span class="sxs-lookup"><span data-stu-id="27421-117">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="27421-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="27421-118">Debugging Interfaces</span></span>](debugging-interfaces.md)

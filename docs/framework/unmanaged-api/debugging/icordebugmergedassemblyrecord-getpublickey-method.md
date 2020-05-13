---
title: ICorDebugMergedAssemblyRecord::GetPublicKey (método)
ms.date: 03/30/2017
ms.assetid: 6f4e78ba-082b-489d-8b58-4c35fbcc7a5b
ms.openlocfilehash: 51724aa1ee6101c50c7cdb4b6071fb458814f483
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213548"
---
# <a name="icordebugmergedassemblyrecordgetpublickey-method"></a><span data-ttu-id="f0b31-102">ICorDebugMergedAssemblyRecord::GetPublicKey (método)</span><span class="sxs-lookup"><span data-stu-id="f0b31-102">ICorDebugMergedAssemblyRecord::GetPublicKey Method</span></span>
<span data-ttu-id="f0b31-103">Obtiene la clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f0b31-103">Gets the assembly's public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0b31-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f0b31-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKey(  
   [in] ULONG32 cbPublicKey,
   [out] ULONG32 *pcbPublicKey,
   [out, size_is(cbPublicKey), length_is(*pcbPublicKey)] BYTE pbPublicKey[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0b31-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f0b31-105">Parameters</span></span>  
 `cbPublicKey`  
 <span data-ttu-id="f0b31-106">[in] Número máximo de bytes en la matriz `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="f0b31-106">[in] The maximum number of bytes in the `pbPublicKey` array.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="f0b31-107">[out] Puntero al número real de bytes escritos en la matriz `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="f0b31-107">[out] A pointer to the actual number of bytes written to the `pbPublicKey` array.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="f0b31-108">[out] Puntero a una matriz de bytes que contiene la clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f0b31-108">[out] A pointer to a byte array that contains the assembly's public key.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0b31-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f0b31-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f0b31-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f0b31-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0b31-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f0b31-111">Requirements</span></span>  
 <span data-ttu-id="f0b31-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0b31-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0b31-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0b31-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0b31-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0b31-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0b31-115">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0b31-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0b31-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f0b31-116">See also</span></span>

- [<span data-ttu-id="f0b31-117">Interfaz ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="f0b31-117">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="f0b31-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="f0b31-118">Debugging Interfaces</span></span>](debugging-interfaces.md)

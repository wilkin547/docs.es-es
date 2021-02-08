---
description: 'Más información sobre: ICorDebugMergedAssemblyRecord:: Getpublickeytoken ((método)'
title: ICorDebugMergedAssemblyRecord::GetPublicKeyT (método)
ms.date: 03/30/2017
ms.assetid: 72020b72-9611-4bc3-b1e7-5a16b023bfa3
ms.openlocfilehash: 5ff870355ddf521012e93ed01a63e32358ca95cb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801072"
---
# <a name="icordebugmergedassemblyrecordgetpublickeytoken-method"></a><span data-ttu-id="3c354-103">ICorDebugMergedAssemblyRecord::GetPublicKeyT (método)</span><span class="sxs-lookup"><span data-stu-id="3c354-103">ICorDebugMergedAssemblyRecord::GetPublicKeyToken Method</span></span>

<span data-ttu-id="3c354-104">Obtiene el token de clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3c354-104">Gets the assembly's public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c354-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c354-105">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKeyToken(  
   [in] ULONG32 cbPublicKeyToken,
   [out] ULONG32 *pcbPublicKeyToken,
   [out, size_is(cbPublicKeyToken), length_is(*pcbPublicKeyToken)] BYTE pbPublicKeyToken[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c354-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3c354-106">Parameters</span></span>  

 `cbPublicKeyToken`  
 <span data-ttu-id="3c354-107">[in] Número máximo de bytes en la matriz `pbPublicKeyToken`.</span><span class="sxs-lookup"><span data-stu-id="3c354-107">[in] The maximum number of bytes in the `pbPublicKeyToken` array.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="3c354-108">[out] Puntero al número real de bytes escritos en la matriz `pbPublicKeyToken`.</span><span class="sxs-lookup"><span data-stu-id="3c354-108">[out] A pointer to the actual number of bytes written to the `pbPublicKeyToken` array.</span></span>  
  
 `pbPublicKeyToken`  
 <span data-ttu-id="3c354-109">[out] Puntero a una matriz de bytes que contiene el token de clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3c354-109">[out] A pointer to a byte array that contains the assembly's public key token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c354-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3c354-110">Remarks</span></span>  

 <span data-ttu-id="3c354-111">El token de clave pública de un ensamblado son los últimos ocho bytes de un hash SHA1 de su clave pública.</span><span class="sxs-lookup"><span data-stu-id="3c354-111">An assembly's public key token is the last eight bytes of a SHA1 hash of its public key.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3c354-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="3c354-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c354-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3c354-113">Requirements</span></span>  

 <span data-ttu-id="3c354-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c354-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c354-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3c354-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3c354-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c354-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c354-117">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c354-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c354-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c354-118">See also</span></span>

- [<span data-ttu-id="3c354-119">Interfaz ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="3c354-119">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="3c354-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="3c354-120">Debugging Interfaces</span></span>](debugging-interfaces.md)

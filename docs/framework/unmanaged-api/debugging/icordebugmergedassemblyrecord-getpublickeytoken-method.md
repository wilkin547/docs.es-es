---
title: ICorDebugMergedAssemblyRecord::GetPublicKeyT (método)
ms.date: 03/30/2017
ms.assetid: 72020b72-9611-4bc3-b1e7-5a16b023bfa3
ms.openlocfilehash: c642d8af7e84288d3aa8912372a2f169b8f22503
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710576"
---
# <a name="icordebugmergedassemblyrecordgetpublickeytoken-method"></a><span data-ttu-id="571c9-102">ICorDebugMergedAssemblyRecord::GetPublicKeyT (método)</span><span class="sxs-lookup"><span data-stu-id="571c9-102">ICorDebugMergedAssemblyRecord::GetPublicKeyToken Method</span></span>

<span data-ttu-id="571c9-103">Obtiene el token de clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="571c9-103">Gets the assembly's public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="571c9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="571c9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKeyToken(  
   [in] ULONG32 cbPublicKeyToken,
   [out] ULONG32 *pcbPublicKeyToken,
   [out, size_is(cbPublicKeyToken), length_is(*pcbPublicKeyToken)] BYTE pbPublicKeyToken[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="571c9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="571c9-105">Parameters</span></span>  

 `cbPublicKeyToken`  
 <span data-ttu-id="571c9-106">[in] Número máximo de bytes en la matriz `pbPublicKeyToken`.</span><span class="sxs-lookup"><span data-stu-id="571c9-106">[in] The maximum number of bytes in the `pbPublicKeyToken` array.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="571c9-107">[out] Puntero al número real de bytes escritos en la matriz `pbPublicKeyToken`.</span><span class="sxs-lookup"><span data-stu-id="571c9-107">[out] A pointer to the actual number of bytes written to the `pbPublicKeyToken` array.</span></span>  
  
 `pbPublicKeyToken`  
 <span data-ttu-id="571c9-108">[out] Puntero a una matriz de bytes que contiene el token de clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="571c9-108">[out] A pointer to a byte array that contains the assembly's public key token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="571c9-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="571c9-109">Remarks</span></span>  

 <span data-ttu-id="571c9-110">El token de clave pública de un ensamblado son los últimos ocho bytes de un hash SHA1 de su clave pública.</span><span class="sxs-lookup"><span data-stu-id="571c9-110">An assembly's public key token is the last eight bytes of a SHA1 hash of its public key.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="571c9-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="571c9-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="571c9-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="571c9-112">Requirements</span></span>  

 <span data-ttu-id="571c9-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="571c9-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="571c9-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="571c9-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="571c9-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="571c9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="571c9-116">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="571c9-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="571c9-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="571c9-117">See also</span></span>

- [<span data-ttu-id="571c9-118">Interfaz ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="571c9-118">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="571c9-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="571c9-119">Debugging Interfaces</span></span>](debugging-interfaces.md)

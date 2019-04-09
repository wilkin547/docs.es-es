---
title: ICorDebugMergedAssemblyRecord::GetPublicKeyT (método)
ms.date: 03/30/2017
ms.assetid: 72020b72-9611-4bc3-b1e7-5a16b023bfa3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0a4a8e5f99a845d2befe55f5939b41224f2aa47b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59077308"
---
# <a name="icordebugmergedassemblyrecordgetpublickeytoken-method"></a><span data-ttu-id="c1ff9-102">ICorDebugMergedAssemblyRecord::GetPublicKeyT (método)</span><span class="sxs-lookup"><span data-stu-id="c1ff9-102">ICorDebugMergedAssemblyRecord::GetPublicKeyToken Method</span></span>
<span data-ttu-id="c1ff9-103">Obtiene el token de clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c1ff9-103">Gets the assembly's public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1ff9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1ff9-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKeyToken(  
   [in] ULONG32 cbPublicKeyToken,   
   [out] ULONG32 *pcbPublicKeyToken,   
   [out, size_is(cbPublicKeyToken), length_is(*pcbPublicKeyToken)] BYTE pbPublicKeyToken[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1ff9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c1ff9-105">Parameters</span></span>  
 `cbPublicKeyToken`  
 <span data-ttu-id="c1ff9-106">[in] Número máximo de bytes en la matriz `pbPublicKeyToken`.</span><span class="sxs-lookup"><span data-stu-id="c1ff9-106">[in] The maximum number of bytes in the `pbPublicKeyToken` array.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="c1ff9-107">[out] Puntero al número real de bytes escritos en la matriz `pbPublicKeyToken`.</span><span class="sxs-lookup"><span data-stu-id="c1ff9-107">[out] A pointer to the actual number of bytes written to the `pbPublicKeyToken` array.</span></span>  
  
 `pbPublicKeyToken`  
 <span data-ttu-id="c1ff9-108">[out] Puntero a una matriz de bytes que contiene el token de clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c1ff9-108">[out] A pointer to a byte array that contains the assembly's public key token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1ff9-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c1ff9-109">Remarks</span></span>  
 <span data-ttu-id="c1ff9-110">El token de clave pública de un ensamblado son los últimos ocho bytes de un hash SHA1 de su clave pública.</span><span class="sxs-lookup"><span data-stu-id="c1ff9-110">An assembly's public key token is the last eight bytes of a SHA1 hash of its public key.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1ff9-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c1ff9-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1ff9-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c1ff9-112">Requirements</span></span>  
 <span data-ttu-id="c1ff9-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1ff9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1ff9-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c1ff9-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c1ff9-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1ff9-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c1ff9-116">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c1ff9-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c1ff9-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1ff9-117">See also</span></span>

- [<span data-ttu-id="c1ff9-118">Interfaz ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="c1ff9-118">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="c1ff9-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="c1ff9-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

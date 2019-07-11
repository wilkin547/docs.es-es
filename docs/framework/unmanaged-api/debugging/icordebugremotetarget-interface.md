---
title: ICorDebugRemoteTarget (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugRemoteTarget
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget
helpviewer_keywords:
- ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: bd9936a6-cc24-4869-8761-0988664464e6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e2e6a4624403dcab30bdb7b6d3af0226204cac0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744645"
---
# <a name="icordebugremotetarget-interface"></a><span data-ttu-id="2e72d-102">ICorDebugRemoteTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2e72d-102">ICorDebugRemoteTarget Interface</span></span>
<span data-ttu-id="2e72d-103">Proporciona métodos que permiten a los desarrolladores depurar aplicaciones basadas en Silverlight en el entorno de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="2e72d-103">Provides methods that enable developers to debug Silverlight-based applications in the common language runtime (CLR) environment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e72d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2e72d-104">Syntax</span></span>  
  
```cpp  
interface ICorDebugRemoteTarget  : IUnknown  
{  
    HRESULT GetHostName (  
        [in]  ULONG32                    cchHostName,  
        [out] ULONG32*                   pcchHostName,  
        [out, size_is(cchHostName),  
              length_is(*pcchHostName)]  
                  WCHAR szHostName[]  
        );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="2e72d-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="2e72d-105">Methods</span></span>  
  
|<span data-ttu-id="2e72d-106">Método</span><span class="sxs-lookup"><span data-stu-id="2e72d-106">Method</span></span>|<span data-ttu-id="2e72d-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2e72d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2e72d-108">ICorDebugRemoteTarget::GetHostName (método)</span><span class="sxs-lookup"><span data-stu-id="2e72d-108">ICorDebugRemoteTarget::GetHostName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-gethostname-method.md)|<span data-ttu-id="2e72d-109">Devuelve el nombre de host o la dirección IP de un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="2e72d-109">Returns the host name or the IP address of a remote machine.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e72d-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2e72d-110">Remarks</span></span>  
 <span data-ttu-id="2e72d-111">No se admite la depuración en modo mixto (es decir, código administrado y nativo) en Windows 95, Windows 98 o Windows ME, ni en plataformas que no sean x86 (como IA-64 y AMD64).</span><span class="sxs-lookup"><span data-stu-id="2e72d-111">Mixed-mode (that is, managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA-64 and AMD64).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e72d-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2e72d-112">Requirements</span></span>  
 <span data-ttu-id="2e72d-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e72d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e72d-114">**Encabezado**: CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="2e72d-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="2e72d-115">**Biblioteca:** : CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e72d-115">**Library:** : CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e72d-116">**Versiones de .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="2e72d-116">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e72d-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e72d-117">See also</span></span>

- [<span data-ttu-id="2e72d-118">ICorDebugRemote (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2e72d-118">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)
- [<span data-ttu-id="2e72d-119">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2e72d-119">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="2e72d-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="2e72d-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

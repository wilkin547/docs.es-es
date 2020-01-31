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
ms.openlocfilehash: bab6b7f683b5563cf362366dfb007f83caeee12d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791935"
---
# <a name="icordebugremotetarget-interface"></a><span data-ttu-id="79d8d-102">ICorDebugRemoteTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="79d8d-102">ICorDebugRemoteTarget Interface</span></span>
<span data-ttu-id="79d8d-103">Proporciona métodos que permiten a los desarrolladores depurar aplicaciones basadas en Silverlight en el entorno de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="79d8d-103">Provides methods that enable developers to debug Silverlight-based applications in the common language runtime (CLR) environment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79d8d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="79d8d-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="79d8d-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="79d8d-105">Methods</span></span>  
  
|<span data-ttu-id="79d8d-106">Método</span><span class="sxs-lookup"><span data-stu-id="79d8d-106">Method</span></span>|<span data-ttu-id="79d8d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="79d8d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="79d8d-108">ICorDebugRemoteTarget::GetHostName (método)</span><span class="sxs-lookup"><span data-stu-id="79d8d-108">ICorDebugRemoteTarget::GetHostName Method</span></span>](icordebugremotetarget-gethostname-method.md)|<span data-ttu-id="79d8d-109">Devuelve el nombre de host o la dirección IP de un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="79d8d-109">Returns the host name or the IP address of a remote machine.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79d8d-110">Notas</span><span class="sxs-lookup"><span data-stu-id="79d8d-110">Remarks</span></span>  
 <span data-ttu-id="79d8d-111">No se admite la depuración en modo mixto (es decir, código administrado y nativo) en Windows 95, Windows 98 o Windows ME, ni en plataformas que no sean x86 (como IA-64 y AMD64).</span><span class="sxs-lookup"><span data-stu-id="79d8d-111">Mixed-mode (that is, managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA-64 and AMD64).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79d8d-112">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="79d8d-112">Requirements</span></span>  
 <span data-ttu-id="79d8d-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79d8d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79d8d-114">**Encabezado:** Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="79d8d-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="79d8d-115">**Biblioteca:** : CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="79d8d-115">**Library:** : CorGuids.lib</span></span>  
  
 <span data-ttu-id="79d8d-116">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="79d8d-116">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79d8d-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="79d8d-117">See also</span></span>

- [<span data-ttu-id="79d8d-118">ICorDebugRemote (interfaz)</span><span class="sxs-lookup"><span data-stu-id="79d8d-118">ICorDebugRemote Interface</span></span>](icordebugremote-interface.md)
- [<span data-ttu-id="79d8d-119">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="79d8d-119">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="79d8d-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="79d8d-120">Debugging Interfaces</span></span>](debugging-interfaces.md)

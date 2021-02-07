---
description: 'Más información acerca de: interfaz ICorDebugRemoteTarget'
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
ms.openlocfilehash: c6567ebb76c7a3c415c9978dc50941cb0b8985a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717880"
---
# <a name="icordebugremotetarget-interface"></a><span data-ttu-id="a5661-103">ICorDebugRemoteTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a5661-103">ICorDebugRemoteTarget Interface</span></span>

<span data-ttu-id="a5661-104">Proporciona métodos que permiten a los desarrolladores depurar aplicaciones basadas en Silverlight en el entorno de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="a5661-104">Provides methods that enable developers to debug Silverlight-based applications in the common language runtime (CLR) environment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5661-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5661-105">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="a5661-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="a5661-106">Methods</span></span>  
  
|<span data-ttu-id="a5661-107">Método</span><span class="sxs-lookup"><span data-stu-id="a5661-107">Method</span></span>|<span data-ttu-id="a5661-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5661-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a5661-109">ICorDebugRemoteTarget::GetHostName (Método)</span><span class="sxs-lookup"><span data-stu-id="a5661-109">ICorDebugRemoteTarget::GetHostName Method</span></span>](icordebugremotetarget-gethostname-method.md)|<span data-ttu-id="a5661-110">Devuelve el nombre de host o la dirección IP de un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="a5661-110">Returns the host name or the IP address of a remote machine.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5661-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a5661-111">Remarks</span></span>  

 <span data-ttu-id="a5661-112">No se admite la depuración en modo mixto (es decir, código administrado y nativo) en Windows 95, Windows 98 o Windows ME, ni en plataformas que no sean x86 (como IA-64 y AMD64).</span><span class="sxs-lookup"><span data-stu-id="a5661-112">Mixed-mode (that is, managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA-64 and AMD64).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5661-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a5661-113">Requirements</span></span>  

 <span data-ttu-id="a5661-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5661-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5661-115">**Encabezado:** Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="a5661-115">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="a5661-116">**Biblioteca:** : CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="a5661-116">**Library:** : CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5661-117">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="a5661-117">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5661-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5661-118">See also</span></span>

- [<span data-ttu-id="a5661-119">ICorDebugRemote (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a5661-119">ICorDebugRemote Interface</span></span>](icordebugremote-interface.md)
- [<span data-ttu-id="a5661-120">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a5661-120">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="a5661-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a5661-121">Debugging Interfaces</span></span>](debugging-interfaces.md)

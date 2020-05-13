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
ms.openlocfilehash: 4883c208468db0096bed3ff8cf4a8ed50a5d7cc6
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379229"
---
# <a name="icordebugremotetarget-interface"></a><span data-ttu-id="d5a52-102">ICorDebugRemoteTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d5a52-102">ICorDebugRemoteTarget Interface</span></span>
<span data-ttu-id="d5a52-103">Proporciona métodos que permiten a los desarrolladores depurar aplicaciones basadas en Silverlight en el entorno de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="d5a52-103">Provides methods that enable developers to debug Silverlight-based applications in the common language runtime (CLR) environment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5a52-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d5a52-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="d5a52-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="d5a52-105">Methods</span></span>  
  
|<span data-ttu-id="d5a52-106">Método</span><span class="sxs-lookup"><span data-stu-id="d5a52-106">Method</span></span>|<span data-ttu-id="d5a52-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d5a52-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d5a52-108">ICorDebugRemoteTarget::GetHostName (Método)</span><span class="sxs-lookup"><span data-stu-id="d5a52-108">ICorDebugRemoteTarget::GetHostName Method</span></span>](icordebugremotetarget-gethostname-method.md)|<span data-ttu-id="d5a52-109">Devuelve el nombre de host o la dirección IP de un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="d5a52-109">Returns the host name or the IP address of a remote machine.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5a52-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d5a52-110">Remarks</span></span>  
 <span data-ttu-id="d5a52-111">No se admite la depuración en modo mixto (es decir, código administrado y nativo) en Windows 95, Windows 98 o Windows ME, ni en plataformas que no sean x86 (como IA-64 y AMD64).</span><span class="sxs-lookup"><span data-stu-id="d5a52-111">Mixed-mode (that is, managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA-64 and AMD64).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5a52-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d5a52-112">Requirements</span></span>  
 <span data-ttu-id="d5a52-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5a52-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5a52-114">**Encabezado:** Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="d5a52-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="d5a52-115">**Biblioteca:** : CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="d5a52-115">**Library:** : CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5a52-116">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="d5a52-116">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5a52-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d5a52-117">See also</span></span>

- [<span data-ttu-id="d5a52-118">ICorDebugRemote (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d5a52-118">ICorDebugRemote Interface</span></span>](icordebugremote-interface.md)
- [<span data-ttu-id="d5a52-119">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d5a52-119">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="d5a52-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="d5a52-120">Debugging Interfaces</span></span>](debugging-interfaces.md)

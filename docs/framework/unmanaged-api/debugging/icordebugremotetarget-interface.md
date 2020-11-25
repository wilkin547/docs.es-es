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
ms.openlocfilehash: 4212597b5ba43f0e4767aa585ca28a011e73e07a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711993"
---
# <a name="icordebugremotetarget-interface"></a><span data-ttu-id="731a6-102">ICorDebugRemoteTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="731a6-102">ICorDebugRemoteTarget Interface</span></span>

<span data-ttu-id="731a6-103">Proporciona métodos que permiten a los desarrolladores depurar aplicaciones basadas en Silverlight en el entorno de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="731a6-103">Provides methods that enable developers to debug Silverlight-based applications in the common language runtime (CLR) environment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="731a6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="731a6-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="731a6-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="731a6-105">Methods</span></span>  
  
|<span data-ttu-id="731a6-106">Método</span><span class="sxs-lookup"><span data-stu-id="731a6-106">Method</span></span>|<span data-ttu-id="731a6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="731a6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="731a6-108">ICorDebugRemoteTarget::GetHostName (Método)</span><span class="sxs-lookup"><span data-stu-id="731a6-108">ICorDebugRemoteTarget::GetHostName Method</span></span>](icordebugremotetarget-gethostname-method.md)|<span data-ttu-id="731a6-109">Devuelve el nombre de host o la dirección IP de un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="731a6-109">Returns the host name or the IP address of a remote machine.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="731a6-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="731a6-110">Remarks</span></span>  

 <span data-ttu-id="731a6-111">No se admite la depuración en modo mixto (es decir, código administrado y nativo) en Windows 95, Windows 98 o Windows ME, ni en plataformas que no sean x86 (como IA-64 y AMD64).</span><span class="sxs-lookup"><span data-stu-id="731a6-111">Mixed-mode (that is, managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA-64 and AMD64).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="731a6-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="731a6-112">Requirements</span></span>  

 <span data-ttu-id="731a6-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="731a6-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="731a6-114">**Encabezado:** Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="731a6-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="731a6-115">**Biblioteca:** : CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="731a6-115">**Library:** : CorGuids.lib</span></span>  
  
 <span data-ttu-id="731a6-116">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="731a6-116">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="731a6-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="731a6-117">See also</span></span>

- [<span data-ttu-id="731a6-118">ICorDebugRemote (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="731a6-118">ICorDebugRemote Interface</span></span>](icordebugremote-interface.md)
- [<span data-ttu-id="731a6-119">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="731a6-119">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="731a6-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="731a6-120">Debugging Interfaces</span></span>](debugging-interfaces.md)

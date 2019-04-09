---
title: Método ICorDebugDebugEvent::GetEventKind
ms.date: 03/30/2017
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 62eede48eea01563dbc3e170720694a24343d0a5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150532"
---
# <a name="icordebugdebugeventgeteventkind-method"></a><span data-ttu-id="d360a-102">Método ICorDebugDebugEvent::GetEventKind</span><span class="sxs-lookup"><span data-stu-id="d360a-102">ICorDebugDebugEvent::GetEventKind Method</span></span>
<span data-ttu-id="d360a-103">Indica el tipo de evento que este objeto `ICorDebugDebugEvent` representa.</span><span class="sxs-lookup"><span data-stu-id="d360a-103">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d360a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d360a-104">Syntax</span></span>  
  
```  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d360a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d360a-105">Parameters</span></span>  
 <span data-ttu-id="d360a-106">pDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="d360a-106">pDebugEventKind</span></span>  
 <span data-ttu-id="d360a-107">Un puntero a un [CorDebugDebugEventKind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) miembro de enumeración que indica el tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="d360a-107">A pointer to a [CorDebugDebugEventKind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) enumeration member that indicates the type of event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d360a-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d360a-108">Remarks</span></span>  
 <span data-ttu-id="d360a-109">Según el valor de `pDebugEventKind`, se puede llamar a `QueryInterface` para obtener una interfaz de evento de depuración más precisa con datos adicionales.</span><span class="sxs-lookup"><span data-stu-id="d360a-109">Based on the value of `pDebugEventKind`, you can call `QueryInterface` to get a more precise debug event interface that has additional data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d360a-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d360a-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d360a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d360a-111">Requirements</span></span>  
 <span data-ttu-id="d360a-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d360a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d360a-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d360a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d360a-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d360a-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d360a-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d360a-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d360a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d360a-116">See also</span></span>

- [<span data-ttu-id="d360a-117">Interfaz ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="d360a-117">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [<span data-ttu-id="d360a-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="d360a-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

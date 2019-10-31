---
title: ICorDebugManagedCallback::UpdateModuleSymbols (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UpdateModuleSymbols
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UpdateModuleSymbols
helpviewer_keywords:
- UpdateModuleSymbols method [.NET Framework debugging]
- ICorDebugManagedCallback::UpdateModuleSymbols method [.NET Framework debugging]
ms.assetid: 0863f644-58e8-45a0-b0c3-a28e99b20938
topic_type:
- apiref
ms.openlocfilehash: 1f5b413ffbbc8fccbea38f23d8c87d40e010dd37
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130616"
---
# <a name="icordebugmanagedcallbackupdatemodulesymbols-method"></a><span data-ttu-id="ddd95-102">ICorDebugManagedCallback::UpdateModuleSymbols (Método)</span><span class="sxs-lookup"><span data-stu-id="ddd95-102">ICorDebugManagedCallback::UpdateModuleSymbols Method</span></span>
<span data-ttu-id="ddd95-103">Notifica al depurador que los símbolos para un módulo de Common Language Runtime han cambiado.</span><span class="sxs-lookup"><span data-stu-id="ddd95-103">Notifies the debugger that the symbols for a common language runtime module have changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddd95-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ddd95-104">Syntax</span></span>  
  
```cpp  
HRESULT UpdateModuleSymbols (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule,  
    [in] IStream            *pSymbolStream  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ddd95-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ddd95-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="ddd95-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el módulo en el que los símbolos han cambiado.</span><span class="sxs-lookup"><span data-stu-id="ddd95-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the module in which the symbols have changed.</span></span>  
  
 `pModule`  
 <span data-ttu-id="ddd95-107">de Un puntero a un objeto ICorDebugModule que representa el módulo en el que los símbolos han cambiado.</span><span class="sxs-lookup"><span data-stu-id="ddd95-107">[in] A pointer to an ICorDebugModule object that represents the module in which the symbols have changed.</span></span>  
  
 `pSymbolStream`  
 <span data-ttu-id="ddd95-108">de Puntero a un objeto de `IStream` COM de Win32 que contiene los símbolos modificados.</span><span class="sxs-lookup"><span data-stu-id="ddd95-108">[in] A pointer to a Win32 COM `IStream` object that contains the modified symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ddd95-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ddd95-109">Remarks</span></span>  
 <span data-ttu-id="ddd95-110">Este método proporciona una oportunidad para actualizar la vista del depurador de los símbolos de un módulo llamando a [ISymUnmanagedReader:: UpdateSymbolStore (](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) o [ISymUnmanagedReader:: replacesymbolstore (](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span><span class="sxs-lookup"><span data-stu-id="ddd95-110">This method provides an opportunity to update the debugger's view of a module's symbols by calling [ISymUnmanagedReader::UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) or [ISymUnmanagedReader::ReplaceSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span></span>  
  
 <span data-ttu-id="ddd95-111">Esta devolución de llamada puede producirse varias veces para el mismo módulo.</span><span class="sxs-lookup"><span data-stu-id="ddd95-111">This callback can occur multiple times for the same module.</span></span>  
  
 <span data-ttu-id="ddd95-112">Un depurador debe intentar enlazar puntos de interrupción sin enlazar en el nivel de origen.</span><span class="sxs-lookup"><span data-stu-id="ddd95-112">A debugger should try to bind unbound source-level breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddd95-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ddd95-113">Requirements</span></span>  
 <span data-ttu-id="ddd95-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ddd95-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddd95-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ddd95-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ddd95-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ddd95-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ddd95-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddd95-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddd95-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ddd95-118">See also</span></span>

- [<span data-ttu-id="ddd95-119">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ddd95-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)

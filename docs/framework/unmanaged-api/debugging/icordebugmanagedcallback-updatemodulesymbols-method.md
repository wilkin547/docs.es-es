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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0a506f05aac3b8335a0863c3152567fe05463a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415885"
---
# <a name="icordebugmanagedcallbackupdatemodulesymbols-method"></a><span data-ttu-id="d6483-102">ICorDebugManagedCallback::UpdateModuleSymbols (Método)</span><span class="sxs-lookup"><span data-stu-id="d6483-102">ICorDebugManagedCallback::UpdateModuleSymbols Method</span></span>
<span data-ttu-id="d6483-103">Notifica al depurador que han cambiado los símbolos para un módulo de common language runtime.</span><span class="sxs-lookup"><span data-stu-id="d6483-103">Notifies the debugger that the symbols for a common language runtime module have changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6483-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6483-104">Syntax</span></span>  
  
```  
HRESULT UpdateModuleSymbols (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule,  
    [in] IStream            *pSymbolStream  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d6483-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d6483-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="d6483-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el módulo en el que se han cambiado los símbolos.</span><span class="sxs-lookup"><span data-stu-id="d6483-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the module in which the symbols have changed.</span></span>  
  
 `pModule`  
 <span data-ttu-id="d6483-107">[in] Un puntero a un objeto ICorDebugModule que representa el módulo en el que se han cambiado los símbolos.</span><span class="sxs-lookup"><span data-stu-id="d6483-107">[in] A pointer to an ICorDebugModule object that represents the module in which the symbols have changed.</span></span>  
  
 `pSymbolStream`  
 <span data-ttu-id="d6483-108">[in] Un puntero a un COM Win32 `IStream` objeto que contiene los símbolos modificados.</span><span class="sxs-lookup"><span data-stu-id="d6483-108">[in] A pointer to a Win32 COM `IStream` object that contains the modified symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6483-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d6483-109">Remarks</span></span>  
 <span data-ttu-id="d6483-110">Este método proporciona una oportunidad para actualizar la vista del depurador de símbolos de un módulo mediante una llamada a [ISymUnmanagedReader:: UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) o [ISymUnmanagedReader:: ReplaceSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span><span class="sxs-lookup"><span data-stu-id="d6483-110">This method provides an opportunity to update the debugger's view of a module's symbols by calling [ISymUnmanagedReader::UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) or [ISymUnmanagedReader::ReplaceSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span></span>  
  
 <span data-ttu-id="d6483-111">Esta devolución de llamada puede aparecer varias veces para el mismo módulo.</span><span class="sxs-lookup"><span data-stu-id="d6483-111">This callback can occur multiple times for the same module.</span></span>  
  
 <span data-ttu-id="d6483-112">Un depurador debería intentar enlazar los puntos de interrupción de nivel de origen sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="d6483-112">A debugger should try to bind unbound source-level breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6483-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d6483-113">Requirements</span></span>  
 <span data-ttu-id="d6483-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6483-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6483-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6483-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6483-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6483-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6483-117">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6483-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6483-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6483-118">See Also</span></span>  
 [<span data-ttu-id="d6483-119">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d6483-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)

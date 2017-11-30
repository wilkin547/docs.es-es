---
title: "ICorDebugManagedCallback::UpdateModuleSymbols (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.UpdateModuleSymbols
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::UpdateModuleSymbols
helpviewer_keywords:
- UpdateModuleSymbols method [.NET Framework debugging]
- ICorDebugManagedCallback::UpdateModuleSymbols method [.NET Framework debugging]
ms.assetid: 0863f644-58e8-45a0-b0c3-a28e99b20938
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5a1606c256bbfd3b0a7de29b84aace1b4831a016
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbackupdatemodulesymbols-method"></a><span data-ttu-id="1ae8b-102">ICorDebugManagedCallback::UpdateModuleSymbols (Método)</span><span class="sxs-lookup"><span data-stu-id="1ae8b-102">ICorDebugManagedCallback::UpdateModuleSymbols Method</span></span>
<span data-ttu-id="1ae8b-103">Notifica al depurador que han cambiado los símbolos para un módulo de common language runtime.</span><span class="sxs-lookup"><span data-stu-id="1ae8b-103">Notifies the debugger that the symbols for a common language runtime module have changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ae8b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ae8b-104">Syntax</span></span>  
  
```  
HRESULT UpdateModuleSymbols (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule,  
    [in] IStream            *pSymbolStream  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1ae8b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1ae8b-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="1ae8b-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el módulo en el que se han cambiado los símbolos.</span><span class="sxs-lookup"><span data-stu-id="1ae8b-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the module in which the symbols have changed.</span></span>  
  
 `pModule`  
 <span data-ttu-id="1ae8b-107">[in] Un puntero a un objeto ICorDebugModule que representa el módulo en el que se han cambiado los símbolos.</span><span class="sxs-lookup"><span data-stu-id="1ae8b-107">[in] A pointer to an ICorDebugModule object that represents the module in which the symbols have changed.</span></span>  
  
 `pSymbolStream`  
 <span data-ttu-id="1ae8b-108">[in] Un puntero a un COM Win32 `IStream` objeto que contiene los símbolos modificados.</span><span class="sxs-lookup"><span data-stu-id="1ae8b-108">[in] A pointer to a Win32 COM `IStream` object that contains the modified symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ae8b-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1ae8b-109">Remarks</span></span>  
 <span data-ttu-id="1ae8b-110">Este método proporciona una oportunidad para actualizar la vista del depurador de símbolos de un módulo mediante una llamada a [ISymUnmanagedReader:: UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) o [ISymUnmanagedReader:: ReplaceSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span><span class="sxs-lookup"><span data-stu-id="1ae8b-110">This method provides an opportunity to update the debugger's view of a module's symbols by calling [ISymUnmanagedReader::UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) or [ISymUnmanagedReader::ReplaceSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span></span>  
  
 <span data-ttu-id="1ae8b-111">Esta devolución de llamada puede aparecer varias veces para el mismo módulo.</span><span class="sxs-lookup"><span data-stu-id="1ae8b-111">This callback can occur multiple times for the same module.</span></span>  
  
 <span data-ttu-id="1ae8b-112">Un depurador debería intentar enlazar los puntos de interrupción de nivel de origen sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="1ae8b-112">A debugger should try to bind unbound source-level breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ae8b-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1ae8b-113">Requirements</span></span>  
 <span data-ttu-id="1ae8b-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ae8b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ae8b-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1ae8b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1ae8b-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ae8b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ae8b-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ae8b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ae8b-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ae8b-118">See Also</span></span>  
 [<span data-ttu-id="1ae8b-119">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1ae8b-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)

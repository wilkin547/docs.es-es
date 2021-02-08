---
description: 'Más información acerca de: ICorDebugManagedCallback:: Updatemodulesymbols ((método)'
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
ms.openlocfilehash: 1e20ee50cdbe0b36d0677051f1fe2b1c777e6cd6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790937"
---
# <a name="icordebugmanagedcallbackupdatemodulesymbols-method"></a><span data-ttu-id="29f05-103">ICorDebugManagedCallback::UpdateModuleSymbols (Método)</span><span class="sxs-lookup"><span data-stu-id="29f05-103">ICorDebugManagedCallback::UpdateModuleSymbols Method</span></span>

<span data-ttu-id="29f05-104">Notifica al depurador que los símbolos para un módulo de Common Language Runtime han cambiado.</span><span class="sxs-lookup"><span data-stu-id="29f05-104">Notifies the debugger that the symbols for a common language runtime module have changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29f05-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="29f05-105">Syntax</span></span>  
  
```cpp  
HRESULT UpdateModuleSymbols (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule,  
    [in] IStream            *pSymbolStream  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29f05-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="29f05-106">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="29f05-107">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el módulo en el que los símbolos han cambiado.</span><span class="sxs-lookup"><span data-stu-id="29f05-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the module in which the symbols have changed.</span></span>  
  
 `pModule`  
 <span data-ttu-id="29f05-108">de Un puntero a un objeto ICorDebugModule que representa el módulo en el que los símbolos han cambiado.</span><span class="sxs-lookup"><span data-stu-id="29f05-108">[in] A pointer to an ICorDebugModule object that represents the module in which the symbols have changed.</span></span>  
  
 `pSymbolStream`  
 <span data-ttu-id="29f05-109">de Un puntero a un objeto COM Win32 `IStream` que contiene los símbolos modificados.</span><span class="sxs-lookup"><span data-stu-id="29f05-109">[in] A pointer to a Win32 COM `IStream` object that contains the modified symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29f05-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="29f05-110">Remarks</span></span>  

 <span data-ttu-id="29f05-111">Este método proporciona una oportunidad para actualizar la vista del depurador de los símbolos de un módulo llamando a [ISymUnmanagedReader:: UpdateSymbolStore (](../diagnostics/isymunmanagedreader-updatesymbolstore-method.md) o [ISymUnmanagedReader:: replacesymbolstore (](../diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span><span class="sxs-lookup"><span data-stu-id="29f05-111">This method provides an opportunity to update the debugger's view of a module's symbols by calling [ISymUnmanagedReader::UpdateSymbolStore](../diagnostics/isymunmanagedreader-updatesymbolstore-method.md) or [ISymUnmanagedReader::ReplaceSymbolStore](../diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span></span>  
  
 <span data-ttu-id="29f05-112">Esta devolución de llamada puede producirse varias veces para el mismo módulo.</span><span class="sxs-lookup"><span data-stu-id="29f05-112">This callback can occur multiple times for the same module.</span></span>  
  
 <span data-ttu-id="29f05-113">Un depurador debe intentar enlazar puntos de interrupción sin enlazar en el nivel de origen.</span><span class="sxs-lookup"><span data-stu-id="29f05-113">A debugger should try to bind unbound source-level breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29f05-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="29f05-114">Requirements</span></span>  

 <span data-ttu-id="29f05-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29f05-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29f05-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="29f05-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="29f05-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29f05-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29f05-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29f05-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29f05-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="29f05-119">See also</span></span>

- [<span data-ttu-id="29f05-120">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="29f05-120">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)

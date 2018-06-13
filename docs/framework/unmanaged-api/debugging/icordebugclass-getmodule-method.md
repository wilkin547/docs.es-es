---
title: ICorDebugClass::GetModule (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetModule
helpviewer_keywords:
- GetModule method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetModule method [.NET Framework debugging]
ms.assetid: 87029cc4-e5e1-42d5-8b98-655bb7ece520
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c52795251b5cacebe749b1eedf918f8b20497796
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402902"
---
# <a name="icordebugclassgetmodule-method"></a><span data-ttu-id="93eb9-102">ICorDebugClass::GetModule (Método)</span><span class="sxs-lookup"><span data-stu-id="93eb9-102">ICorDebugClass::GetModule Method</span></span>
<span data-ttu-id="93eb9-103">Obtiene el módulo que define esta clase.</span><span class="sxs-lookup"><span data-stu-id="93eb9-103">Gets the module that defines this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93eb9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="93eb9-104">Syntax</span></span>  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule    **pModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="93eb9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="93eb9-105">Parameters</span></span>  
 `pModule`  
 <span data-ttu-id="93eb9-106">[out] Un puntero a la dirección de un objeto ICorDebugModule que representa el módulo en el que se define esta clase.</span><span class="sxs-lookup"><span data-stu-id="93eb9-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this class is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93eb9-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="93eb9-107">Requirements</span></span>  
 <span data-ttu-id="93eb9-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93eb9-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93eb9-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="93eb9-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="93eb9-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93eb9-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93eb9-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93eb9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

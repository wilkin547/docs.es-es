---
description: 'Más información acerca de: ICorDebugClass:: GetModule (método)'
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
ms.openlocfilehash: 338ea5aeede4a209f7a3e3ed685ae9bd84105890
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711549"
---
# <a name="icordebugclassgetmodule-method"></a><span data-ttu-id="c62da-103">ICorDebugClass::GetModule (Método)</span><span class="sxs-lookup"><span data-stu-id="c62da-103">ICorDebugClass::GetModule Method</span></span>

<span data-ttu-id="c62da-104">Obtiene el módulo que define esta clase.</span><span class="sxs-lookup"><span data-stu-id="c62da-104">Gets the module that defines this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c62da-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c62da-105">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule    **pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c62da-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c62da-106">Parameters</span></span>  

 `pModule`  
 <span data-ttu-id="c62da-107">enuncia Puntero a la dirección de un objeto ICorDebugModule que representa el módulo en el que se define esta clase.</span><span class="sxs-lookup"><span data-stu-id="c62da-107">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this class is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c62da-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c62da-108">Requirements</span></span>  

 <span data-ttu-id="c62da-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c62da-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c62da-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c62da-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c62da-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c62da-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c62da-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c62da-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

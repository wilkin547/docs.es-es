---
description: 'Más información acerca de: ICorDebugAssembly:: Enumeratemodules ((método)'
title: ICorDebugAssembly::EnumerateModules (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.EnumerateModules
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::EnumerateModules
helpviewer_keywords:
- ICorDebugAssembly::EnumerateModules method [.NET Framework debugging]
- EnumerateModules method [.NET Framework debugging]
ms.assetid: c7ba51a1-0dd5-4452-b471-232febe0f897
topic_type:
- apiref
ms.openlocfilehash: 5d34fb1762e8f953007d6fcb59ab1147028f06a8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722872"
---
# <a name="icordebugassemblyenumeratemodules-method"></a><span data-ttu-id="35e4f-103">ICorDebugAssembly::EnumerateModules (Método)</span><span class="sxs-lookup"><span data-stu-id="35e4f-103">ICorDebugAssembly::EnumerateModules Method</span></span>

<span data-ttu-id="35e4f-104">Obtiene un enumerador para los módulos incluidos en `ICorDebugAssembly` .</span><span class="sxs-lookup"><span data-stu-id="35e4f-104">Gets an enumerator for the modules contained in the `ICorDebugAssembly`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35e4f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35e4f-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateModules (  
    [out] ICorDebugModuleEnum **ppModules  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35e4f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="35e4f-106">Parameters</span></span>  

 `ppModules`  
 <span data-ttu-id="35e4f-107">enuncia Puntero a la dirección de la interfaz ICorDebugModuleEnum (que es el enumerador.</span><span class="sxs-lookup"><span data-stu-id="35e4f-107">[out] A pointer to the address of the ICorDebugModuleEnum interface that is the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35e4f-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="35e4f-108">Requirements</span></span>  

 <span data-ttu-id="35e4f-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35e4f-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35e4f-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="35e4f-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35e4f-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35e4f-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35e4f-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35e4f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

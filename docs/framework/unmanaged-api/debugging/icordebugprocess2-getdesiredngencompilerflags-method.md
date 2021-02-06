---
description: 'Más información sobre: ICorDebugProcess2:: Getdesiredngencompilerflags ((método)'
title: ICorDebugProcess2::GetDesiredNGENCompilerFlags (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags method [.NET Framework debugging]
- GetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: fc834580-3a90-4315-95d2-349b6bb7d059
topic_type:
- apiref
ms.openlocfilehash: ddc1c3a958ef42ab51d0ae06fd7ff29b13829c3c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650220"
---
# <a name="icordebugprocess2getdesiredngencompilerflags-method"></a><span data-ttu-id="2e00e-103">ICorDebugProcess2::GetDesiredNGENCompilerFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="2e00e-103">ICorDebugProcess2::GetDesiredNGENCompilerFlags Method</span></span>

<span data-ttu-id="2e00e-104">Obtiene la configuración actual del marcador de compilador que el Common Language Runtime (CLR) utiliza para seleccionar la imagen precompilada correcta (es decir, nativa) que se va a cargar en este proceso.</span><span class="sxs-lookup"><span data-stu-id="2e00e-104">Gets the current compiler flag settings that the common language runtime (CLR) uses to select the correct precompiled (that is, native) image to be loaded into this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e00e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2e00e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDesiredNGENCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e00e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2e00e-106">Parameters</span></span>  

 `pdwFlags`  
 <span data-ttu-id="2e00e-107">enuncia Un puntero a una combinación bit a bit de los valores de enumeración de [cordebugjitcompilerflags (](cordebugjitcompilerflags-enumeration.md) que se usan para seleccionar la imagen precompilada correcta que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="2e00e-107">[out] A pointer to a bitwise combination of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration values that are used to select the correct precompiled image to be loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e00e-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2e00e-108">Remarks</span></span>  

 <span data-ttu-id="2e00e-109">Use el método [ICorDebugProcess2:: SetDesiredNGENCompilerFlags (](icordebugprocess2-setdesiredngencompilerflags-method.md) para establecer las marcas que CLR usará para seleccionar la imagen precompilada correcta que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="2e00e-109">Use the [ICorDebugProcess2::SetDesiredNGENCompilerFlags](icordebugprocess2-setdesiredngencompilerflags-method.md) method to set the flags that the CLR will use to select the correct pre-compiled image to load.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e00e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2e00e-110">Requirements</span></span>  

 <span data-ttu-id="2e00e-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e00e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e00e-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2e00e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2e00e-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e00e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e00e-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e00e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

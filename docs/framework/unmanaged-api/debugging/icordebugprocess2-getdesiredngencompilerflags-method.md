---
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
ms.openlocfilehash: d2e54f0b16300673409eb2f5757338dfa3011e61
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213002"
---
# <a name="icordebugprocess2getdesiredngencompilerflags-method"></a><span data-ttu-id="81ffb-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="81ffb-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="81ffb-103">Obtiene la configuración actual del marcador de compilador que el Common Language Runtime (CLR) utiliza para seleccionar la imagen precompilada correcta (es decir, nativa) que se va a cargar en este proceso.</span><span class="sxs-lookup"><span data-stu-id="81ffb-103">Gets the current compiler flag settings that the common language runtime (CLR) uses to select the correct precompiled (that is, native) image to be loaded into this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81ffb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="81ffb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDesiredNGENCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81ffb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="81ffb-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="81ffb-106">enuncia Un puntero a una combinación bit a bit de los valores de enumeración de [cordebugjitcompilerflags (](cordebugjitcompilerflags-enumeration.md) que se usan para seleccionar la imagen precompilada correcta que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="81ffb-106">[out] A pointer to a bitwise combination of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration values that are used to select the correct precompiled image to be loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81ffb-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="81ffb-107">Remarks</span></span>  
 <span data-ttu-id="81ffb-108">Use el método [ICorDebugProcess2:: SetDesiredNGENCompilerFlags (](icordebugprocess2-setdesiredngencompilerflags-method.md) para establecer las marcas que CLR usará para seleccionar la imagen precompilada correcta que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="81ffb-108">Use the [ICorDebugProcess2::SetDesiredNGENCompilerFlags](icordebugprocess2-setdesiredngencompilerflags-method.md) method to set the flags that the CLR will use to select the correct pre-compiled image to load.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81ffb-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="81ffb-109">Requirements</span></span>  
 <span data-ttu-id="81ffb-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81ffb-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81ffb-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="81ffb-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="81ffb-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81ffb-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81ffb-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81ffb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

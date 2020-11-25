---
title: ICorDebugProcess7::SetWriteableMetadataUpdateMode (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugProcess7.SetWriteableMetadataUpdateMode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 8589bba7-7304-45ba-9e31-7bf43dfd5c19
topic_type:
- apiref
ms.openlocfilehash: 5671f8cb51210c27dffdedba28b4b145b3fedc55
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732559"
---
# <a name="icordebugprocess7setwriteablemetadataupdatemode-method"></a><span data-ttu-id="ac2b2-102">ICorDebugProcess7::SetWriteableMetadataUpdateMode (Método)</span><span class="sxs-lookup"><span data-stu-id="ac2b2-102">ICorDebugProcess7::SetWriteableMetadataUpdateMode Method</span></span>

<span data-ttu-id="ac2b2-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="ac2b2-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="ac2b2-104">Configura cómo el depurador controla las actualizaciones en memoria de los metadatos dentro del proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="ac2b2-104">Configures how the debugger handles in-memory updates to metadata within the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac2b2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac2b2-105">Syntax</span></span>  
  
```cpp
HRESULT SetWriteableMetadataUpdateMode(  
   WriteableMetadataUpdateMode flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac2b2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ac2b2-106">Parameters</span></span>  

 `flags`  
 <span data-ttu-id="ac2b2-107">Un valor de enumeración [writeablemetadataupdatemode (](writeablemetadataupdatemode-enumeration.md) que especifica si las actualizaciones en memoria de los metadatos en el proceso de destino son visibles ( `WriteableMetadataUpdateMode::AlwaysShowUpdates` ) o no ( `WriteableMetadataUpdateMode::LegacyCompatPolicy` ) en el depurador.</span><span class="sxs-lookup"><span data-stu-id="ac2b2-107">A [WriteableMetadataUpdateMode](writeablemetadataupdatemode-enumeration.md) enumeration value that specifies whether in-memory updates to metadata in the target process are visible (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) or not visible (`WriteableMetadataUpdateMode::LegacyCompatPolicy`) to the debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac2b2-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ac2b2-108">Remarks</span></span>  

 <span data-ttu-id="ac2b2-109">Actualiza los metadatos del proceso de destino que proceden de Editar y Continuar, de un generador de perfiles o de <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ac2b2-109">Updates to the metadata of the target process can come from Edit and Continue, a profiler, or <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac2b2-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac2b2-110">Requirements</span></span>  

 <span data-ttu-id="ac2b2-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac2b2-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac2b2-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ac2b2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac2b2-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac2b2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac2b2-114">**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac2b2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac2b2-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ac2b2-115">See also</span></span>

- [<span data-ttu-id="ac2b2-116">ICorDebugProcess7 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ac2b2-116">ICorDebugProcess7 Interface</span></span>](icordebugprocess7-interface.md)
- [<span data-ttu-id="ac2b2-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="ac2b2-117">Debugging Interfaces</span></span>](debugging-interfaces.md)

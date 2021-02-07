---
description: 'Más información acerca de: enumeración ASM_DISPLAY_FLAGS'
title: ASM_DISPLAY_FLAGS (Enumeración)
ms.date: 03/30/2017
api_name:
- ASM_DISPLAY_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_DISPLAY_FLAGS
helpviewer_keywords:
- ASM_DISPLAY_FLAGS enumeration [.NET Framework fusion]
ms.assetid: dbade6c9-9d26-4a79-9fd2-46108edd12d7
topic_type:
- apiref
ms.openlocfilehash: 82412fd4675d855f70183458bf704ac8498a6de7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761374"
---
# <a name="asm_display_flags-enumeration"></a><span data-ttu-id="a1f0a-103">ASM_DISPLAY_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="a1f0a-103">ASM_DISPLAY_FLAGS Enumeration</span></span>

<span data-ttu-id="a1f0a-104">Indica la versión, la compilación, la referencia cultural, la firma, etc., del ensamblado cuyo nombre para mostrar se recuperará mediante el método [IAssemblyName:: getDisplayName](iassemblyname-getdisplayname-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a1f0a-104">Indicates the version, build, culture, signature, and so on, of the assembly whose display name will be retrieved by the [IAssemblyName::GetDisplayName](iassemblyname-getdisplayname-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1f0a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1f0a-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
  
    ASM_DISPLAYF_VERSION                 = 0x01,  
    ASM_DISPLAYF_CULTURE                 = 0x02,  
    ASM_DISPLAYF_PUBLIC_KEY_TOKEN        = 0x04,  
    ASM_DISPLAYF_PUBLIC_KEY              = 0x08,  
    ASM_DISPLAYF_CUSTOM                  = 0x10,  
    ASM_DISPLAYF_PROCESSORARCHITECTURE   = 0x20,  
    ASM_DISPLAYF_LANGUAGEID              = 0x40,  
    ASM_DISPLAYF_RETARGET                = 0x80,  
    ASM_DISPLAYF_CONFIG_MASK             = 0x100,  
    ASM_DISPLAYF_MVID                    = 0x200,  
    ASM_DISPLAYF_FULL                    =
                      ASM_DISPLAYF_VERSION           |
                      ASM_DISPLAYF_CULTURE           |
                      ASM_DISPLAYF_PUBLIC_KEY_TOKEN  |
                      ASM_DISPLAYF_RETARGET          |
                      ASM_DISPLAYF_PROCESSORARCHITECTURE  
  
} ASM_DISPLAY_FLAGS;  
```  
  
## <a name="remarks"></a><span data-ttu-id="a1f0a-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a1f0a-106">Remarks</span></span>  

 <span data-ttu-id="a1f0a-107">`ASM_DISPLAYF_FULL` refleja todos los cambios realizados en la versión del objeto [IAssemblyName](iassemblyname-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="a1f0a-107">`ASM_DISPLAYF_FULL` reflects any changes made to the version of the [IAssemblyName](iassemblyname-interface.md) object.</span></span> <span data-ttu-id="a1f0a-108">No suponga que el valor devuelto es inmutable.</span><span class="sxs-lookup"><span data-stu-id="a1f0a-108">Do not assume that the returned value is immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1f0a-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a1f0a-109">Requirements</span></span>  

 <span data-ttu-id="a1f0a-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1f0a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1f0a-111">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="a1f0a-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a1f0a-112">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a1f0a-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a1f0a-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1f0a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1f0a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1f0a-114">See also</span></span>

- [<span data-ttu-id="a1f0a-115">IAssemblyName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a1f0a-115">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="a1f0a-116">Enumeraciones de fusión</span><span class="sxs-lookup"><span data-stu-id="a1f0a-116">Fusion Enumerations</span></span>](fusion-enumerations.md)

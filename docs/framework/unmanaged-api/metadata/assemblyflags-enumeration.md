---
title: AssemblyFlags (Enumeración)
ms.date: 03/30/2017
api_name:
- AssemblyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyFlags
helpviewer_keywords:
- AssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: 40f9bd9e-16ec-447e-81b0-168c875e9866
topic_type:
- apiref
ms.openlocfilehash: 1cb84b94b37a2e9e8dd4d20d09cbca82db290c0f
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009462"
---
# <a name="assemblyflags-enumeration"></a><span data-ttu-id="c5b3c-102">AssemblyFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="c5b3c-102">AssemblyFlags Enumeration</span></span>
<span data-ttu-id="c5b3c-103">Contiene valores que describen las características de tiempo de ejecución de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c5b3c-103">Contains values that describe run-time features of an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5b3c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c5b3c-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="c5b3c-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="c5b3c-105">Members</span></span>  
  
|<span data-ttu-id="c5b3c-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="c5b3c-106">Member</span></span>|<span data-ttu-id="c5b3c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c5b3c-107">Description</span></span>|  
|------------|-----------------|  
|`afImplicitExportedTypes`|<span data-ttu-id="c5b3c-108">Especifica que las definiciones de tipos exportadas están implícitas dentro de los archivos que componen el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c5b3c-108">Specifies that exported type definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="c5b3c-109">En las versiones 1,0 y 1,1 de .NET Framework, se supone que este valor siempre está establecido.</span><span class="sxs-lookup"><span data-stu-id="c5b3c-109">In the .NET Framework versions 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afImplicitResources`|<span data-ttu-id="c5b3c-110">Especifica que las definiciones de recursos están implícitas dentro de los archivos que componen el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c5b3c-110">Specifies that resource definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="c5b3c-111">En el .NET Framework 1,0 y 1,1, siempre se supone que se establece este valor.</span><span class="sxs-lookup"><span data-stu-id="c5b3c-111">In the .NET Framework 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afNonSideBySideAppDomain`|<span data-ttu-id="c5b3c-112">Especifica que el ensamblado no se puede ejecutar con otras versiones si se ejecutan en el mismo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="c5b3c-112">Specifies that the assembly cannot execute with other versions if they are running in the same application domain.</span></span>|  
|`afNonSideBySideProcess`|<span data-ttu-id="c5b3c-113">Especifica que el ensamblado no se puede ejecutar con otras versiones si se ejecutan en el mismo proceso.</span><span class="sxs-lookup"><span data-stu-id="c5b3c-113">Specifies that the assembly cannot execute with other versions if they are running in the same process.</span></span>|  
|`afNonSideBySideMachine`|<span data-ttu-id="c5b3c-114">Especifica que el ensamblado no se puede ejecutar con otras versiones si se ejecutan en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="c5b3c-114">Specifies that the assembly cannot execute with other versions if they are running on the same computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5b3c-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c5b3c-115">Remarks</span></span>  
 <span data-ttu-id="c5b3c-116">Los valores entre 0x0010 y 0x0070, ambos incluidos, se usan para describir las características de compatibilidad en paralelo del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="c5b3c-116">The values between 0x0010 and 0x0070, inclusive, are used to describe side-by-side compatibility features of the referenced assembly.</span></span> <span data-ttu-id="c5b3c-117">Si no se establece ninguno de estos valores, se supone que el ensamblado es compatible en paralelo.</span><span class="sxs-lookup"><span data-stu-id="c5b3c-117">If none of these values are set, the assembly is assumed to be side-by-side compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5b3c-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c5b3c-118">Requirements</span></span>  
 <span data-ttu-id="c5b3c-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5b3c-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5b3c-120">**Encabezado:** MsCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c5b3c-120">**Header:** MsCorEE.h</span></span>  
  
 <span data-ttu-id="c5b3c-121">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c5b3c-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c5b3c-122">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5b3c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5b3c-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c5b3c-123">See also</span></span>

- [<span data-ttu-id="c5b3c-124">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="c5b3c-124">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="c5b3c-125">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c5b3c-125">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)

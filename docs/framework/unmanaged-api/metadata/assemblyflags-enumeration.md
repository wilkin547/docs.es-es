---
description: 'Más información sobre: enumeración AssemblyFlags ('
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
ms.openlocfilehash: 17cc0dec305c21d21693fe8f4f8d82c039f73278
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679009"
---
# <a name="assemblyflags-enumeration"></a><span data-ttu-id="5ad4b-103">AssemblyFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="5ad4b-103">AssemblyFlags Enumeration</span></span>

<span data-ttu-id="5ad4b-104">Contiene valores que describen las características de tiempo de ejecución de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5ad4b-104">Contains values that describe run-time features of an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ad4b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5ad4b-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="5ad4b-106">Members</span><span class="sxs-lookup"><span data-stu-id="5ad4b-106">Members</span></span>  
  
|<span data-ttu-id="5ad4b-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="5ad4b-107">Member</span></span>|<span data-ttu-id="5ad4b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="5ad4b-108">Description</span></span>|  
|------------|-----------------|  
|`afImplicitExportedTypes`|<span data-ttu-id="5ad4b-109">Especifica que las definiciones de tipos exportadas están implícitas dentro de los archivos que componen el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5ad4b-109">Specifies that exported type definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="5ad4b-110">En las versiones 1,0 y 1,1 de .NET Framework, se supone que este valor siempre está establecido.</span><span class="sxs-lookup"><span data-stu-id="5ad4b-110">In the .NET Framework versions 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afImplicitResources`|<span data-ttu-id="5ad4b-111">Especifica que las definiciones de recursos están implícitas dentro de los archivos que componen el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5ad4b-111">Specifies that resource definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="5ad4b-112">En el .NET Framework 1,0 y 1,1, siempre se supone que se establece este valor.</span><span class="sxs-lookup"><span data-stu-id="5ad4b-112">In the .NET Framework 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afNonSideBySideAppDomain`|<span data-ttu-id="5ad4b-113">Especifica que el ensamblado no se puede ejecutar con otras versiones si se ejecutan en el mismo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5ad4b-113">Specifies that the assembly cannot execute with other versions if they are running in the same application domain.</span></span>|  
|`afNonSideBySideProcess`|<span data-ttu-id="5ad4b-114">Especifica que el ensamblado no se puede ejecutar con otras versiones si se ejecutan en el mismo proceso.</span><span class="sxs-lookup"><span data-stu-id="5ad4b-114">Specifies that the assembly cannot execute with other versions if they are running in the same process.</span></span>|  
|`afNonSideBySideMachine`|<span data-ttu-id="5ad4b-115">Especifica que el ensamblado no se puede ejecutar con otras versiones si se ejecutan en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="5ad4b-115">Specifies that the assembly cannot execute with other versions if they are running on the same computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ad4b-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5ad4b-116">Remarks</span></span>  

 <span data-ttu-id="5ad4b-117">Los valores entre 0x0010 y 0x0070, ambos incluidos, se usan para describir las características de compatibilidad en paralelo del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="5ad4b-117">The values between 0x0010 and 0x0070, inclusive, are used to describe side-by-side compatibility features of the referenced assembly.</span></span> <span data-ttu-id="5ad4b-118">Si no se establece ninguno de estos valores, se supone que el ensamblado es compatible en paralelo.</span><span class="sxs-lookup"><span data-stu-id="5ad4b-118">If none of these values are set, the assembly is assumed to be side-by-side compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ad4b-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5ad4b-119">Requirements</span></span>  

 <span data-ttu-id="5ad4b-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ad4b-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ad4b-121">**Encabezado:** MsCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5ad4b-121">**Header:** MsCorEE.h</span></span>  
  
 <span data-ttu-id="5ad4b-122">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5ad4b-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5ad4b-123">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ad4b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ad4b-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ad4b-124">See also</span></span>

- [<span data-ttu-id="5ad4b-125">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="5ad4b-125">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="5ad4b-126">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5ad4b-126">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)

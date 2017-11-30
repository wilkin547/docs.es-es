---
title: "AssemblyFlags (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: AssemblyFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: AssemblyFlags
helpviewer_keywords: AssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: 40f9bd9e-16ec-447e-81b0-168c875e9866
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 91760b6d16b663257bf3d89915da3bd88b3411bf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="assemblyflags-enumeration"></a><span data-ttu-id="b9684-102">AssemblyFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="b9684-102">AssemblyFlags Enumeration</span></span>
<span data-ttu-id="b9684-103">Contiene valores que describen las características de tiempo de ejecución de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b9684-103">Contains values that describe run-time features of an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9684-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b9684-104">Syntax</span></span>  
  
```  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="b9684-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="b9684-105">Members</span></span>  
  
|<span data-ttu-id="b9684-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="b9684-106">Member</span></span>|<span data-ttu-id="b9684-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b9684-107">Description</span></span>|  
|------------|-----------------|  
|`afImplicitExportedTypes`|<span data-ttu-id="b9684-108">Especifica que las definiciones de tipo exportado son implícitas dentro de los archivos que componen el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b9684-108">Specifies that exported type definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="b9684-109">En las versiones 1.0 y 1.1 de .NET Framework, se supone que este valor se establezca.</span><span class="sxs-lookup"><span data-stu-id="b9684-109">In the .NET Framework versions 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afImplicitResources`|<span data-ttu-id="b9684-110">Especifica que las definiciones de recursos están implícitas dentro de los archivos que componen el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b9684-110">Specifies that resource definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="b9684-111">En .NET Framework 1.0 y 1.1, este valor siempre se supone que para puede establecer.</span><span class="sxs-lookup"><span data-stu-id="b9684-111">In the .NET Framework 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afNonSideBySideAppDomain`|<span data-ttu-id="b9684-112">Especifica que el ensamblado no puede ejecutarse con otras versiones si se están ejecutando en el mismo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b9684-112">Specifies that the assembly cannot execute with other versions if they are running in the same application domain.</span></span>|  
|`afNonSideBySideProcess`|<span data-ttu-id="b9684-113">Especifica que el ensamblado no puede ejecutarse con otras versiones si se están ejecutando en el mismo proceso.</span><span class="sxs-lookup"><span data-stu-id="b9684-113">Specifies that the assembly cannot execute with other versions if they are running in the same process.</span></span>|  
|`afNonSideBySideMachine`|<span data-ttu-id="b9684-114">Especifica que el ensamblado no puede ejecutarse con otras versiones si se ejecutan en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="b9684-114">Specifies that the assembly cannot execute with other versions if they are running on the same computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9684-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b9684-115">Remarks</span></span>  
 <span data-ttu-id="b9684-116">Los valores entre 0 x 0010 y 0 x 0070, ambos inclusive, se utilizan para describir las características de compatibilidad en paralelo del ensamblado que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="b9684-116">The values between 0x0010 and 0x0070, inclusive, are used to describe side-by-side compatibility features of the referenced assembly.</span></span> <span data-ttu-id="b9684-117">Si se establece ninguno de estos valores, se supone que el ensamblado es compatible en paralelo.</span><span class="sxs-lookup"><span data-stu-id="b9684-117">If none of these values are set, the assembly is assumed to be side-by-side compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9684-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b9684-118">Requirements</span></span>  
 <span data-ttu-id="b9684-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9684-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9684-120">**Encabezado:** MsCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b9684-120">**Header:** MsCorEE.h</span></span>  
  
 <span data-ttu-id="b9684-121">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b9684-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b9684-122">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9684-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9684-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9684-123">See Also</span></span>  
 [<span data-ttu-id="b9684-124">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="b9684-124">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [<span data-ttu-id="b9684-125">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b9684-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)

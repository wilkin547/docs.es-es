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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7c86a4fd2788c8ea2df5d9e54c5c221afd179704
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906001"
---
# <a name="assemblyflags-enumeration"></a><span data-ttu-id="bf5e9-102">AssemblyFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="bf5e9-102">AssemblyFlags Enumeration</span></span>
<span data-ttu-id="bf5e9-103">Contiene valores que describen las características de tiempo de ejecución de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bf5e9-103">Contains values that describe run-time features of an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf5e9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf5e9-104">Syntax</span></span>  
  
```  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="bf5e9-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="bf5e9-105">Members</span></span>  
  
|<span data-ttu-id="bf5e9-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="bf5e9-106">Member</span></span>|<span data-ttu-id="bf5e9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf5e9-107">Description</span></span>|  
|------------|-----------------|  
|`afImplicitExportedTypes`|<span data-ttu-id="bf5e9-108">Especifica que las definiciones de tipo exportado son implícitas dentro de los archivos que componen el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bf5e9-108">Specifies that exported type definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="bf5e9-109">En las versiones 1.0 y 1.1 de .NET Framework, se supone que este valor debe establecerse.</span><span class="sxs-lookup"><span data-stu-id="bf5e9-109">In the .NET Framework versions 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afImplicitResources`|<span data-ttu-id="bf5e9-110">Especifica que las definiciones de recursos están implícitas dentro de los archivos que componen el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bf5e9-110">Specifies that resource definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="bf5e9-111">En .NET Framework 1.0 y 1.1, se supone que este valor debe establecerse.</span><span class="sxs-lookup"><span data-stu-id="bf5e9-111">In the .NET Framework 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afNonSideBySideAppDomain`|<span data-ttu-id="bf5e9-112">Especifica que el ensamblado no puede ejecutarse con otras versiones si se están ejecutando en el mismo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="bf5e9-112">Specifies that the assembly cannot execute with other versions if they are running in the same application domain.</span></span>|  
|`afNonSideBySideProcess`|<span data-ttu-id="bf5e9-113">Especifica que el ensamblado no puede ejecutarse con otras versiones si se están ejecutando en el mismo proceso.</span><span class="sxs-lookup"><span data-stu-id="bf5e9-113">Specifies that the assembly cannot execute with other versions if they are running in the same process.</span></span>|  
|`afNonSideBySideMachine`|<span data-ttu-id="bf5e9-114">Especifica que el ensamblado no puede ejecutarse con otras versiones si se están ejecutando en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="bf5e9-114">Specifies that the assembly cannot execute with other versions if they are running on the same computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf5e9-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bf5e9-115">Remarks</span></span>  
 <span data-ttu-id="bf5e9-116">Los valores comprendidos entre 0 x 0010 y 0 x 0070, ambos inclusive, se utilizan para describir las características de compatibilidad en paralelo del ensamblado que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="bf5e9-116">The values between 0x0010 and 0x0070, inclusive, are used to describe side-by-side compatibility features of the referenced assembly.</span></span> <span data-ttu-id="bf5e9-117">Si se establece ninguno de estos valores, se supone que el ensamblado para que sea compatible en paralelo.</span><span class="sxs-lookup"><span data-stu-id="bf5e9-117">If none of these values are set, the assembly is assumed to be side-by-side compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf5e9-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf5e9-118">Requirements</span></span>  
 <span data-ttu-id="bf5e9-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf5e9-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf5e9-120">**Encabezado**: MsCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bf5e9-120">**Header:** MsCorEE.h</span></span>  
  
 <span data-ttu-id="bf5e9-121">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bf5e9-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bf5e9-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf5e9-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf5e9-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf5e9-123">See also</span></span>

- [<span data-ttu-id="bf5e9-124">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="bf5e9-124">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="bf5e9-125">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf5e9-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)

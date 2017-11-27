---
title: ASSEMBLY_INFO (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ASSEMBLY_INFO
api_location: fusion.dll
api_type: COM
f1_keywords: ASSEMBLY_INFO
helpviewer_keywords: ASSEMBLY_INFO structure [.NET Framework fusion]
ms.assetid: b3cbb47c-457f-4083-8895-49562ca99ab8
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d532bbd2d338f942c09c4213620468a3361db5f6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="assemblyinfo-structure"></a><span data-ttu-id="2f4dc-102">ASSEMBLY_INFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="2f4dc-102">ASSEMBLY_INFO Structure</span></span>
<span data-ttu-id="2f4dc-103">Contiene información sobre un ensamblado que está registrado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="2f4dc-103">Contains information about an assembly that is registered in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f4dc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2f4dc-104">Syntax</span></span>  
  
```  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="2f4dc-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="2f4dc-105">Members</span></span>  
  
|<span data-ttu-id="2f4dc-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="2f4dc-106">Member</span></span>|<span data-ttu-id="2f4dc-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f4dc-107">Description</span></span>|  
|------------|-----------------|  
|`cbAssemblyInfo`|<span data-ttu-id="2f4dc-108">El tamaño, en bytes, de la estructura.</span><span class="sxs-lookup"><span data-stu-id="2f4dc-108">The size, in bytes, of the structure.</span></span> <span data-ttu-id="2f4dc-109">Este campo está reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="2f4dc-109">This field is reserved for future extensibility.</span></span>|  
|`dwAssemblyFlags`|<span data-ttu-id="2f4dc-110">Marcadores que indican los detalles sobre el ensamblado de la instalación.</span><span class="sxs-lookup"><span data-stu-id="2f4dc-110">Flags that indicate installation details about the assembly.</span></span> <span data-ttu-id="2f4dc-111">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="2f4dc-111">The following values are supported:</span></span><br /><br /> <span data-ttu-id="2f4dc-112">-El valor ASSEMBLYINFO_FLAG_INSTALLED, que indica que el ensamblado está instalado.</span><span class="sxs-lookup"><span data-stu-id="2f4dc-112">-   The ASSEMBLYINFO_FLAG_INSTALLED value, which indicates that the assembly is installed.</span></span> <span data-ttu-id="2f4dc-113">La versión actual de .NET Framework siempre establece `dwAssemblyFlags` en este valor.</span><span class="sxs-lookup"><span data-stu-id="2f4dc-113">The current version of the .NET Framework always sets `dwAssemblyFlags` to this value.</span></span><br /><span data-ttu-id="2f4dc-114">-El valor ASSEMBLYINFO_FLAG_PAYLOADRESIDENT, que indica que el ensamblado es un residente de carga.</span><span class="sxs-lookup"><span data-stu-id="2f4dc-114">-   The ASSEMBLYINFO_FLAG_PAYLOADRESIDENT value, which indicates that the assembly is a payload resident.</span></span> <span data-ttu-id="2f4dc-115">La versión actual de .NET Framework nunca establece `dwAssemblyFlags` en este valor.</span><span class="sxs-lookup"><span data-stu-id="2f4dc-115">The current version of the .NET Framework never sets `dwAssemblyFlags` to this value.</span></span>|  
|`uliAssemblySizeInKB`|<span data-ttu-id="2f4dc-116">El tamaño total, en kilobytes, de los archivos que contiene el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2f4dc-116">The total size, in kilobytes, of the files that the assembly contains.</span></span>|  
|`pszCurrentAssemblyPathBuf`|<span data-ttu-id="2f4dc-117">Un puntero a un búfer de cadena que contiene la ruta de acceso actual al archivo de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="2f4dc-117">A pointer to a string buffer that holds the current path to the manifest file.</span></span> <span data-ttu-id="2f4dc-118">La ruta de acceso debe terminar con un carácter nulo.</span><span class="sxs-lookup"><span data-stu-id="2f4dc-118">The path must end with a null character.</span></span>|  
|`cchBuf`|<span data-ttu-id="2f4dc-119">El número de caracteres anchos, incluido el terminador nulo, que `pszCurrentAssemblyPathBuf` contiene.</span><span class="sxs-lookup"><span data-stu-id="2f4dc-119">The number of wide characters, including the null terminator, that `pszCurrentAssemblyPathBuf` contains.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2f4dc-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2f4dc-120">Requirements</span></span>  
 <span data-ttu-id="2f4dc-121">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f4dc-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f4dc-122">**Encabezado:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="2f4dc-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="2f4dc-123">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f4dc-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f4dc-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f4dc-124">See Also</span></span>  
 [<span data-ttu-id="2f4dc-125">Estructuras de fusión</span><span class="sxs-lookup"><span data-stu-id="2f4dc-125">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
 [<span data-ttu-id="2f4dc-126">Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="2f4dc-126">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)

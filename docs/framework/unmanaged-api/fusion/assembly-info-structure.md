---
description: 'Más información acerca de: estructura de ASSEMBLY_INFO'
title: ASSEMBLY_INFO (Estructura)
ms.date: 03/30/2017
api_name:
- ASSEMBLY_INFO
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASSEMBLY_INFO
helpviewer_keywords:
- ASSEMBLY_INFO structure [.NET Framework fusion]
ms.assetid: b3cbb47c-457f-4083-8895-49562ca99ab8
topic_type:
- apiref
ms.openlocfilehash: c28d9abf13769197b62705d51bbcf4f099616bbc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761293"
---
# <a name="assembly_info-structure"></a><span data-ttu-id="4dc35-103">ASSEMBLY_INFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="4dc35-103">ASSEMBLY_INFO Structure</span></span>

<span data-ttu-id="4dc35-104">Contiene información acerca de un ensamblado registrado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="4dc35-104">Contains information about an assembly that is registered in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dc35-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4dc35-105">Syntax</span></span>  
  
```cpp  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="4dc35-106">Members</span><span class="sxs-lookup"><span data-stu-id="4dc35-106">Members</span></span>  
  
|<span data-ttu-id="4dc35-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="4dc35-107">Member</span></span>|<span data-ttu-id="4dc35-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="4dc35-108">Description</span></span>|  
|------------|-----------------|  
|`cbAssemblyInfo`|<span data-ttu-id="4dc35-109">Tamaño de la estructura, en bytes.</span><span class="sxs-lookup"><span data-stu-id="4dc35-109">The size, in bytes, of the structure.</span></span> <span data-ttu-id="4dc35-110">Este campo está reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="4dc35-110">This field is reserved for future extensibility.</span></span>|  
|`dwAssemblyFlags`|<span data-ttu-id="4dc35-111">Marcas que indican los detalles de la instalación del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4dc35-111">Flags that indicate installation details about the assembly.</span></span> <span data-ttu-id="4dc35-112">Se admiten los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="4dc35-112">The following values are supported:</span></span><br /><br /> <span data-ttu-id="4dc35-113">-El valor de ASSEMBLYINFO_FLAG_INSTALLED, que indica que el ensamblado está instalado.</span><span class="sxs-lookup"><span data-stu-id="4dc35-113">-   The ASSEMBLYINFO_FLAG_INSTALLED value, which indicates that the assembly is installed.</span></span> <span data-ttu-id="4dc35-114">La versión actual de .NET Framework siempre establece `dwAssemblyFlags` en este valor.</span><span class="sxs-lookup"><span data-stu-id="4dc35-114">The current version of the .NET Framework always sets `dwAssemblyFlags` to this value.</span></span><br /><span data-ttu-id="4dc35-115">-El valor de ASSEMBLYINFO_FLAG_PAYLOADRESIDENT, que indica que el ensamblado es un residente de carga.</span><span class="sxs-lookup"><span data-stu-id="4dc35-115">-   The ASSEMBLYINFO_FLAG_PAYLOADRESIDENT value, which indicates that the assembly is a payload resident.</span></span> <span data-ttu-id="4dc35-116">La versión actual de la .NET Framework nunca establece `dwAssemblyFlags` en este valor.</span><span class="sxs-lookup"><span data-stu-id="4dc35-116">The current version of the .NET Framework never sets `dwAssemblyFlags` to this value.</span></span>|  
|`uliAssemblySizeInKB`|<span data-ttu-id="4dc35-117">Tamaño total, en kilobytes, de los archivos que contiene el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4dc35-117">The total size, in kilobytes, of the files that the assembly contains.</span></span>|  
|`pszCurrentAssemblyPathBuf`|<span data-ttu-id="4dc35-118">Un puntero a un búfer de cadena que contiene la ruta de acceso actual al archivo de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="4dc35-118">A pointer to a string buffer that holds the current path to the manifest file.</span></span> <span data-ttu-id="4dc35-119">La ruta de acceso debe terminar con un carácter nulo.</span><span class="sxs-lookup"><span data-stu-id="4dc35-119">The path must end with a null character.</span></span>|  
|`cchBuf`|<span data-ttu-id="4dc35-120">El número de caracteres anchos, incluido el terminador null, que `pszCurrentAssemblyPathBuf` contiene.</span><span class="sxs-lookup"><span data-stu-id="4dc35-120">The number of wide characters, including the null terminator, that `pszCurrentAssemblyPathBuf` contains.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4dc35-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4dc35-121">Requirements</span></span>  

 <span data-ttu-id="4dc35-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4dc35-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4dc35-123">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="4dc35-123">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="4dc35-124">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4dc35-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dc35-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="4dc35-125">See also</span></span>

- [<span data-ttu-id="4dc35-126">Estructuras de fusión</span><span class="sxs-lookup"><span data-stu-id="4dc35-126">Fusion Structures</span></span>](fusion-structures.md)
- [<span data-ttu-id="4dc35-127">Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="4dc35-127">Global Assembly Cache</span></span>](../../app-domains/gac.md)

---
title: OSINFO (Estructura)
ms.date: 03/30/2017
api_name:
- OSINFO
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- OSINFO
helpviewer_keywords:
- OSINFO structure [.NET Framework metadata]
ms.assetid: fac7b480-7adb-4450-a5e9-690fed81ffae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a36cd3c5fb638799a735e4b4a1a98959500300b5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761595"
---
# <a name="osinfo-structure"></a><span data-ttu-id="d7c64-102">OSINFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="d7c64-102">OSINFO Structure</span></span>
<span data-ttu-id="d7c64-103">Contiene detalles sobre el sistema operativo para un ensamblado o módulo.</span><span class="sxs-lookup"><span data-stu-id="d7c64-103">Contains details about the operating system for an assembly or module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7c64-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d7c64-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;   
    DWORD   dwOSMinorVersion;   
} OSINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="d7c64-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="d7c64-105">Members</span></span>  
  
|<span data-ttu-id="d7c64-106">Member</span><span class="sxs-lookup"><span data-stu-id="d7c64-106">Member</span></span>|<span data-ttu-id="d7c64-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d7c64-107">Description</span></span>|  
|------------|-----------------|  
|`dwOSPlatformId`|<span data-ttu-id="d7c64-108">Uno de los valores de identificador definidos por la función de la plataforma Microsoft Windows `GetVersionEx`.</span><span class="sxs-lookup"><span data-stu-id="d7c64-108">One of the identifier values defined by the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="d7c64-109">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="d7c64-109">The following values are supported:</span></span><br /><br /> <span data-ttu-id="d7c64-110">-VER_PLATFORM_WIN32s, o 0 x 0000, para especificar Microsoft Windows 3.1.</span><span class="sxs-lookup"><span data-stu-id="d7c64-110">-   VER_PLATFORM_WIN32s, or 0x0000, to specify Microsoft Windows 3.1.</span></span><br /><span data-ttu-id="d7c64-111">-VER_PLATFORM_WIN32_WINDOWS, o 0 x 0001, para especificar Windows 95, Windows 98 o sistemas operativos que se hereda de ellos.</span><span class="sxs-lookup"><span data-stu-id="d7c64-111">-   VER_PLATFORM_WIN32_WINDOWS, or 0x0001, to specify Windows 95, Windows 98, or operating systems descended from them.</span></span><br /><span data-ttu-id="d7c64-112">-VER_PLATFORM_WIN32_NT, o 0 x 0010, para especificar Windows NT o sistemas operativos que se hereda de él.</span><span class="sxs-lookup"><span data-stu-id="d7c64-112">-   VER_PLATFORM_WIN32_NT, or 0x0010, to specify Windows NT or operating systems descended from it.</span></span>|  
|`dwOSMajorVersion`|<span data-ttu-id="d7c64-113">La versión principal del sistema operativo o un valor NULL para indicar cualquier versión.</span><span class="sxs-lookup"><span data-stu-id="d7c64-113">The operating system major version, or a NULL value to indicate any version.</span></span>|  
|`dwOSMinorVersion`|<span data-ttu-id="d7c64-114">La versión secundaria del sistema operativo o un valor NULL para indicar cualquier versión.</span><span class="sxs-lookup"><span data-stu-id="d7c64-114">The operating system minor version, or a NULL value to indicate any version.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7c64-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d7c64-115">Remarks</span></span>  
 <span data-ttu-id="d7c64-116">`OSINFO` se basa en el `OSVERSIONINFOEX` estructura que es utilizado en las llamadas a la función de la plataforma Microsoft Windows `GetVersionEx`.</span><span class="sxs-lookup"><span data-stu-id="d7c64-116">`OSINFO` is based on the `OSVERSIONINFOEX` structure that is used in calls to the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="d7c64-117">Esta estructura se usa por ASSEMBLYMETADATA (estructura) para indicar su compatibilidad de sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="d7c64-117">This structure is used by the ASSEMBLYMETADATA structure to indicate its operating system support.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7c64-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d7c64-118">Requirements</span></span>  
 <span data-ttu-id="d7c64-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7c64-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7c64-120">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="d7c64-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d7c64-121">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d7c64-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d7c64-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7c64-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7c64-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7c64-123">See also</span></span>

- [<span data-ttu-id="d7c64-124">Estructuras de metadatos</span><span class="sxs-lookup"><span data-stu-id="d7c64-124">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="d7c64-125">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d7c64-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)

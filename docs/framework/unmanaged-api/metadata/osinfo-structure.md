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
ms.openlocfilehash: 048fe687e4d979576896f5310bddc855b40bb695
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175231"
---
# <a name="osinfo-structure"></a><span data-ttu-id="0d42c-102">OSINFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="0d42c-102">OSINFO Structure</span></span>
<span data-ttu-id="0d42c-103">Contiene detalles sobre el sistema operativo de un ensamblado o módulo.</span><span class="sxs-lookup"><span data-stu-id="0d42c-103">Contains details about the operating system for an assembly or module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d42c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0d42c-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;
    DWORD   dwOSMinorVersion;
} OSINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="0d42c-105">Members</span><span class="sxs-lookup"><span data-stu-id="0d42c-105">Members</span></span>  
  
|<span data-ttu-id="0d42c-106">Member</span><span class="sxs-lookup"><span data-stu-id="0d42c-106">Member</span></span>|<span data-ttu-id="0d42c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0d42c-107">Description</span></span>|  
|------------|-----------------|  
|`dwOSPlatformId`|<span data-ttu-id="0d42c-108">Uno de los valores de identificador `GetVersionEx`definidos por la función de plataforma Microsoft Windows .</span><span class="sxs-lookup"><span data-stu-id="0d42c-108">One of the identifier values defined by the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="0d42c-109">Se admiten los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="0d42c-109">The following values are supported:</span></span><br /><br /> <span data-ttu-id="0d42c-110">- VER_PLATFORM_WIN32s, o 0x0000, para especificar Microsoft Windows 3.1.</span><span class="sxs-lookup"><span data-stu-id="0d42c-110">-   VER_PLATFORM_WIN32s, or 0x0000, to specify Microsoft Windows 3.1.</span></span><br /><span data-ttu-id="0d42c-111">- VER_PLATFORM_WIN32_WINDOWS, o 0x0001, para especificar Windows 95, Windows 98 o sistemas operativos descendientes de ellos.</span><span class="sxs-lookup"><span data-stu-id="0d42c-111">-   VER_PLATFORM_WIN32_WINDOWS, or 0x0001, to specify Windows 95, Windows 98, or operating systems descended from them.</span></span><br /><span data-ttu-id="0d42c-112">- VER_PLATFORM_WIN32_NT, o 0x0002, para especificar Windows NT o sistemas operativos descendientes de él.</span><span class="sxs-lookup"><span data-stu-id="0d42c-112">-   VER_PLATFORM_WIN32_NT, or 0x0002, to specify Windows NT or operating systems descended from it.</span></span>|  
|`dwOSMajorVersion`|<span data-ttu-id="0d42c-113">La versión principal del sistema operativo o un valor NULL para indicar cualquier versión.</span><span class="sxs-lookup"><span data-stu-id="0d42c-113">The operating system major version, or a NULL value to indicate any version.</span></span>|  
|`dwOSMinorVersion`|<span data-ttu-id="0d42c-114">La versión secundaria del sistema operativo o un valor NULL para indicar cualquier versión.</span><span class="sxs-lookup"><span data-stu-id="0d42c-114">The operating system minor version, or a NULL value to indicate any version.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d42c-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0d42c-115">Remarks</span></span>  
 <span data-ttu-id="0d42c-116">`OSINFO`se basa `OSVERSIONINFOEX` en la estructura que se utiliza `GetVersionEx`en las llamadas a la función de plataforma Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="0d42c-116">`OSINFO` is based on the `OSVERSIONINFOEX` structure that is used in calls to the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="0d42c-117">Esta estructura es utilizada por la estructura ASSEMBLYMETADATA para indicar su compatibilidad con el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="0d42c-117">This structure is used by the ASSEMBLYMETADATA structure to indicate its operating system support.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d42c-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0d42c-118">Requirements</span></span>  
 <span data-ttu-id="0d42c-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d42c-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d42c-120">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0d42c-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0d42c-121">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0d42c-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0d42c-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d42c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d42c-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0d42c-123">See also</span></span>

- [<span data-ttu-id="0d42c-124">Estructuras de metadatos</span><span class="sxs-lookup"><span data-stu-id="0d42c-124">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="0d42c-125">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0d42c-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)

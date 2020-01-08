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
ms.openlocfilehash: d66e9bc3a027610d917e15dc9769b92ea1c5fb71
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345602"
---
# <a name="osinfo-structure"></a><span data-ttu-id="fa268-102">OSINFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="fa268-102">OSINFO Structure</span></span>
<span data-ttu-id="fa268-103">Contiene detalles sobre el sistema operativo de un ensamblado o un módulo.</span><span class="sxs-lookup"><span data-stu-id="fa268-103">Contains details about the operating system for an assembly or module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa268-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa268-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;   
    DWORD   dwOSMinorVersion;   
} OSINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="fa268-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="fa268-105">Members</span></span>  
  
|<span data-ttu-id="fa268-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="fa268-106">Member</span></span>|<span data-ttu-id="fa268-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa268-107">Description</span></span>|  
|------------|-----------------|  
|`dwOSPlatformId`|<span data-ttu-id="fa268-108">Uno de los valores de identificador definidos por la función de la plataforma Microsoft Windows `GetVersionEx`.</span><span class="sxs-lookup"><span data-stu-id="fa268-108">One of the identifier values defined by the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="fa268-109">Se admiten los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="fa268-109">The following values are supported:</span></span><br /><br /> <span data-ttu-id="fa268-110">-VER_PLATFORM_WIN32s, o 0x0000, para especificar Microsoft Windows 3,1.</span><span class="sxs-lookup"><span data-stu-id="fa268-110">-   VER_PLATFORM_WIN32s, or 0x0000, to specify Microsoft Windows 3.1.</span></span><br /><span data-ttu-id="fa268-111">-VER_PLATFORM_WIN32_WINDOWS, o 0x0001, para especificar los sistemas operativos Windows 95, Windows 98 o que descienden de ellos.</span><span class="sxs-lookup"><span data-stu-id="fa268-111">-   VER_PLATFORM_WIN32_WINDOWS, or 0x0001, to specify Windows 95, Windows 98, or operating systems descended from them.</span></span><br /><span data-ttu-id="fa268-112">-VER_PLATFORM_WIN32_NT, o 0x0002, para especificar los sistemas operativos Windows NT o que descienden de él.</span><span class="sxs-lookup"><span data-stu-id="fa268-112">-   VER_PLATFORM_WIN32_NT, or 0x0002, to specify Windows NT or operating systems descended from it.</span></span>|  
|`dwOSMajorVersion`|<span data-ttu-id="fa268-113">La versión principal del sistema operativo o un valor NULL para indicar cualquier versión.</span><span class="sxs-lookup"><span data-stu-id="fa268-113">The operating system major version, or a NULL value to indicate any version.</span></span>|  
|`dwOSMinorVersion`|<span data-ttu-id="fa268-114">La versión secundaria del sistema operativo o un valor NULL para indicar cualquier versión.</span><span class="sxs-lookup"><span data-stu-id="fa268-114">The operating system minor version, or a NULL value to indicate any version.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa268-115">Notas</span><span class="sxs-lookup"><span data-stu-id="fa268-115">Remarks</span></span>  
 <span data-ttu-id="fa268-116">`OSINFO` se basa en la estructura de `OSVERSIONINFOEX` que se utiliza en las llamadas a la función de la plataforma Microsoft Windows `GetVersionEx`.</span><span class="sxs-lookup"><span data-stu-id="fa268-116">`OSINFO` is based on the `OSVERSIONINFOEX` structure that is used in calls to the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="fa268-117">La estructura ASSEMBLYMETADATA (usa esta estructura para indicar su compatibilidad con el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="fa268-117">This structure is used by the ASSEMBLYMETADATA structure to indicate its operating system support.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa268-118">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="fa268-118">Requirements</span></span>  
 <span data-ttu-id="fa268-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa268-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa268-120">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fa268-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fa268-121">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fa268-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fa268-122">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa268-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa268-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa268-123">See also</span></span>

- [<span data-ttu-id="fa268-124">Estructuras de metadatos</span><span class="sxs-lookup"><span data-stu-id="fa268-124">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="fa268-125">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fa268-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)

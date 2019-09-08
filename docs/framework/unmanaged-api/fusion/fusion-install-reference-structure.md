---
title: FUSION_INSTALL_REFERENCE (Estructura)
ms.date: 03/30/2017
api_name:
- FUSION_INSTALL_REFERENCE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- FUSION_INSTALL_REFERENCE
helpviewer_keywords:
- FUSION_INSTALL_REFERENCE structure [.NET Framework fusion]
ms.assetid: ae181ec8-36bf-4ed1-9a02-ca27d417c80b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e81fb7c99b9fd03a69456a84f2191770f40121d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795347"
---
# <a name="fusion_install_reference-structure"></a><span data-ttu-id="41d48-102">FUSION_INSTALL_REFERENCE (Estructura)</span><span class="sxs-lookup"><span data-stu-id="41d48-102">FUSION_INSTALL_REFERENCE Structure</span></span>
<span data-ttu-id="41d48-103">Representa una referencia que una aplicación realiza a un ensamblado que la aplicación ha instalado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="41d48-103">Represents a reference that an application makes to an assembly that the application has installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41d48-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="41d48-104">Syntax</span></span>  
  
```cpp  
typedef struct _FUSION_INSTALL_REFERENCE_ {  
    DWORD    cbSize,  
    DWORD    dwFlags,  
    GUID     guidScheme,  
    LPCWSTR  szIdentifier,  
    LPCWSTR  szNonCanonicalData  
} FUSION_INSTALL_REFERENCE, *LPFUSION_INSTALL_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="41d48-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="41d48-105">Members</span></span>  
  
|<span data-ttu-id="41d48-106">Member</span><span class="sxs-lookup"><span data-stu-id="41d48-106">Member</span></span>|<span data-ttu-id="41d48-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="41d48-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="41d48-108">Tamaño de la estructura en bytes.</span><span class="sxs-lookup"><span data-stu-id="41d48-108">The size of the structure in bytes.</span></span>|  
|`dwFlags`|<span data-ttu-id="41d48-109">Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="41d48-109">Reserved for future extensibility.</span></span> <span data-ttu-id="41d48-110">Este valor debe ser 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="41d48-110">This value must be 0 (zero).</span></span>|  
|`guidScheme`|<span data-ttu-id="41d48-111">Entidad que agrega la referencia.</span><span class="sxs-lookup"><span data-stu-id="41d48-111">The entity that adds the reference.</span></span> <span data-ttu-id="41d48-112">Este campo puede tener uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="41d48-112">This field can have one of the following values:</span></span><br /><br /> <span data-ttu-id="41d48-113">- FUSION_REFCOUNT_MSI_GUID: Una aplicación que se instaló mediante el Microsoft Windows Installer hace referencia al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="41d48-113">-   FUSION_REFCOUNT_MSI_GUID: The assembly is referenced by an application that was installed using the Microsoft Windows Installer.</span></span> <span data-ttu-id="41d48-114">El `szIdentifier` campo se establece en `MSI`y el `szNonCanonicalData` campo se establece en `Windows Installer`.</span><span class="sxs-lookup"><span data-stu-id="41d48-114">The `szIdentifier` field is set to `MSI`, and the `szNonCanonicalData` field is set to `Windows Installer`.</span></span> <span data-ttu-id="41d48-115">Este esquema se utiliza para los ensamblados en paralelo de Windows.</span><span class="sxs-lookup"><span data-stu-id="41d48-115">This scheme is used for Windows side-by-side assemblies.</span></span><br /><span data-ttu-id="41d48-116">-   FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: Una aplicación que aparece en la interfaz **Agregar o quitar programas** hace referencia al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="41d48-116">-   FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: The assembly is referenced by an application that appears in the **Add/Remove Programs** interface.</span></span> <span data-ttu-id="41d48-117">El `szIdentifier` campo proporciona el token que registra la aplicación con la interfaz **Agregar o quitar programas** .</span><span class="sxs-lookup"><span data-stu-id="41d48-117">The `szIdentifier` field provides the token that registers the application with the **Add/Remove Programs** interface.</span></span><br /><span data-ttu-id="41d48-118">- FUSION_REFCOUNT_FILEPATH_GUID: Una aplicación que representa un archivo en el sistema de archivos hace referencia al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="41d48-118">-   FUSION_REFCOUNT_FILEPATH_GUID: The assembly is referenced by an application that is represented by a file in the file system.</span></span> <span data-ttu-id="41d48-119">El `szIdentifier` campo proporciona la ruta de acceso a este archivo.</span><span class="sxs-lookup"><span data-stu-id="41d48-119">The `szIdentifier` field provides the path to this file.</span></span><br /><span data-ttu-id="41d48-120">- FUSION_REFCOUNT_OPAQUE_STRING_GUID: Una aplicación que representa solo una cadena opaca hace referencia al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="41d48-120">-   FUSION_REFCOUNT_OPAQUE_STRING_GUID: The assembly is referenced by an application that is represented only by an opaque string.</span></span> <span data-ttu-id="41d48-121">El `szIdentifier` campo proporciona esta cadena opaca.</span><span class="sxs-lookup"><span data-stu-id="41d48-121">The `szIdentifier` field provides this opaque string.</span></span> <span data-ttu-id="41d48-122">La caché global de ensamblados no comprueba la existencia de referencias opacas al quitar este valor.</span><span class="sxs-lookup"><span data-stu-id="41d48-122">The global assembly cache does not check for the existence of opaque references when you remove this value.</span></span><br /><span data-ttu-id="41d48-123">- FUSION_REFCOUNT_OSINSTALL_GUID: Este valor está reservado.</span><span class="sxs-lookup"><span data-stu-id="41d48-123">-   FUSION_REFCOUNT_OSINSTALL_GUID: This value is reserved.</span></span>|  
|`szIdentifier`|<span data-ttu-id="41d48-124">Cadena única que identifica la aplicación que ha instalado el ensamblado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="41d48-124">A unique string that identifies the application that installed the assembly in the global assembly cache.</span></span> <span data-ttu-id="41d48-125">Su valor depende del valor del `guidScheme` campo.</span><span class="sxs-lookup"><span data-stu-id="41d48-125">Its value depends upon the value of the `guidScheme` field.</span></span>|  
|`szNonCanonicalData`|<span data-ttu-id="41d48-126">Cadena que solo entiende la entidad que agrega la referencia.</span><span class="sxs-lookup"><span data-stu-id="41d48-126">A string that is understood only by the entity that adds the reference.</span></span> <span data-ttu-id="41d48-127">La caché global de ensamblados almacena esta cadena, pero no la utiliza.</span><span class="sxs-lookup"><span data-stu-id="41d48-127">The global assembly cache stores this string, but does not use it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="41d48-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="41d48-128">Requirements</span></span>  
 <span data-ttu-id="41d48-129">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41d48-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41d48-130">**Encabezado**: Fusion. h</span><span class="sxs-lookup"><span data-stu-id="41d48-130">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="41d48-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41d48-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41d48-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="41d48-132">See also</span></span>

- [<span data-ttu-id="41d48-133">Estructuras de fusión</span><span class="sxs-lookup"><span data-stu-id="41d48-133">Fusion Structures</span></span>](fusion-structures.md)
- [<span data-ttu-id="41d48-134">Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="41d48-134">Global Assembly Cache</span></span>](../../app-domains/gac.md)

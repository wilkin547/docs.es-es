---
title: FUSION_INSTALL_REFERENCE (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FUSION_INSTALL_REFERENCE
api_location: fusion.dll
api_type: COM
f1_keywords: FUSION_INSTALL_REFERENCE
helpviewer_keywords: FUSION_INSTALL_REFERENCE structure [.NET Framework fusion]
ms.assetid: ae181ec8-36bf-4ed1-9a02-ca27d417c80b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 36321606fe208233fb6114fe9568b655f0e1b400
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="fusioninstallreference-structure"></a><span data-ttu-id="02c93-102">FUSION_INSTALL_REFERENCE (Estructura)</span><span class="sxs-lookup"><span data-stu-id="02c93-102">FUSION_INSTALL_REFERENCE Structure</span></span>
<span data-ttu-id="02c93-103">Representa una referencia que hace que una aplicación a un ensamblado que se ha instalado la aplicación en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="02c93-103">Represents a reference that an application makes to an assembly that the application has installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02c93-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02c93-104">Syntax</span></span>  
  
```  
typedef struct _FUSION_INSTALL_REFERENCE_ {  
    DWORD    cbSize,  
    DWORD    dwFlags,  
    GUID     guidScheme,  
    LPCWSTR  szIdentifier,  
    LPCWSTR  szNonCanonicalData  
} FUSION_INSTALL_REFERENCE, *LPFUSION_INSTALL_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="02c93-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="02c93-105">Members</span></span>  
  
|<span data-ttu-id="02c93-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="02c93-106">Member</span></span>|<span data-ttu-id="02c93-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="02c93-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="02c93-108">El tamaño de la estructura, en bytes.</span><span class="sxs-lookup"><span data-stu-id="02c93-108">The size of the structure in bytes.</span></span>|  
|`dwFlags`|<span data-ttu-id="02c93-109">Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="02c93-109">Reserved for future extensibility.</span></span> <span data-ttu-id="02c93-110">Este valor debe ser 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="02c93-110">This value must be 0 (zero).</span></span>|  
|`guidScheme`|<span data-ttu-id="02c93-111">La entidad que agrega la referencia.</span><span class="sxs-lookup"><span data-stu-id="02c93-111">The entity that adds the reference.</span></span> <span data-ttu-id="02c93-112">Este campo puede tener uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="02c93-112">This field can have one of the following values:</span></span><br /><br /> <span data-ttu-id="02c93-113">-FUSION_REFCOUNT_MSI_GUID: Una aplicación que se instala con Microsoft Windows Installer hace referencia al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="02c93-113">-   FUSION_REFCOUNT_MSI_GUID: The assembly is referenced by an application that was installed using the Microsoft Windows Installer.</span></span> <span data-ttu-id="02c93-114">El `szIdentifier` campo está establecido en `MSI`y el `szNonCanonicalData` campo está establecido en `Windows Installer`.</span><span class="sxs-lookup"><span data-stu-id="02c93-114">The `szIdentifier` field is set to `MSI`, and the `szNonCanonicalData` field is set to `Windows Installer`.</span></span> <span data-ttu-id="02c93-115">Este esquema se utiliza para los ensamblados en paralelo de Windows.</span><span class="sxs-lookup"><span data-stu-id="02c93-115">This scheme is used for Windows side-by-side assemblies.</span></span><br /><span data-ttu-id="02c93-116">-FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: El ensamblado hace referencia una aplicación que aparece en el **agregar o quitar programas** interfaz.</span><span class="sxs-lookup"><span data-stu-id="02c93-116">-   FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: The assembly is referenced by an application that appears in the **Add/Remove Programs** interface.</span></span> <span data-ttu-id="02c93-117">El `szIdentifier` campo proporciona el símbolo (token) que registra la aplicación con el **agregar o quitar programas** interfaz.</span><span class="sxs-lookup"><span data-stu-id="02c93-117">The `szIdentifier` field provides the token that registers the application with the **Add/Remove Programs** interface.</span></span><br /><span data-ttu-id="02c93-118">-FUSION_REFCOUNT_FILEPATH_GUID: Una aplicación que se representa mediante un archivo en el sistema de archivos hace referencia al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="02c93-118">-   FUSION_REFCOUNT_FILEPATH_GUID: The assembly is referenced by an application that is represented by a file in the file system.</span></span> <span data-ttu-id="02c93-119">El `szIdentifier` campo proporciona la ruta de acceso a este archivo.</span><span class="sxs-lookup"><span data-stu-id="02c93-119">The `szIdentifier` field provides the path to this file.</span></span><br /><span data-ttu-id="02c93-120">-FUSION_REFCOUNT_OPAQUE_STRING_GUID: Una aplicación que se representa sólo mediante una cadena opaca hace referencia al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="02c93-120">-   FUSION_REFCOUNT_OPAQUE_STRING_GUID: The assembly is referenced by an application that is represented only by an opaque string.</span></span> <span data-ttu-id="02c93-121">El `szIdentifier` campo proporciona esta cadena opaca.</span><span class="sxs-lookup"><span data-stu-id="02c93-121">The `szIdentifier` field provides this opaque string.</span></span> <span data-ttu-id="02c93-122">La caché global de ensamblados no comprueba la existencia de referencias opacas cuando se quita este valor.</span><span class="sxs-lookup"><span data-stu-id="02c93-122">The global assembly cache does not check for the existence of opaque references when you remove this value.</span></span><br /><span data-ttu-id="02c93-123">-FUSION_REFCOUNT_OSINSTALL_GUID: Este valor está reservado.</span><span class="sxs-lookup"><span data-stu-id="02c93-123">-   FUSION_REFCOUNT_OSINSTALL_GUID: This value is reserved.</span></span>|  
|`szIdentifier`|<span data-ttu-id="02c93-124">Una cadena única que identifica la aplicación que instala al ensamblado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="02c93-124">A unique string that identifies the application that installed the assembly in the global assembly cache.</span></span> <span data-ttu-id="02c93-125">Su valor depende del valor de la `guidScheme` campo.</span><span class="sxs-lookup"><span data-stu-id="02c93-125">Its value depends upon the value of the `guidScheme` field.</span></span>|  
|`szNonCanonicalData`|<span data-ttu-id="02c93-126">Una cadena que sólo es reconocida por la entidad que agrega la referencia.</span><span class="sxs-lookup"><span data-stu-id="02c93-126">A string that is understood only by the entity that adds the reference.</span></span> <span data-ttu-id="02c93-127">La caché global de ensamblados almacena esta cadena, pero no la usa.</span><span class="sxs-lookup"><span data-stu-id="02c93-127">The global assembly cache stores this string, but does not use it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="02c93-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="02c93-128">Requirements</span></span>  
 <span data-ttu-id="02c93-129">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02c93-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02c93-130">**Encabezado:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="02c93-130">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="02c93-131">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02c93-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02c93-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="02c93-132">See Also</span></span>  
 [<span data-ttu-id="02c93-133">Estructuras de fusión</span><span class="sxs-lookup"><span data-stu-id="02c93-133">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
 [<span data-ttu-id="02c93-134">Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="02c93-134">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)

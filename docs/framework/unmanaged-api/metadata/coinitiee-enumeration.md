---
title: "COINITIEE (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COINITIEE
api_location: mscoree.dll
api_type: COM
f1_keywords: COINITIEE
helpviewer_keywords: COINITIEE enumeration [.NET Framework metadata]
ms.assetid: 64264238-3b68-4bac-a887-36b552426a6c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 03711186954aa24beff65e5d4d5b5e484c6dc276
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="coinitiee-enumeration"></a><span data-ttu-id="466f4-102">COINITIEE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="466f4-102">COINITIEE Enumeration</span></span>
<span data-ttu-id="466f4-103">Especifica las constantes utilizadas por [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) al inicializar common language runtime.</span><span class="sxs-lookup"><span data-stu-id="466f4-103">Specifies constants used by [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="466f4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="466f4-104">Syntax</span></span>  
  
```  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="466f4-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="466f4-105">Members</span></span>  
  
|<span data-ttu-id="466f4-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="466f4-106">Member</span></span>|<span data-ttu-id="466f4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="466f4-107">Description</span></span>|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|<span data-ttu-id="466f4-108">Modo de inicialización predeterminado.</span><span class="sxs-lookup"><span data-stu-id="466f4-108">Default initialization mode.</span></span> <span data-ttu-id="466f4-109">Esto inicializa el tiempo de ejecución y crea el valor predeterminado <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="466f4-109">This initializes the runtime and creates the default <xref:System.AppDomain>.</span></span>|  
|`COINITEE_DLL`|<span data-ttu-id="466f4-110">Se inicializa para ejecutar un archivo DLL administrado.</span><span class="sxs-lookup"><span data-stu-id="466f4-110">Initializes to run a managed DLL.</span></span>|  
|`COINITEE_MAIN`|<span data-ttu-id="466f4-111">Se inicializa para ejecutar un archivo ejecutable administrado.</span><span class="sxs-lookup"><span data-stu-id="466f4-111">Initializes to run a managed EXE.</span></span> <span data-ttu-id="466f4-112">Esto inicializa el tiempo de ejecución pero no crea el valor predeterminado <xref:System.AppDomain>, que se crea después de escribir la rutina principal del archivo EXE.</span><span class="sxs-lookup"><span data-stu-id="466f4-112">This initializes the runtime but does not create the default <xref:System.AppDomain>, which is created after entering the main routine of the EXE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="466f4-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="466f4-113">Requirements</span></span>  
 <span data-ttu-id="466f4-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="466f4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="466f4-115">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="466f4-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="466f4-116">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="466f4-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="466f4-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="466f4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="466f4-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="466f4-118">See Also</span></span>  
 [<span data-ttu-id="466f4-119">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="466f4-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

---
description: 'Más información sobre: enumeración COINITIEE ('
title: COINITIEE (Enumeración)
ms.date: 03/30/2017
api_name:
- COINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COINITIEE
helpviewer_keywords:
- COINITIEE enumeration [.NET Framework metadata]
ms.assetid: 64264238-3b68-4bac-a887-36b552426a6c
topic_type:
- apiref
ms.openlocfilehash: c17980582903a29cdfe33c64200c31f29ddeb17c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678619"
---
# <a name="coinitiee-enumeration"></a><span data-ttu-id="865be-103">COINITIEE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="865be-103">COINITIEE Enumeration</span></span>

<span data-ttu-id="865be-104">Especifica las constantes utilizadas por el [Coinicializador](../hosting/coinitializeee-function.md) al inicializar el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="865be-104">Specifies constants used by [CoInitializeEE](../hosting/coinitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="865be-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="865be-105">Syntax</span></span>  
  
```cpp  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="865be-106">Members</span><span class="sxs-lookup"><span data-stu-id="865be-106">Members</span></span>  
  
|<span data-ttu-id="865be-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="865be-107">Member</span></span>|<span data-ttu-id="865be-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="865be-108">Description</span></span>|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|<span data-ttu-id="865be-109">Modo de inicialización predeterminado.</span><span class="sxs-lookup"><span data-stu-id="865be-109">Default initialization mode.</span></span> <span data-ttu-id="865be-110">Esto inicializa el tiempo de ejecución y crea el valor predeterminado <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="865be-110">This initializes the runtime and creates the default <xref:System.AppDomain>.</span></span>|  
|`COINITEE_DLL`|<span data-ttu-id="865be-111">Inicializa para ejecutar un archivo DLL administrado.</span><span class="sxs-lookup"><span data-stu-id="865be-111">Initializes to run a managed DLL.</span></span>|  
|`COINITEE_MAIN`|<span data-ttu-id="865be-112">Inicializa para ejecutar un ejecutable administrado.</span><span class="sxs-lookup"><span data-stu-id="865be-112">Initializes to run a managed EXE.</span></span> <span data-ttu-id="865be-113">Esto inicializa el tiempo de ejecución, pero no crea el valor predeterminado <xref:System.AppDomain> , que se crea después de escribir la rutina principal del archivo exe.</span><span class="sxs-lookup"><span data-stu-id="865be-113">This initializes the runtime but does not create the default <xref:System.AppDomain>, which is created after entering the main routine of the EXE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="865be-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="865be-114">Requirements</span></span>  

 <span data-ttu-id="865be-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="865be-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="865be-116">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="865be-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="865be-117">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="865be-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="865be-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="865be-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="865be-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="865be-119">See also</span></span>

- [<span data-ttu-id="865be-120">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="865be-120">Metadata Enumerations</span></span>](metadata-enumerations.md)

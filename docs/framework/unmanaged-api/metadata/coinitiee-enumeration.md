---
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
ms.openlocfilehash: f4d1c2f105abb64bf196d0dd8371c2788c97336e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005913"
---
# <a name="coinitiee-enumeration"></a><span data-ttu-id="cc612-102">COINITIEE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="cc612-102">COINITIEE Enumeration</span></span>
<span data-ttu-id="cc612-103">Especifica las constantes utilizadas por el [Coinicializador](../hosting/coinitializeee-function.md) al inicializar el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="cc612-103">Specifies constants used by [CoInitializeEE](../hosting/coinitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc612-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cc612-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="cc612-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="cc612-105">Members</span></span>  
  
|<span data-ttu-id="cc612-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="cc612-106">Member</span></span>|<span data-ttu-id="cc612-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc612-107">Description</span></span>|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|<span data-ttu-id="cc612-108">Modo de inicialización predeterminado.</span><span class="sxs-lookup"><span data-stu-id="cc612-108">Default initialization mode.</span></span> <span data-ttu-id="cc612-109">Esto inicializa el tiempo de ejecución y crea el valor predeterminado <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="cc612-109">This initializes the runtime and creates the default <xref:System.AppDomain>.</span></span>|  
|`COINITEE_DLL`|<span data-ttu-id="cc612-110">Inicializa para ejecutar un archivo DLL administrado.</span><span class="sxs-lookup"><span data-stu-id="cc612-110">Initializes to run a managed DLL.</span></span>|  
|`COINITEE_MAIN`|<span data-ttu-id="cc612-111">Inicializa para ejecutar un ejecutable administrado.</span><span class="sxs-lookup"><span data-stu-id="cc612-111">Initializes to run a managed EXE.</span></span> <span data-ttu-id="cc612-112">Esto inicializa el tiempo de ejecución, pero no crea el valor predeterminado <xref:System.AppDomain> , que se crea después de escribir la rutina principal del archivo exe.</span><span class="sxs-lookup"><span data-stu-id="cc612-112">This initializes the runtime but does not create the default <xref:System.AppDomain>, which is created after entering the main routine of the EXE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cc612-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cc612-113">Requirements</span></span>  
 <span data-ttu-id="cc612-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc612-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc612-115">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cc612-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cc612-116">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cc612-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cc612-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc612-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc612-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cc612-118">See also</span></span>

- [<span data-ttu-id="cc612-119">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="cc612-119">Metadata Enumerations</span></span>](metadata-enumerations.md)

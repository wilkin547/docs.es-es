---
title: CVStruct (estructura)
ms.date: 03/30/2017
api_name:
- CVStruct
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CVStruct
helpviewer_keywords:
- CVStruct structure [.NET Framework metadata]
ms.assetid: e9e4e497-d5fb-464b-991c-3bdd824664fd
topic_type:
- apiref
ms.openlocfilehash: 19ee3097dfe80ba9dcbdaf316db0fd165b50abc6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436429"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="5c344-102">CVStruct (estructura)</span><span class="sxs-lookup"><span data-stu-id="5c344-102">CVStruct Structure</span></span>
<span data-ttu-id="5c344-103">Contiene información que se utiliza al instalar un módulo o una imagen compuesta.</span><span class="sxs-lookup"><span data-stu-id="5c344-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c344-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5c344-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="5c344-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="5c344-105">Members</span></span>  
  
|<span data-ttu-id="5c344-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="5c344-106">Member</span></span>|<span data-ttu-id="5c344-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c344-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="5c344-108">Principal</span><span class="sxs-lookup"><span data-stu-id="5c344-108">Major</span></span>|<span data-ttu-id="5c344-109">Número de compilación de la versión principal.</span><span class="sxs-lookup"><span data-stu-id="5c344-109">Major version build number.</span></span>|  
|<span data-ttu-id="5c344-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="5c344-110">Minor</span></span>|<span data-ttu-id="5c344-111">Número de compilación de la versión secundaria.</span><span class="sxs-lookup"><span data-stu-id="5c344-111">Minor version build number.</span></span>|  
|<span data-ttu-id="5c344-112">Sub</span><span class="sxs-lookup"><span data-stu-id="5c344-112">Sub</span></span>|<span data-ttu-id="5c344-113">Número de subcompilación.</span><span class="sxs-lookup"><span data-stu-id="5c344-113">Sub-build number.</span></span>|  
|<span data-ttu-id="5c344-114">Compilar</span><span class="sxs-lookup"><span data-stu-id="5c344-114">Build</span></span>|<span data-ttu-id="5c344-115">Número de compilación.</span><span class="sxs-lookup"><span data-stu-id="5c344-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5c344-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5c344-116">Requirements</span></span>  
 <span data-ttu-id="5c344-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c344-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c344-118">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5c344-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5c344-119">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5c344-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5c344-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c344-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c344-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c344-121">See also</span></span>

- [<span data-ttu-id="5c344-122">Estructuras de metadatos</span><span class="sxs-lookup"><span data-stu-id="5c344-122">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)

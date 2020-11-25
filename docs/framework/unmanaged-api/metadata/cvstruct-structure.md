---
title: CVStruct (Estructura)
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
ms.openlocfilehash: db36b94fafe20b58b9bcbb886b8d285326960f67
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715581"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="cfda5-102">CVStruct (Estructura)</span><span class="sxs-lookup"><span data-stu-id="cfda5-102">CVStruct Structure</span></span>

<span data-ttu-id="cfda5-103">Contiene información que se utiliza al instalar un módulo o una imagen compuesta.</span><span class="sxs-lookup"><span data-stu-id="cfda5-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfda5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cfda5-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="cfda5-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="cfda5-105">Members</span></span>  
  
|<span data-ttu-id="cfda5-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="cfda5-106">Member</span></span>|<span data-ttu-id="cfda5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="cfda5-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="cfda5-108">Major</span><span class="sxs-lookup"><span data-stu-id="cfda5-108">Major</span></span>|<span data-ttu-id="cfda5-109">Número de compilación de la versión principal.</span><span class="sxs-lookup"><span data-stu-id="cfda5-109">Major version build number.</span></span>|  
|<span data-ttu-id="cfda5-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="cfda5-110">Minor</span></span>|<span data-ttu-id="cfda5-111">Número de compilación de la versión secundaria.</span><span class="sxs-lookup"><span data-stu-id="cfda5-111">Minor version build number.</span></span>|  
|<span data-ttu-id="cfda5-112">Sub</span><span class="sxs-lookup"><span data-stu-id="cfda5-112">Sub</span></span>|<span data-ttu-id="cfda5-113">Número de subcompilación.</span><span class="sxs-lookup"><span data-stu-id="cfda5-113">Sub-build number.</span></span>|  
|<span data-ttu-id="cfda5-114">Compilar</span><span class="sxs-lookup"><span data-stu-id="cfda5-114">Build</span></span>|<span data-ttu-id="cfda5-115">Número de compilación.</span><span class="sxs-lookup"><span data-stu-id="cfda5-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cfda5-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cfda5-116">Requirements</span></span>  

 <span data-ttu-id="cfda5-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cfda5-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfda5-118">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cfda5-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cfda5-119">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cfda5-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cfda5-120">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfda5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfda5-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cfda5-121">See also</span></span>

- [<span data-ttu-id="cfda5-122">Estructuras de metadatos</span><span class="sxs-lookup"><span data-stu-id="cfda5-122">Metadata Structures</span></span>](metadata-structures.md)

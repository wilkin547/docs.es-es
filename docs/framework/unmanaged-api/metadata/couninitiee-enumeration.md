---
title: COUNINITIEE (Enumeración)
ms.date: 03/30/2017
api_name:
- COUNINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COUNINITIEE
helpviewer_keywords:
- COUNINITIEE enumeration [.NET Framework metadata]
ms.assetid: c42baa79-f469-4330-95a2-baf7f021c2fc
topic_type:
- apiref
ms.openlocfilehash: b0f8c7e6d2acf4d4c080cc147bf6d42bf13cb51b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723836"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="38169-102">COUNINITIEE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="38169-102">COUNINITIEE Enumeration</span></span>

<span data-ttu-id="38169-103">Especifica las constantes utilizadas por [CoUninitializeEE (](../hosting/couninitializeee-function.md) al inicializar el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="38169-103">Specifies constants used by [CoUninitializeEE](../hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38169-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="38169-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="38169-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="38169-105">Members</span></span>  
  
|<span data-ttu-id="38169-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="38169-106">Member</span></span>|<span data-ttu-id="38169-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="38169-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="38169-108">Indica el modo de no inicialización predeterminado.</span><span class="sxs-lookup"><span data-stu-id="38169-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="38169-109">Indica el modo de anulación de la carga de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="38169-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="38169-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="38169-110">Requirements</span></span>  

 <span data-ttu-id="38169-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38169-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38169-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="38169-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="38169-113">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="38169-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="38169-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38169-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38169-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="38169-115">See also</span></span>

- [<span data-ttu-id="38169-116">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="38169-116">Metadata Enumerations</span></span>](metadata-enumerations.md)

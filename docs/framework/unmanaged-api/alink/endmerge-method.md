---
description: 'Más información sobre: método Endmerge ('
title: EndMerge (Método)
ms.date: 03/30/2017
api_name:
- IALink.EndMerge
- EndMerge
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EndMerge
helpviewer_keywords:
- EndMerge method
ms.assetid: 1d03bb15-a2c8-4a04-8fc6-b126c89c3778
topic_type:
- apiref
ms.openlocfilehash: aac23d6d87f3fe74c1094bdd4a7f9c9f7f3fa7cc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638163"
---
# <a name="endmerge-method"></a><span data-ttu-id="3937b-103">EndMerge (Método)</span><span class="sxs-lookup"><span data-stu-id="3937b-103">EndMerge Method</span></span>

<span data-ttu-id="3937b-104">Indica que todos los atributos personalizados se han combinado en el ámbito de emisión.</span><span class="sxs-lookup"><span data-stu-id="3937b-104">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3937b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3937b-105">Syntax</span></span>  
  
```cpp  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3937b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3937b-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="3937b-107">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3937b-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3937b-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3937b-108">Return Value</span></span>  

 <span data-ttu-id="3937b-109">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="3937b-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3937b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3937b-110">Requirements</span></span>  

 <span data-ttu-id="3937b-111">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="3937b-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3937b-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3937b-112">See also</span></span>

- [<span data-ttu-id="3937b-113">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3937b-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="3937b-114">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3937b-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="3937b-115">API de ALink</span><span class="sxs-lookup"><span data-stu-id="3937b-115">ALink API</span></span>](index.md)

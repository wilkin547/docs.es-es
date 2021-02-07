---
description: 'Más información sobre: método GetResolutionScope ('
title: GetResolutionScope (Método)
ms.date: 03/30/2017
api_name:
- IALink.GetResolutionScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetResolutionScope
helpviewer_keywords:
- GetResolutionScope method
ms.assetid: 5b48ca60-dacd-44b2-9979-4a5122f00812
topic_type:
- apiref
ms.openlocfilehash: add8ccb1ef6eb0f4b688dcf80563e9280099120d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718400"
---
# <a name="getresolutionscope-method"></a><span data-ttu-id="3f936-103">GetResolutionScope (Método)</span><span class="sxs-lookup"><span data-stu-id="3f936-103">GetResolutionScope Method</span></span>

<span data-ttu-id="3f936-104">Recupera el ámbito de un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="3f936-104">Retrieves the scope of a given type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f936-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3f936-105">Syntax</span></span>  
  
```cpp  
HRESULT GetResolutionScope(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    mdToken     TargetFile,  
    mdToken*    pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f936-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3f936-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="3f936-107">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3f936-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="3f936-108">Archivo que necesita una referencia.</span><span class="sxs-lookup"><span data-stu-id="3f936-108">File that is in need of a reference.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="3f936-109">Token de archivo en el que se define el tipo, normalmente recuperado con el [método importFile](importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="3f936-109">Token of file that type is defined in, usually retrieved with [ImportFile Method](importfile-method.md).</span></span>  
  
 `pScope`  
 <span data-ttu-id="3f936-110">Recibe la referencia del ensamblado o módulo.</span><span class="sxs-lookup"><span data-stu-id="3f936-110">Receives the assembly or module reference.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3f936-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3f936-111">Return Value</span></span>  

 <span data-ttu-id="3f936-112">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="3f936-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f936-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3f936-113">Requirements</span></span>  

 <span data-ttu-id="3f936-114">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="3f936-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f936-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f936-115">See also</span></span>

- [<span data-ttu-id="3f936-116">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3f936-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="3f936-117">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3f936-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="3f936-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="3f936-118">ALink API</span></span>](index.md)

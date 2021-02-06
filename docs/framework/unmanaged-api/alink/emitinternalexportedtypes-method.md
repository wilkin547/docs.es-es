---
description: 'Más información sobre: método Emitinternalexportedtypes ('
title: EmitInternalExportedTypes (Método)
ms.date: 03/30/2017
api_name:
- EmitInternalExportedTypes
- IALink2.EmitInternalExportedTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitInternalExportedTypes
helpviewer_keywords:
- EmitInternalExportedTypes method
ms.assetid: 28c8b00d-2c14-40b4-aed5-a1db0e2428eb
topic_type:
- apiref
ms.openlocfilehash: 5d23c593988b31c077d3b65b11b73113e164ed74
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638306"
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="d79bd-103">EmitInternalExportedTypes (Método)</span><span class="sxs-lookup"><span data-stu-id="d79bd-103">EmitInternalExportedTypes Method</span></span>

<span data-ttu-id="d79bd-104">Emite tipos agregados al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d79bd-104">Emits types added to the assembly.</span></span> <span data-ttu-id="d79bd-105">Llame a este método después de que se hayan agregado los tipos internos conocidos.</span><span class="sxs-lookup"><span data-stu-id="d79bd-105">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d79bd-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d79bd-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="d79bd-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d79bd-107">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="d79bd-108">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d79bd-108">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d79bd-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d79bd-109">Return Value</span></span>  

 <span data-ttu-id="d79bd-110">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="d79bd-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d79bd-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d79bd-111">Requirements</span></span>  

 <span data-ttu-id="d79bd-112">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="d79bd-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d79bd-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d79bd-113">See also</span></span>

- [<span data-ttu-id="d79bd-114">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d79bd-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="d79bd-115">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d79bd-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="d79bd-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="d79bd-116">ALink API</span></span>](index.md)

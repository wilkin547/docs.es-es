---
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
ms.openlocfilehash: faf1438f56cd49b235ffbb18a0154e3e20c202b9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684972"
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="8adeb-102">EmitInternalExportedTypes (Método)</span><span class="sxs-lookup"><span data-stu-id="8adeb-102">EmitInternalExportedTypes Method</span></span>

<span data-ttu-id="8adeb-103">Emite tipos agregados al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8adeb-103">Emits types added to the assembly.</span></span> <span data-ttu-id="8adeb-104">Llame a este método después de que se hayan agregado los tipos internos conocidos.</span><span class="sxs-lookup"><span data-stu-id="8adeb-104">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8adeb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8adeb-105">Syntax</span></span>  
  
```cpp  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="8adeb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8adeb-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="8adeb-107">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8adeb-107">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8adeb-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8adeb-108">Return Value</span></span>  

 <span data-ttu-id="8adeb-109">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="8adeb-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8adeb-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8adeb-110">Requirements</span></span>  

 <span data-ttu-id="8adeb-111">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="8adeb-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8adeb-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8adeb-112">See also</span></span>

- [<span data-ttu-id="8adeb-113">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8adeb-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="8adeb-114">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8adeb-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="8adeb-115">API de ALink</span><span class="sxs-lookup"><span data-stu-id="8adeb-115">ALink API</span></span>](index.md)

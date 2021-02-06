---
description: 'Más información sobre: método Emitmanifest ('
title: EmitManifest (Método)
ms.date: 03/30/2017
api_name:
- EmitManifest
- IALink.EmitManifest
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitManifest
helpviewer_keywords:
- EmitManifest method
ms.assetid: fdebc1f3-b62e-4d9e-b775-8ccaa8ecb250
topic_type:
- apiref
ms.openlocfilehash: 770631864c030c067feb0b02d2f00c36076aa44c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638280"
---
# <a name="emitmanifest-method"></a><span data-ttu-id="b434e-103">EmitManifest (Método)</span><span class="sxs-lookup"><span data-stu-id="b434e-103">EmitManifest Method</span></span>

<span data-ttu-id="b434e-104">Emite el manifiesto final.</span><span class="sxs-lookup"><span data-stu-id="b434e-104">Emits the final manifest.</span></span> <span data-ttu-id="b434e-105">Llame a este método después de importar todos los demás archivos y establecer todas las opciones.</span><span class="sxs-lookup"><span data-stu-id="b434e-105">Call this method after importing all other files and setting all options.</span></span> <span data-ttu-id="b434e-106">No llame a este método para módulos sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="b434e-106">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b434e-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b434e-107">Syntax</span></span>  
  
```cpp  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b434e-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b434e-108">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="b434e-109">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b434e-109">ID of the assembly.</span></span>  
  
 `pdwReserveSize`  
 <span data-ttu-id="b434e-110">Recibe el tamaño que se va a reservar en el archivo de ensamblado, recuperado de la [función strongnamesignaturesize (](../strong-naming/strongnamesignaturesize-function.md).</span><span class="sxs-lookup"><span data-stu-id="b434e-110">Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../strong-naming/strongnamesignaturesize-function.md).</span></span>  
  
 `ptkManifest`  
 <span data-ttu-id="b434e-111">Opcionalmente, recibe el token del manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b434e-111">Optionally receives the assembly manifest token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b434e-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b434e-112">Return Value</span></span>  

 <span data-ttu-id="b434e-113">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="b434e-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b434e-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b434e-114">Requirements</span></span>  

 <span data-ttu-id="b434e-115">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="b434e-115">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b434e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b434e-116">See also</span></span>

- [<span data-ttu-id="b434e-117">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b434e-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="b434e-118">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b434e-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="b434e-119">API de ALink</span><span class="sxs-lookup"><span data-stu-id="b434e-119">ALink API</span></span>](index.md)

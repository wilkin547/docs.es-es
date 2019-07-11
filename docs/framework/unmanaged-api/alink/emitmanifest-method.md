---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 91dc4cb7d64d49d1e95c0c8eb79a29736559d842
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742087"
---
# <a name="emitmanifest-method"></a><span data-ttu-id="7bdb2-102">EmitManifest (Método)</span><span class="sxs-lookup"><span data-stu-id="7bdb2-102">EmitManifest Method</span></span>
<span data-ttu-id="7bdb2-103">Emite el manifiesto final.</span><span class="sxs-lookup"><span data-stu-id="7bdb2-103">Emits the final manifest.</span></span> <span data-ttu-id="7bdb2-104">Llame a este método después de importar todos los demás archivos y establecer todas las opciones.</span><span class="sxs-lookup"><span data-stu-id="7bdb2-104">Call this method after importing all other files and setting all options.</span></span> <span data-ttu-id="7bdb2-105">No llame a este método para módulos no enlazados.</span><span class="sxs-lookup"><span data-stu-id="7bdb2-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bdb2-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7bdb2-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="7bdb2-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7bdb2-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="7bdb2-108">Id. del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7bdb2-108">ID of the assembly.</span></span>  
  
 `pdwReserveSize`  
 <span data-ttu-id="7bdb2-109">Recibe el tamaño que se reserva en el archivo de ensamblado, recuperarse [StrongNameSignatureSize (función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md).</span><span class="sxs-lookup"><span data-stu-id="7bdb2-109">Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md).</span></span>  
  
 `ptkManifest`  
 <span data-ttu-id="7bdb2-110">Opcionalmente, recibe el token del manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7bdb2-110">Optionally receives the assembly manifest token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7bdb2-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7bdb2-111">Return Value</span></span>  
 <span data-ttu-id="7bdb2-112">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="7bdb2-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bdb2-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7bdb2-113">Requirements</span></span>  
 <span data-ttu-id="7bdb2-114">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="7bdb2-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bdb2-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="7bdb2-115">See also</span></span>

- [<span data-ttu-id="7bdb2-116">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7bdb2-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="7bdb2-117">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7bdb2-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="7bdb2-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="7bdb2-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

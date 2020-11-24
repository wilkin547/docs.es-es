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
ms.openlocfilehash: b1c005e58f18b03a7da5f3836f719b95c41bca95
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684946"
---
# <a name="emitmanifest-method"></a><span data-ttu-id="cf075-102">EmitManifest (Método)</span><span class="sxs-lookup"><span data-stu-id="cf075-102">EmitManifest Method</span></span>

<span data-ttu-id="cf075-103">Emite el manifiesto final.</span><span class="sxs-lookup"><span data-stu-id="cf075-103">Emits the final manifest.</span></span> <span data-ttu-id="cf075-104">Llame a este método después de importar todos los demás archivos y establecer todas las opciones.</span><span class="sxs-lookup"><span data-stu-id="cf075-104">Call this method after importing all other files and setting all options.</span></span> <span data-ttu-id="cf075-105">No llame a este método para módulos sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="cf075-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf075-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf075-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf075-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cf075-107">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="cf075-108">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="cf075-108">ID of the assembly.</span></span>  
  
 `pdwReserveSize`  
 <span data-ttu-id="cf075-109">Recibe el tamaño que se va a reservar en el archivo de ensamblado, recuperado de la [función strongnamesignaturesize (](../strong-naming/strongnamesignaturesize-function.md).</span><span class="sxs-lookup"><span data-stu-id="cf075-109">Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../strong-naming/strongnamesignaturesize-function.md).</span></span>  
  
 `ptkManifest`  
 <span data-ttu-id="cf075-110">Opcionalmente, recibe el token del manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="cf075-110">Optionally receives the assembly manifest token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cf075-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cf075-111">Return Value</span></span>  

 <span data-ttu-id="cf075-112">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="cf075-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf075-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cf075-113">Requirements</span></span>  

 <span data-ttu-id="cf075-114">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="cf075-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf075-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cf075-115">See also</span></span>

- [<span data-ttu-id="cf075-116">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cf075-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="cf075-117">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cf075-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="cf075-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="cf075-118">ALink API</span></span>](index.md)

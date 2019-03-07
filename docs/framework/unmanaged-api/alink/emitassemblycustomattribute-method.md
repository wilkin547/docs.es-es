---
title: EmitAssemblyCustomAttribute (Método)
ms.date: 03/30/2017
api_name:
- IALink.EmitAssemblyCustomAttribute
- EmitAssemblyCustomAttribute
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssemblyCustomAttribute
helpviewer_keywords:
- EmitAssemblyCustomAttribute method
ms.assetid: b72f5409-79af-4fa7-90a7-7630eec170f1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 69914bce7ed322d90cfbd03dd611e2b745dfe066
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470053"
---
# <a name="emitassemblycustomattribute-method"></a><span data-ttu-id="85002-102">EmitAssemblyCustomAttribute (Método)</span><span class="sxs-lookup"><span data-stu-id="85002-102">EmitAssemblyCustomAttribute Method</span></span>
<span data-ttu-id="85002-103">Llamada para establecer los atributos personalizados de nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="85002-103">Call to set assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85002-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85002-104">Syntax</span></span>  
  
```  
HRESULT EmitAssemblyCustomAttribute(  
    mdAssembly   AssemblyID,  
    mdToken      FileToken,  
    mdToken      tkType,  
    void const*  pCustomValue,  
    DWORD        cbCustomValue,  
    BOOL         bSecurity,  
    BOOL         bAllowMulti  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="85002-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="85002-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="85002-106">Id. del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="85002-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="85002-107">Archivo que define el atributo.</span><span class="sxs-lookup"><span data-stu-id="85002-107">File that defiles the attribute.</span></span> <span data-ttu-id="85002-108">Puede ser NULL si `AssemblyID` no indica un netmodule independiente.</span><span class="sxs-lookup"><span data-stu-id="85002-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `tkType`  
 <span data-ttu-id="85002-109">Tipo del atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="85002-109">Type of the custom attribute.</span></span>  
  
 `pCustomValue`  
 <span data-ttu-id="85002-110">Datos del valor personalizado.</span><span class="sxs-lookup"><span data-stu-id="85002-110">Custom value data.</span></span>  
  
 `cbCustomValue`  
 <span data-ttu-id="85002-111">Longitud de datos de valor personalizado.</span><span class="sxs-lookup"><span data-stu-id="85002-111">Length of custom value data.</span></span>  
  
 `bSecurity`  
 <span data-ttu-id="85002-112">TRUE si el atributo personalizado está relacionado con la firma de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="85002-112">TRUE if the custom attribute is related to assembly signing.</span></span>  
  
 `bAllowMulti`  
 <span data-ttu-id="85002-113">TRUE si deben emitirse varios atributos.</span><span class="sxs-lookup"><span data-stu-id="85002-113">TRUE if multiple attributes are to be emitted.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="85002-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="85002-114">Return Value</span></span>  
 <span data-ttu-id="85002-115">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="85002-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85002-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="85002-116">Requirements</span></span>  
 <span data-ttu-id="85002-117">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="85002-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85002-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="85002-118">See also</span></span>
- [<span data-ttu-id="85002-119">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="85002-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="85002-120">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="85002-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="85002-121">API de ALink</span><span class="sxs-lookup"><span data-stu-id="85002-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

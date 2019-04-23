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
ms.openlocfilehash: 67073f04cfe981dd383369029d9a4b436929a0a6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59117850"
---
# <a name="emitassemblycustomattribute-method"></a><span data-ttu-id="5f9e7-102">EmitAssemblyCustomAttribute (Método)</span><span class="sxs-lookup"><span data-stu-id="5f9e7-102">EmitAssemblyCustomAttribute Method</span></span>
<span data-ttu-id="5f9e7-103">Llamada para establecer los atributos personalizados de nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5f9e7-103">Call to set assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f9e7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f9e7-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="5f9e7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5f9e7-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="5f9e7-106">Id. del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5f9e7-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="5f9e7-107">Archivo que define el atributo.</span><span class="sxs-lookup"><span data-stu-id="5f9e7-107">File that defiles the attribute.</span></span> <span data-ttu-id="5f9e7-108">Puede ser NULL si `AssemblyID` no indica un netmodule independiente.</span><span class="sxs-lookup"><span data-stu-id="5f9e7-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `tkType`  
 <span data-ttu-id="5f9e7-109">Tipo del atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="5f9e7-109">Type of the custom attribute.</span></span>  
  
 `pCustomValue`  
 <span data-ttu-id="5f9e7-110">Datos del valor personalizado.</span><span class="sxs-lookup"><span data-stu-id="5f9e7-110">Custom value data.</span></span>  
  
 `cbCustomValue`  
 <span data-ttu-id="5f9e7-111">Longitud de datos de valor personalizado.</span><span class="sxs-lookup"><span data-stu-id="5f9e7-111">Length of custom value data.</span></span>  
  
 `bSecurity`  
 <span data-ttu-id="5f9e7-112">TRUE si el atributo personalizado está relacionado con la firma de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="5f9e7-112">TRUE if the custom attribute is related to assembly signing.</span></span>  
  
 `bAllowMulti`  
 <span data-ttu-id="5f9e7-113">TRUE si deben emitirse varios atributos.</span><span class="sxs-lookup"><span data-stu-id="5f9e7-113">TRUE if multiple attributes are to be emitted.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f9e7-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5f9e7-114">Return Value</span></span>  
 <span data-ttu-id="5f9e7-115">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="5f9e7-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f9e7-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5f9e7-116">Requirements</span></span>  
 <span data-ttu-id="5f9e7-117">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="5f9e7-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f9e7-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f9e7-118">See also</span></span>

- [<span data-ttu-id="5f9e7-119">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5f9e7-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="5f9e7-120">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5f9e7-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="5f9e7-121">API de ALink</span><span class="sxs-lookup"><span data-stu-id="5f9e7-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

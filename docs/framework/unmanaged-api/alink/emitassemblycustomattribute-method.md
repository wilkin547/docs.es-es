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
ms.openlocfilehash: ec0a86e3396ad42152bc0a244f74ad13deba16e4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446509"
---
# <a name="emitassemblycustomattribute-method"></a><span data-ttu-id="ddbc5-102">EmitAssemblyCustomAttribute (Método)</span><span class="sxs-lookup"><span data-stu-id="ddbc5-102">EmitAssemblyCustomAttribute Method</span></span>
<span data-ttu-id="ddbc5-103">Llame a para establecer los atributos personalizados de nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ddbc5-103">Call to set assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddbc5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ddbc5-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="ddbc5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ddbc5-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ddbc5-106">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ddbc5-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="ddbc5-107">Archivo que Desarchiva el atributo.</span><span class="sxs-lookup"><span data-stu-id="ddbc5-107">File that defiles the attribute.</span></span> <span data-ttu-id="ddbc5-108">Puede ser NULL si `AssemblyID` no indica un valor de netmodule sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="ddbc5-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `tkType`  
 <span data-ttu-id="ddbc5-109">Tipo del atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="ddbc5-109">Type of the custom attribute.</span></span>  
  
 `pCustomValue`  
 <span data-ttu-id="ddbc5-110">Datos de valores personalizados.</span><span class="sxs-lookup"><span data-stu-id="ddbc5-110">Custom value data.</span></span>  
  
 `cbCustomValue`  
 <span data-ttu-id="ddbc5-111">Longitud de los datos de valor personalizados.</span><span class="sxs-lookup"><span data-stu-id="ddbc5-111">Length of custom value data.</span></span>  
  
 `bSecurity`  
 <span data-ttu-id="ddbc5-112">TRUE si el atributo personalizado está relacionado con la firma de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="ddbc5-112">TRUE if the custom attribute is related to assembly signing.</span></span>  
  
 `bAllowMulti`  
 <span data-ttu-id="ddbc5-113">TRUE si se van a emitir varios atributos.</span><span class="sxs-lookup"><span data-stu-id="ddbc5-113">TRUE if multiple attributes are to be emitted.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ddbc5-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ddbc5-114">Return Value</span></span>  
 <span data-ttu-id="ddbc5-115">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="ddbc5-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddbc5-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ddbc5-116">Requirements</span></span>  
 <span data-ttu-id="ddbc5-117">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="ddbc5-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddbc5-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ddbc5-118">See also</span></span>

- [<span data-ttu-id="ddbc5-119">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ddbc5-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="ddbc5-120">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ddbc5-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="ddbc5-121">API de ALink</span><span class="sxs-lookup"><span data-stu-id="ddbc5-121">ALink API</span></span>](index.md)

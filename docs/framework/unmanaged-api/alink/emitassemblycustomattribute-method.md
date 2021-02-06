---
description: 'Más información sobre: método Emitassemblycustomattribute ('
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
ms.openlocfilehash: c91eb563c14b442a22db8f328287c10e5cc9a63c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638332"
---
# <a name="emitassemblycustomattribute-method"></a><span data-ttu-id="9653b-103">EmitAssemblyCustomAttribute (Método)</span><span class="sxs-lookup"><span data-stu-id="9653b-103">EmitAssemblyCustomAttribute Method</span></span>

<span data-ttu-id="9653b-104">Llame a para establecer los atributos personalizados de nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9653b-104">Call to set assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9653b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9653b-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="9653b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9653b-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="9653b-107">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9653b-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="9653b-108">Archivo que Desarchiva el atributo.</span><span class="sxs-lookup"><span data-stu-id="9653b-108">File that defiles the attribute.</span></span> <span data-ttu-id="9653b-109">Puede ser NULL si `AssemblyID` no indica un valor de netmodule sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="9653b-109">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `tkType`  
 <span data-ttu-id="9653b-110">Tipo del atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="9653b-110">Type of the custom attribute.</span></span>  
  
 `pCustomValue`  
 <span data-ttu-id="9653b-111">Datos de valores personalizados.</span><span class="sxs-lookup"><span data-stu-id="9653b-111">Custom value data.</span></span>  
  
 `cbCustomValue`  
 <span data-ttu-id="9653b-112">Longitud de los datos de valor personalizados.</span><span class="sxs-lookup"><span data-stu-id="9653b-112">Length of custom value data.</span></span>  
  
 `bSecurity`  
 <span data-ttu-id="9653b-113">TRUE si el atributo personalizado está relacionado con la firma de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="9653b-113">TRUE if the custom attribute is related to assembly signing.</span></span>  
  
 `bAllowMulti`  
 <span data-ttu-id="9653b-114">TRUE si se van a emitir varios atributos.</span><span class="sxs-lookup"><span data-stu-id="9653b-114">TRUE if multiple attributes are to be emitted.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9653b-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9653b-115">Return Value</span></span>  

 <span data-ttu-id="9653b-116">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="9653b-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9653b-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9653b-117">Requirements</span></span>  

 <span data-ttu-id="9653b-118">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="9653b-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9653b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="9653b-119">See also</span></span>

- [<span data-ttu-id="9653b-120">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9653b-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="9653b-121">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9653b-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="9653b-122">API de ALink</span><span class="sxs-lookup"><span data-stu-id="9653b-122">ALink API</span></span>](index.md)

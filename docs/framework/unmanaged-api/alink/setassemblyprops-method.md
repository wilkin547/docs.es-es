---
title: SetAssemblyProps (Método)
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyProps
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method
ms.assetid: a3d7cf29-1414-49e6-8aae-9b3283c4f5f0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dc9ca5d9533a6c4a297155a47ac0061f1232d242
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481119"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="34f35-102">SetAssemblyProps (Método)</span><span class="sxs-lookup"><span data-stu-id="34f35-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="34f35-103">Asigna las propiedades de nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="34f35-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34f35-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="34f35-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="34f35-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="34f35-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="34f35-106">Id. del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="34f35-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="34f35-107">Archivo que define la propiedad.</span><span class="sxs-lookup"><span data-stu-id="34f35-107">File that defines the property.</span></span> <span data-ttu-id="34f35-108">Puede ser NULL si `AssemblyID` no indica un netmodule independiente.</span><span class="sxs-lookup"><span data-stu-id="34f35-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="34f35-109">Indica la opción de modificar.</span><span class="sxs-lookup"><span data-stu-id="34f35-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="34f35-110">Nuevo valor de la opción.</span><span class="sxs-lookup"><span data-stu-id="34f35-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="34f35-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="34f35-111">Return Value</span></span>  
 <span data-ttu-id="34f35-112">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="34f35-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34f35-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="34f35-113">Requirements</span></span>  
 <span data-ttu-id="34f35-114">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="34f35-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34f35-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="34f35-115">See also</span></span>
- [<span data-ttu-id="34f35-116">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="34f35-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="34f35-117">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="34f35-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="34f35-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="34f35-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

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
ms.openlocfilehash: aed553a3a8d54b5229a122e76b61e3e58d4af3c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401971"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="1fbd9-102">SetAssemblyProps (Método)</span><span class="sxs-lookup"><span data-stu-id="1fbd9-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="1fbd9-103">Asigna propiedades de nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1fbd9-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fbd9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1fbd9-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1fbd9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1fbd9-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="1fbd9-106">Identificador del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1fbd9-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="1fbd9-107">Archivo que define la propiedad.</span><span class="sxs-lookup"><span data-stu-id="1fbd9-107">File that defines the property.</span></span> <span data-ttu-id="1fbd9-108">Puede ser NULL si `AssemblyID` no indica un archivo netmodule no enlazado.</span><span class="sxs-lookup"><span data-stu-id="1fbd9-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="1fbd9-109">Indica que la opción para modificar.</span><span class="sxs-lookup"><span data-stu-id="1fbd9-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="1fbd9-110">Nuevo valor de la opción.</span><span class="sxs-lookup"><span data-stu-id="1fbd9-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1fbd9-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1fbd9-111">Return Value</span></span>  
 <span data-ttu-id="1fbd9-112">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="1fbd9-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fbd9-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1fbd9-113">Requirements</span></span>  
 <span data-ttu-id="1fbd9-114">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="1fbd9-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fbd9-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="1fbd9-115">See Also</span></span>  
 [<span data-ttu-id="1fbd9-116">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1fbd9-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="1fbd9-117">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1fbd9-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="1fbd9-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="1fbd9-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

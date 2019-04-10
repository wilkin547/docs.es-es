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
ms.openlocfilehash: 589bd7b2132693c89dc10ae1a5c8d0bf52ed481e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218997"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="911bb-102">SetAssemblyProps (Método)</span><span class="sxs-lookup"><span data-stu-id="911bb-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="911bb-103">Asigna las propiedades de nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="911bb-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="911bb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="911bb-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="911bb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="911bb-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="911bb-106">Id. del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="911bb-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="911bb-107">Archivo que define la propiedad.</span><span class="sxs-lookup"><span data-stu-id="911bb-107">File that defines the property.</span></span> <span data-ttu-id="911bb-108">Puede ser NULL si `AssemblyID` no indica un netmodule independiente.</span><span class="sxs-lookup"><span data-stu-id="911bb-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="911bb-109">Indica la opción de modificar.</span><span class="sxs-lookup"><span data-stu-id="911bb-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="911bb-110">Nuevo valor de la opción.</span><span class="sxs-lookup"><span data-stu-id="911bb-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="911bb-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="911bb-111">Return Value</span></span>  
 <span data-ttu-id="911bb-112">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="911bb-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="911bb-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="911bb-113">Requirements</span></span>  
 <span data-ttu-id="911bb-114">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="911bb-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="911bb-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="911bb-115">See also</span></span>

- [<span data-ttu-id="911bb-116">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="911bb-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="911bb-117">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="911bb-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="911bb-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="911bb-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

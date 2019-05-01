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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949089"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="ce363-102">SetAssemblyProps (Método)</span><span class="sxs-lookup"><span data-stu-id="ce363-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="ce363-103">Asigna las propiedades de nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ce363-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce363-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ce363-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce363-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ce363-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ce363-106">Id. del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ce363-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="ce363-107">Archivo que define la propiedad.</span><span class="sxs-lookup"><span data-stu-id="ce363-107">File that defines the property.</span></span> <span data-ttu-id="ce363-108">Puede ser NULL si `AssemblyID` no indica un netmodule independiente.</span><span class="sxs-lookup"><span data-stu-id="ce363-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="ce363-109">Indica la opción de modificar.</span><span class="sxs-lookup"><span data-stu-id="ce363-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="ce363-110">Nuevo valor de la opción.</span><span class="sxs-lookup"><span data-stu-id="ce363-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ce363-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ce363-111">Return Value</span></span>  
 <span data-ttu-id="ce363-112">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="ce363-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce363-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ce363-113">Requirements</span></span>  
 <span data-ttu-id="ce363-114">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="ce363-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce363-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce363-115">See also</span></span>

- [<span data-ttu-id="ce363-116">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ce363-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="ce363-117">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ce363-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="ce363-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="ce363-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

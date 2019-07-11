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
ms.openlocfilehash: 1e9f51799ea56cb1e5819d708a0e4a8136a94f3d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741483"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="46783-102">SetAssemblyProps (Método)</span><span class="sxs-lookup"><span data-stu-id="46783-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="46783-103">Asigna las propiedades de nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="46783-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46783-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="46783-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="46783-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="46783-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="46783-106">Id. del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="46783-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="46783-107">Archivo que define la propiedad.</span><span class="sxs-lookup"><span data-stu-id="46783-107">File that defines the property.</span></span> <span data-ttu-id="46783-108">Puede ser NULL si `AssemblyID` no indica un netmodule independiente.</span><span class="sxs-lookup"><span data-stu-id="46783-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="46783-109">Indica la opción de modificar.</span><span class="sxs-lookup"><span data-stu-id="46783-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="46783-110">Nuevo valor de la opción.</span><span class="sxs-lookup"><span data-stu-id="46783-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46783-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="46783-111">Return Value</span></span>  
 <span data-ttu-id="46783-112">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="46783-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46783-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="46783-113">Requirements</span></span>  
 <span data-ttu-id="46783-114">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="46783-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46783-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="46783-115">See also</span></span>

- [<span data-ttu-id="46783-116">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="46783-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="46783-117">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="46783-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="46783-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="46783-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

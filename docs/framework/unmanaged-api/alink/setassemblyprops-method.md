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
ms.openlocfilehash: 4bfad8b985a8ef059031464e99a8004842b276c0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445571"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="bbe75-102">SetAssemblyProps (Método)</span><span class="sxs-lookup"><span data-stu-id="bbe75-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="bbe75-103">Asigna propiedades de nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bbe75-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbe75-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bbe75-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="bbe75-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bbe75-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="bbe75-106">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bbe75-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="bbe75-107">Archivo que define la propiedad.</span><span class="sxs-lookup"><span data-stu-id="bbe75-107">File that defines the property.</span></span> <span data-ttu-id="bbe75-108">Puede ser NULL si `AssemblyID` no indica un valor de netmodule sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="bbe75-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="bbe75-109">Indica la opción que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="bbe75-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="bbe75-110">Nuevo valor de la opción.</span><span class="sxs-lookup"><span data-stu-id="bbe75-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bbe75-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bbe75-111">Return Value</span></span>  
 <span data-ttu-id="bbe75-112">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="bbe75-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbe75-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bbe75-113">Requirements</span></span>  
 <span data-ttu-id="bbe75-114">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="bbe75-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbe75-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="bbe75-115">See also</span></span>

- [<span data-ttu-id="bbe75-116">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bbe75-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="bbe75-117">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bbe75-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="bbe75-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="bbe75-118">ALink API</span></span>](index.md)

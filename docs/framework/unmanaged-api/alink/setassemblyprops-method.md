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
ms.openlocfilehash: 4b0de5f9759491f1303edc978b1548e91214daf8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733755"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="7c758-102">SetAssemblyProps (Método)</span><span class="sxs-lookup"><span data-stu-id="7c758-102">SetAssemblyProps Method</span></span>

<span data-ttu-id="7c758-103">Asigna propiedades de nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7c758-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c758-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7c758-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c758-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7c758-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="7c758-106">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7c758-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="7c758-107">Archivo que define la propiedad.</span><span class="sxs-lookup"><span data-stu-id="7c758-107">File that defines the property.</span></span> <span data-ttu-id="7c758-108">Puede ser NULL si `AssemblyID` no indica un valor de netmodule sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="7c758-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="7c758-109">Indica la opción que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="7c758-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="7c758-110">Nuevo valor de la opción.</span><span class="sxs-lookup"><span data-stu-id="7c758-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c758-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7c758-111">Return Value</span></span>  

 <span data-ttu-id="7c758-112">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="7c758-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c758-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7c758-113">Requirements</span></span>  

 <span data-ttu-id="7c758-114">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="7c758-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c758-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7c758-115">See also</span></span>

- [<span data-ttu-id="7c758-116">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7c758-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="7c758-117">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7c758-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="7c758-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="7c758-118">ALink API</span></span>](index.md)

---
description: 'Más información sobre: método SetAssemblyProps ('
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
ms.openlocfilehash: 212d8aad22ac1cb231db46f20ff65de2339a21aa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662356"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="130d7-103">SetAssemblyProps (Método)</span><span class="sxs-lookup"><span data-stu-id="130d7-103">SetAssemblyProps Method</span></span>

<span data-ttu-id="130d7-104">Asigna propiedades de nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="130d7-104">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="130d7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="130d7-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="130d7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="130d7-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="130d7-107">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="130d7-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="130d7-108">Archivo que define la propiedad.</span><span class="sxs-lookup"><span data-stu-id="130d7-108">File that defines the property.</span></span> <span data-ttu-id="130d7-109">Puede ser NULL si `AssemblyID` no indica un valor de netmodule sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="130d7-109">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="130d7-110">Indica la opción que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="130d7-110">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="130d7-111">Nuevo valor de la opción.</span><span class="sxs-lookup"><span data-stu-id="130d7-111">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="130d7-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="130d7-112">Return Value</span></span>  

 <span data-ttu-id="130d7-113">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="130d7-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="130d7-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="130d7-114">Requirements</span></span>  

 <span data-ttu-id="130d7-115">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="130d7-115">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="130d7-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="130d7-116">See also</span></span>

- [<span data-ttu-id="130d7-117">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="130d7-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="130d7-118">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="130d7-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="130d7-119">API de ALink</span><span class="sxs-lookup"><span data-stu-id="130d7-119">ALink API</span></span>](index.md)

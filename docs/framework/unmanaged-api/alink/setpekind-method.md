---
description: 'Más información sobre: método SetPEKind ('
title: SetPEKind (Método)
ms.date: 03/30/2017
api_name:
- IALink2.SetPEKind
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetPEKind
helpviewer_keywords:
- SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type:
- apiref
ms.openlocfilehash: 4154e9e80b7f88b6951c9aa8da5fc23d340c96dc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662304"
---
# <a name="setpekind-method"></a><span data-ttu-id="123d4-103">SetPEKind (Método)</span><span class="sxs-lookup"><span data-stu-id="123d4-103">SetPEKind Method</span></span>

<span data-ttu-id="123d4-104">Determina el tipo portable ejecutable, ya sea específico del equipo o independiente del equipo.</span><span class="sxs-lookup"><span data-stu-id="123d4-104">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="123d4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="123d4-105">Syntax</span></span>  
  
```cpp  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;
```  
  
## <a name="parameters"></a><span data-ttu-id="123d4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="123d4-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="123d4-107">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="123d4-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="123d4-108">Token del archivo para el que se va a establecer el tipo de PE.</span><span class="sxs-lookup"><span data-stu-id="123d4-108">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="123d4-109">Puede ser NULL si `AssemblyID` no indica un valor de netmodule sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="123d4-109">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="123d4-110">Tipo de PE, como indica la [enumeración CorPEKind (](../metadata/corpekind-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="123d4-110">The type of PE, as indicated by the [CorPEKind Enumeration](../metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="123d4-111">La arquitectura del equipo de destino, como se indica en el encabezado NT.</span><span class="sxs-lookup"><span data-stu-id="123d4-111">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="123d4-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="123d4-112">Return Value</span></span>  

 <span data-ttu-id="123d4-113">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="123d4-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="123d4-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="123d4-114">Requirements</span></span>  

 <span data-ttu-id="123d4-115">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="123d4-115">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="123d4-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="123d4-116">See also</span></span>

- [<span data-ttu-id="123d4-117">Método GetPEKind</span><span class="sxs-lookup"><span data-stu-id="123d4-117">GetPEKind Method</span></span>](../metadata/imetadataimport2-getpekind-method.md)
- [<span data-ttu-id="123d4-118">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="123d4-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="123d4-119">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="123d4-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="123d4-120">API de ALink</span><span class="sxs-lookup"><span data-stu-id="123d4-120">ALink API</span></span>](index.md)

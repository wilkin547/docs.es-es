---
description: 'Más información sobre: método Getfiledef ('
title: GetFileDef (Método)
ms.date: 03/30/2017
api_name:
- IALink2.GetFileDef
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetFileDef
helpviewer_keywords:
- GetFileDef method
ms.assetid: 4e3fbe6c-b82a-4181-ab17-7faa1263f5b3
topic_type:
- apiref
ms.openlocfilehash: 5d44336e686ca565f468fb95ce5290ee41d5e16e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718452"
---
# <a name="getfiledef-method"></a><span data-ttu-id="c0411-103">GetFileDef (Método)</span><span class="sxs-lookup"><span data-stu-id="c0411-103">GetFileDef Method</span></span>

<span data-ttu-id="c0411-104">Recupera el token de FileDef real que se usa en los metadatos (en contraposición al token asignado por ALink).</span><span class="sxs-lookup"><span data-stu-id="c0411-104">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0411-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c0411-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0411-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c0411-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="c0411-107">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c0411-107">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="c0411-108">Token del archivo agregado tal y como se recuperó del método AddFile o del método addImport (.</span><span class="sxs-lookup"><span data-stu-id="c0411-108">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="c0411-109">Recibe el token FileDef.</span><span class="sxs-lookup"><span data-stu-id="c0411-109">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c0411-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c0411-110">Return Value</span></span>  

 <span data-ttu-id="c0411-111">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="c0411-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0411-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c0411-112">Requirements</span></span>  

 <span data-ttu-id="c0411-113">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="c0411-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0411-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0411-114">See also</span></span>

- [<span data-ttu-id="c0411-115">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c0411-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="c0411-116">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c0411-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="c0411-117">API de ALink</span><span class="sxs-lookup"><span data-stu-id="c0411-117">ALink API</span></span>](index.md)

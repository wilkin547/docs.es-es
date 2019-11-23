---
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
ms.openlocfilehash: 6a561205602920123176bd421ca2ef1b601166c1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426052"
---
# <a name="getfiledef-method"></a><span data-ttu-id="11812-102">GetFileDef (Método)</span><span class="sxs-lookup"><span data-stu-id="11812-102">GetFileDef Method</span></span>
<span data-ttu-id="11812-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span><span class="sxs-lookup"><span data-stu-id="11812-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11812-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11812-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="11812-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="11812-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="11812-106">ID of the assembly.</span><span class="sxs-lookup"><span data-stu-id="11812-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="11812-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span><span class="sxs-lookup"><span data-stu-id="11812-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="11812-108">Receives the FileDef token.</span><span class="sxs-lookup"><span data-stu-id="11812-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11812-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="11812-109">Return Value</span></span>  
 <span data-ttu-id="11812-110">Returns S_OK if the method succeeds.</span><span class="sxs-lookup"><span data-stu-id="11812-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11812-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="11812-111">Requirements</span></span>  
 <span data-ttu-id="11812-112">Requires alink.h</span><span class="sxs-lookup"><span data-stu-id="11812-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11812-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="11812-113">See also</span></span>

- [<span data-ttu-id="11812-114">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11812-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="11812-115">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11812-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="11812-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="11812-116">ALink API</span></span>](index.md)

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
# <a name="getfiledef-method"></a><span data-ttu-id="f5429-102">GetFileDef (Método)</span><span class="sxs-lookup"><span data-stu-id="f5429-102">GetFileDef Method</span></span>
<span data-ttu-id="f5429-103">Recupera el token de FileDef real que se usa en los metadatos (en contraposición al token asignado por ALink).</span><span class="sxs-lookup"><span data-stu-id="f5429-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5429-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f5429-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5429-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f5429-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="f5429-106">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f5429-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="f5429-107">Token del archivo agregado tal y como se recuperó del método AddFile o del método addImport (.</span><span class="sxs-lookup"><span data-stu-id="f5429-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="f5429-108">Recibe el token FileDef.</span><span class="sxs-lookup"><span data-stu-id="f5429-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f5429-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f5429-109">Return Value</span></span>  
 <span data-ttu-id="f5429-110">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="f5429-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5429-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f5429-111">Requirements</span></span>  
 <span data-ttu-id="f5429-112">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="f5429-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5429-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5429-113">See also</span></span>

- [<span data-ttu-id="f5429-114">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f5429-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="f5429-115">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f5429-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="f5429-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="f5429-116">ALink API</span></span>](index.md)

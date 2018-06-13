---
title: SetManifestFile (Método)
ms.date: 03/30/2017
api_name:
- IALink3.SetManifestFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetManifestFile
helpviewer_keywords:
- SetManifestFile method
ms.assetid: 1b33de4c-19cb-4a36-a93f-8675b2a36d58
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8f8398c16b27836b772e8ac56ee1f7e8494f4be0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403574"
---
# <a name="setmanifestfile-method"></a><span data-ttu-id="a163d-102">SetManifestFile (Método)</span><span class="sxs-lookup"><span data-stu-id="a163d-102">SetManifestFile Method</span></span>
<span data-ttu-id="a163d-103">Permite especificar o restablecer el archivo de manifiesto que el vinculador usa al crear el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a163d-103">Enables you to specify or reset the manifest file that the linker uses when it creates the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a163d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a163d-104">Syntax</span></span>  
  
```  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a163d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a163d-105">Parameters</span></span>  
 `pszFile`  
  
 <span data-ttu-id="a163d-106">El nombre del archivo de manifiesto cuyo contenido se coloca en el blob de recursos de Win32.</span><span class="sxs-lookup"><span data-stu-id="a163d-106">The name of the manifest file whose contents are put into the Win32 resources blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a163d-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a163d-107">Return Value</span></span>  
 <span data-ttu-id="a163d-108">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="a163d-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a163d-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a163d-109">Remarks</span></span>  
 <span data-ttu-id="a163d-110">Esto se llama antes de solicitar la Win32ResBlob.</span><span class="sxs-lookup"><span data-stu-id="a163d-110">Call this before asking for the Win32ResBlob.</span></span> <span data-ttu-id="a163d-111">El valor de la `pszFile` parámetro es el nombre del archivo de manifiesto cuyo contenido se lee y se coloca en los recursos de Win32 con el identificador de RT_MANIFEST.</span><span class="sxs-lookup"><span data-stu-id="a163d-111">The value of the `pszFile` parameter is the name of the manifest file whose contents are read and put in the Win32 resources with ID of RT_MANIFEST.</span></span> <span data-ttu-id="a163d-112">Cuando se llama mediante un parámetro es null, se borran los manifiestos leídos previamente.</span><span class="sxs-lookup"><span data-stu-id="a163d-112">When called by using a parameter of NULL, any previously read manifest is cleared.</span></span> <span data-ttu-id="a163d-113">Esto permite restablecer el estado del vinculador que el de tiempo de inicialización.</span><span class="sxs-lookup"><span data-stu-id="a163d-113">This enables one to reset the state of the linker to that of initialization time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a163d-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a163d-114">Requirements</span></span>  
 <span data-ttu-id="a163d-115">Requiere aLink.h</span><span class="sxs-lookup"><span data-stu-id="a163d-115">Requires aLink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a163d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a163d-116">See Also</span></span>  
 [<span data-ttu-id="a163d-117">IALink3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a163d-117">IALink3 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink3-interface.md)  
 [<span data-ttu-id="a163d-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="a163d-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)  
 [<span data-ttu-id="a163d-119">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a163d-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="a163d-120">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="a163d-120">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)

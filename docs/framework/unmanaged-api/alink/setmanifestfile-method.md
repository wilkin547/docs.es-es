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
ms.openlocfilehash: df97f4c37d8f335ce183685debd7c0933be910ed
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445561"
---
# <a name="setmanifestfile-method"></a><span data-ttu-id="30c24-102">SetManifestFile (Método)</span><span class="sxs-lookup"><span data-stu-id="30c24-102">SetManifestFile Method</span></span>
<span data-ttu-id="30c24-103">Permite especificar o restablecer el archivo de manifiesto que el vinculador utiliza al crear el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="30c24-103">Enables you to specify or reset the manifest file that the linker uses when it creates the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30c24-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="30c24-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="30c24-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="30c24-105">Parameters</span></span>  
 `pszFile`  
  
 <span data-ttu-id="30c24-106">Nombre del archivo de manifiesto cuyo contenido se coloca en el BLOB de recursos de Win32.</span><span class="sxs-lookup"><span data-stu-id="30c24-106">The name of the manifest file whose contents are put into the Win32 resources blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30c24-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="30c24-107">Return Value</span></span>  
 <span data-ttu-id="30c24-108">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="30c24-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30c24-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="30c24-109">Remarks</span></span>  
 <span data-ttu-id="30c24-110">Llame a este método antes de solicitar el Win32ResBlob.</span><span class="sxs-lookup"><span data-stu-id="30c24-110">Call this before asking for the Win32ResBlob.</span></span> <span data-ttu-id="30c24-111">El valor del parámetro `pszFile` es el nombre del archivo de manifiesto cuyo contenido se lee y se coloca en los recursos de Win32 con el identificador de RT_MANIFEST.</span><span class="sxs-lookup"><span data-stu-id="30c24-111">The value of the `pszFile` parameter is the name of the manifest file whose contents are read and put in the Win32 resources with ID of RT_MANIFEST.</span></span> <span data-ttu-id="30c24-112">Cuando se llama con un parámetro de NULL, se borra cualquier manifiesto leído previamente.</span><span class="sxs-lookup"><span data-stu-id="30c24-112">When called by using a parameter of NULL, any previously read manifest is cleared.</span></span> <span data-ttu-id="30c24-113">Esto permite restablecer el estado del enlazador con respecto al tiempo de inicialización.</span><span class="sxs-lookup"><span data-stu-id="30c24-113">This enables one to reset the state of the linker to that of initialization time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30c24-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="30c24-114">Requirements</span></span>  
 <span data-ttu-id="30c24-115">Requiere aLink. h</span><span class="sxs-lookup"><span data-stu-id="30c24-115">Requires aLink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30c24-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="30c24-116">See also</span></span>

- [<span data-ttu-id="30c24-117">IALink3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="30c24-117">IALink3 Interface</span></span>](ialink3-interface.md)
- [<span data-ttu-id="30c24-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="30c24-118">ALink API</span></span>](index.md)
- [<span data-ttu-id="30c24-119">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="30c24-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="30c24-120">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="30c24-120">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)

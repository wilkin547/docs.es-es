---
description: 'Más información sobre: método Getwin32resblob ('
title: GetWin32ResBlob (Método)
ms.date: 03/30/2017
api_name:
- IALink.GetWin32ResBlob
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetWin32ResBlob
helpviewer_keywords:
- GetWin32ResBlob method
ms.assetid: 36997e04-f9f6-4254-a041-6767ac6c51d9
topic_type:
- apiref
ms.openlocfilehash: e1140b14bfba56dfac03c443a537d6d2188575b8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718270"
---
# <a name="getwin32resblob-method"></a><span data-ttu-id="e570d-103">GetWin32ResBlob (Método)</span><span class="sxs-lookup"><span data-stu-id="e570d-103">GetWin32ResBlob Method</span></span>

<span data-ttu-id="e570d-104">Recupera el BLOB de recursos de Win32.</span><span class="sxs-lookup"><span data-stu-id="e570d-104">Retrieves Win32 resource blob.</span></span> <span data-ttu-id="e570d-105">Llame a este método después de establecer las opciones de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e570d-105">Call this method after setting assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e570d-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e570d-106">Syntax</span></span>  
  
```cpp  
HRESULT GetWin32ResBlob(  
    mdAssembly    AssemblyID,  
    mdToken       FileToken,  
    BOOL          fDll,  
    LPCWSTR       pszIconFile,  
    const void**  ppResBlob,  
    DWORD*        pcbResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e570d-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e570d-107">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="e570d-108">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e570d-108">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="e570d-109">Token de archivo que se usa para recuperar el nombre de archivo que se utilizará al construir el recurso de versión de Win32.</span><span class="sxs-lookup"><span data-stu-id="e570d-109">File token used to retrieve the filename to be used when constructing the Win32 Version resource</span></span>  
  
 `fDll`  
 <span data-ttu-id="e570d-110">TRUE si file es un archivo DLL, false para un archivo EXE.</span><span class="sxs-lookup"><span data-stu-id="e570d-110">TRUE if file is a DLL, false for an EXE.</span></span>  
  
 `pszIconFile`  
 <span data-ttu-id="e570d-111">Icono opcional que se va a insertar en el BLOB de recursos.</span><span class="sxs-lookup"><span data-stu-id="e570d-111">Optional icon to insert into the resource blob.</span></span>  
  
 `ppResBlob`  
 <span data-ttu-id="e570d-112">Recibe el BLOB de recursos.</span><span class="sxs-lookup"><span data-stu-id="e570d-112">Receives the resource blob.</span></span>  
  
 `pcbResBlob`  
 <span data-ttu-id="e570d-113">Recibe el tamaño del BLOB.</span><span class="sxs-lookup"><span data-stu-id="e570d-113">Receives the size of the blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e570d-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e570d-114">Return Value</span></span>  

 <span data-ttu-id="e570d-115">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="e570d-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e570d-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e570d-116">Requirements</span></span>  

 <span data-ttu-id="e570d-117">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="e570d-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e570d-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e570d-118">See also</span></span>

- [<span data-ttu-id="e570d-119">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e570d-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="e570d-120">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e570d-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="e570d-121">API de ALink</span><span class="sxs-lookup"><span data-stu-id="e570d-121">ALink API</span></span>](index.md)

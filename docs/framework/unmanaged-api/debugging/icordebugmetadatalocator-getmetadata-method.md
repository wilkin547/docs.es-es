---
description: 'Más información sobre: ICorDebugMetaDataLocator (:: GetMetaData (método)'
title: ICorDebugMetaDataLocator::GetMetaData (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugMetaDataLocator.GetMetaData
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMetaDataLocator::GetMetaData
helpviewer_keywords:
- ICorDebugMetaDataLocator::GetMetaData method [.NET Framework debugging]
- GetMetaData method, ICorDebugMetaDataLocator interface [.NET Framework debugging]
ms.assetid: f9b0ff22-54db-45eb-9cc3-508000a3141d
topic_type:
- apiref
ms.openlocfilehash: 419a03e42a54057ab70e31a368e918612f3a85f6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691697"
---
# <a name="icordebugmetadatalocatorgetmetadata-method"></a><span data-ttu-id="88441-103">ICorDebugMetaDataLocator::GetMetaData (Método)</span><span class="sxs-lookup"><span data-stu-id="88441-103">ICorDebugMetaDataLocator::GetMetaData Method</span></span>

<span data-ttu-id="88441-104">Pide al depurador que devuelva la ruta de acceso completa a un módulo cuyos metadatos se necesitan para completar una operación solicitada por el depurador.</span><span class="sxs-lookup"><span data-stu-id="88441-104">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88441-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="88441-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaData(  
      [in] LPCWSTR wszImagePath,  
      [in] DWORD   dwImageTimeStamp,  
      [in] DWORD   dwImageSize,  
      [in] ULONG32 cchPathBuffer,  
      [out] ULONG32 * pcchPathBuffer,  
      [out, size_is(cchPathBuffer), length_is(*pcchPathBuffer)]  
               WCHAR wszPathBuffer[]  
      );  
```  
  
## <a name="parameters"></a><span data-ttu-id="88441-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="88441-106">Parameters</span></span>  

 `wszImagePath`  
 <span data-ttu-id="88441-107">[in] Cadena terminada en NULL que representa la ruta de acceso completa al archivo.</span><span class="sxs-lookup"><span data-stu-id="88441-107">[in] A null-terminated string that represents the full path to the file.</span></span> <span data-ttu-id="88441-108">Si la ruta de acceso completa no está disponible, el nombre y la extensión del archivo (*filename*.*extensión*).</span><span class="sxs-lookup"><span data-stu-id="88441-108">If the full path is not available, the name and extension of the file (*filename*.*extension*).</span></span>  
  
 `dwImageTimeStamp`  
 <span data-ttu-id="88441-109">[in] Marca de tiempo de los encabezados del archivo PE de la imagen.</span><span class="sxs-lookup"><span data-stu-id="88441-109">[in] The time stamp from the image's PE file headers.</span></span> <span data-ttu-id="88441-110">Este parámetro puede usarse potencialmente para una búsqueda del servidor de símbolos ([SymSrv](/windows/desktop/debug/using-symsrv)).</span><span class="sxs-lookup"><span data-stu-id="88441-110">This parameter can potentially be used for a symbol server ([SymSrv](/windows/desktop/debug/using-symsrv)) lookup.</span></span>  
  
 `dwImageSize`  
 <span data-ttu-id="88441-111">[in] Tamaño de la imagen en los encabezados de archivo PE.</span><span class="sxs-lookup"><span data-stu-id="88441-111">[in] The image size from PE file headers.</span></span> <span data-ttu-id="88441-112">Este parámetro podría usarse para una búsqueda de SymSrv.</span><span class="sxs-lookup"><span data-stu-id="88441-112">This parameter can potentially be used for a SymSrv lookup.</span></span>  
  
 `cchPathBuffer`  
 <span data-ttu-id="88441-113">[in] Número de caracteres de `wszPathBuffer`.</span><span class="sxs-lookup"><span data-stu-id="88441-113">[in] The character count in `wszPathBuffer`.</span></span>  
  
 `pcchPathBuffer`  
 <span data-ttu-id="88441-114">[out] Número de `WCHAR` escritos en `wszPathBuffer`.</span><span class="sxs-lookup"><span data-stu-id="88441-114">[out] The count of `WCHAR`s written to `wszPathBuffer`.</span></span>  
  
 <span data-ttu-id="88441-115">Si el método devuelve E_NOT_SUFFICIENT_BUFFER, contiene el número de `WCHAR` necesarios para almacenar la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="88441-115">If the method returns E_NOT_SUFFICIENT_BUFFER, contains the count of `WCHAR`s needed to store the path.</span></span>  
  
 `wszPathBuffer`  
 <span data-ttu-id="88441-116">[out] Puntero a un búfer en el que el depurador copiará la ruta de acceso completa del archivo que contiene los metadatos solicitados.</span><span class="sxs-lookup"><span data-stu-id="88441-116">[out] Pointer to a buffer into which the debugger will copy the full path of the file that contains the requested metadata.</span></span>  
  
 <span data-ttu-id="88441-117">La `ofReadOnly` marca de la enumeración [CorOpenFlags (](../metadata/coropenflags-enumeration.md) se usa para solicitar acceso de solo lectura a los metadatos de este archivo.</span><span class="sxs-lookup"><span data-stu-id="88441-117">The `ofReadOnly` flag from the [CorOpenFlags](../metadata/coropenflags-enumeration.md) enumeration is used to request read-only access to the metadata in this file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="88441-118">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="88441-118">Return Value</span></span>  

 <span data-ttu-id="88441-119">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="88441-119">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span> <span data-ttu-id="88441-120">Cualquier otro HRESULT de error indica que el archivo no se puede recuperar.</span><span class="sxs-lookup"><span data-stu-id="88441-120">All other failure HRESULTs indicate that the file is not retrievable.</span></span>  
  
|<span data-ttu-id="88441-121">HRESULT</span><span class="sxs-lookup"><span data-stu-id="88441-121">HRESULT</span></span>|<span data-ttu-id="88441-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="88441-122">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="88441-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="88441-123">S_OK</span></span>|<span data-ttu-id="88441-124">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="88441-124">The method completed successfully.</span></span> <span data-ttu-id="88441-125">`wszPathBuffer` contiene la ruta de acceso completa al archivo y termina en NULL.</span><span class="sxs-lookup"><span data-stu-id="88441-125">`wszPathBuffer` contains the full path to the file and is null-terminated.</span></span>|  
|<span data-ttu-id="88441-126">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="88441-126">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="88441-127">El tamaño actual de `wszPathBuffer` no es suficiente para contener la ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="88441-127">The current size of `wszPathBuffer` is not sufficient to hold the full path.</span></span> <span data-ttu-id="88441-128">En este caso, `pcchPathBuffer` contiene el número necesario de `WCHAR`, incluido el carácter NULL final, y se llama a `GetMetaData` una segunda vez con el tamaño de búfer solicitado.</span><span class="sxs-lookup"><span data-stu-id="88441-128">In this case, `pcchPathBuffer` contains the needed count of `WCHAR`s, including the terminating null character, and `GetMetaData` is called a second time with the requested buffer size.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88441-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="88441-129">Remarks</span></span>  

 <span data-ttu-id="88441-130">Si `wszImagePath` contiene una ruta de acceso completa para un módulo de un volcado de memoria, especifica la ruta de acceso del equipo desde el que se recopiló el volcado de memoria.</span><span class="sxs-lookup"><span data-stu-id="88441-130">If `wszImagePath` contains a full path for a module from a dump, it specifies the path from the computer where the dump was collected.</span></span> <span data-ttu-id="88441-131">Puede que el archivo no exista en esta ubicación o que en ella haya almacenado un archivo incorrecto con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="88441-131">The file may not exist at this location, or an incorrect file with the same name may be stored on the path.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88441-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="88441-132">Requirements</span></span>  

 <span data-ttu-id="88441-133">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88441-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88441-134">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="88441-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="88441-135">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="88441-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="88441-136">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88441-136">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88441-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="88441-137">See also</span></span>

- [<span data-ttu-id="88441-138">ICorDebugThread4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="88441-138">ICorDebugThread4 Interface</span></span>](icordebugthread4-interface.md)
- [<span data-ttu-id="88441-139">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="88441-139">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="88441-140">Depuración</span><span class="sxs-lookup"><span data-stu-id="88441-140">Debugging</span></span>](index.md)

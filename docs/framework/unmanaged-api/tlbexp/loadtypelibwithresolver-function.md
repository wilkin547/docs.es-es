---
title: LoadTypeLibWithResolver (Función)
ms.date: 03/30/2017
api_name:
- LoadTypeLibWithResolver
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- LoadTypeLibWithResolver
helpviewer_keywords:
- LoadTypeLibWithResolver function [.NET Framework]
ms.assetid: 7123a89b-eb9b-463a-a552-a081e33b0a3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b6a217e2212bb900d7ba83ccdd9cb00d30454baf
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45749653"
---
# <a name="loadtypelibwithresolver-function"></a><span data-ttu-id="b1b49-102">LoadTypeLibWithResolver (Función)</span><span class="sxs-lookup"><span data-stu-id="b1b49-102">LoadTypeLibWithResolver Function</span></span>
<span data-ttu-id="b1b49-103">Carga una biblioteca de tipos y utiliza proporcionado [ITypeLibResolver (interfaz)](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) para resolver las bibliotecas de tipos internamente que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="b1b49-103">Loads a type library and uses the supplied [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) to resolve any internally referenced type libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1b49-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b1b49-104">Syntax</span></span>  
  
```  
HRESULT LoadTypeLibWithResolver(  
    [in]  LPCOLESTR           szFile,  
    [in]  REGKIND             regkind,  
    [in]  ITypeLibResolver   *pTlbResolver,  
    [out] ITypeLib          **pptlib);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b1b49-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b1b49-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="b1b49-106">[in] La ruta de acceso de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="b1b49-106">[in] The file path of the type library.</span></span>  
  
 `regkind`  
 <span data-ttu-id="b1b49-107">[in] Un [enumeración REGKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/ne-oleauto-tagregkind) marca que controla cómo se registra la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="b1b49-107">[in] A [REGKIND enumeration](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/ne-oleauto-tagregkind) flag that controls how the type library is registered.</span></span> <span data-ttu-id="b1b49-108">Sus valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="b1b49-108">Its possible values are:</span></span>  
  
-   <span data-ttu-id="b1b49-109">`REGKIND_DEFAULT`: Use el comportamiento predeterminado del registro.</span><span class="sxs-lookup"><span data-stu-id="b1b49-109">`REGKIND_DEFAULT`: Use default registration behavior.</span></span>  
  
-   <span data-ttu-id="b1b49-110">`REGKIND_REGISTER`: Registre esta biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="b1b49-110">`REGKIND_REGISTER`: Register this type library.</span></span>  
  
-   <span data-ttu-id="b1b49-111">`REGKIND_NONE`: No registra esta biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="b1b49-111">`REGKIND_NONE`: Do not register this type library.</span></span>  
  
 `pTlbResolver`  
 <span data-ttu-id="b1b49-112">[in] Un puntero a la implementación de la [ITypeLibResolver (interfaz)](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md).</span><span class="sxs-lookup"><span data-stu-id="b1b49-112">[in] A pointer to the implementation of the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md).</span></span>  
  
 `pptlib`  
 <span data-ttu-id="b1b49-113">[out] Una referencia a la biblioteca de tipos que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="b1b49-113">[out] A reference to the type library that is being loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b1b49-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b1b49-114">Return Value</span></span>  
 <span data-ttu-id="b1b49-115">Uno de los valores HRESULT enumerados en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="b1b49-115">One of the HRESULT values listed in the following table.</span></span>  
  
|<span data-ttu-id="b1b49-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b1b49-116">Return value</span></span>|<span data-ttu-id="b1b49-117">Significado</span><span class="sxs-lookup"><span data-stu-id="b1b49-117">Meaning</span></span>|  
|------------------|-------------|  
|`S_OK`|<span data-ttu-id="b1b49-118">Correcto.</span><span class="sxs-lookup"><span data-stu-id="b1b49-118">Success.</span></span>|  
|`E_OUTOFMEMORY`|<span data-ttu-id="b1b49-119">Memoria insuficiente</span><span class="sxs-lookup"><span data-stu-id="b1b49-119">Out of memory.</span></span>|  
|`E_POINTER`|<span data-ttu-id="b1b49-120">Uno o varios de los punteros no son válidos.</span><span class="sxs-lookup"><span data-stu-id="b1b49-120">One or more of the pointers are invalid.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="b1b49-121">Uno o varios de los argumentos no son válidos.</span><span class="sxs-lookup"><span data-stu-id="b1b49-121">One or more of the arguments are invalid.</span></span>|  
|`TYPE_E_IOERROR`|<span data-ttu-id="b1b49-122">La función no pudo escribir en el archivo.</span><span class="sxs-lookup"><span data-stu-id="b1b49-122">The function could not write to the file.</span></span>|  
|`TYPE_E_REGISTRYACCESS`|<span data-ttu-id="b1b49-123">No se pudo abrir la base de datos de registro del sistema.</span><span class="sxs-lookup"><span data-stu-id="b1b49-123">The system registration database could not be opened.</span></span>|  
|`TYPE_E_INVALIDSTATE`|<span data-ttu-id="b1b49-124">No se pudo abrir la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="b1b49-124">The type library could not be opened.</span></span>|  
|`TYPE_E_CANTLOADLIBRARY`|<span data-ttu-id="b1b49-125">No se pudo cargar la biblioteca de tipos o DLL.</span><span class="sxs-lookup"><span data-stu-id="b1b49-125">The type library or DLL could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1b49-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b1b49-126">Remarks</span></span>  
 <span data-ttu-id="b1b49-127">El [Tlbexp.exe (exportador de biblioteca)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) llamadas la `LoadTypeLibWithResolver` función durante el proceso de conversión de ensamblado a biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="b1b49-127">The [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) calls the `LoadTypeLibWithResolver` function during the assembly-to-type-library conversion process.</span></span>  
  
 <span data-ttu-id="b1b49-128">Esta función carga la biblioteca de tipos especificada con acceso mínimo al registro.</span><span class="sxs-lookup"><span data-stu-id="b1b49-128">This function loads the specified type library with minimal access to the registry.</span></span> <span data-ttu-id="b1b49-129">La función, a continuación, examina la biblioteca de tipos para las bibliotecas de tipo de referencia internamente, cada uno de los cuales debe cargarse y agregado a la biblioteca de tipos de elemento primario.</span><span class="sxs-lookup"><span data-stu-id="b1b49-129">The function then examines the type library for internally referenced type libraries, each of which must be loaded and added to the parent type library.</span></span>  
  
 <span data-ttu-id="b1b49-130">Antes de que se puede cargar una biblioteca de tipos que se hace referencia, su ruta de acceso del archivo de referencia debe resolverse en una ruta de acceso completa al archivo.</span><span class="sxs-lookup"><span data-stu-id="b1b49-130">Before a referenced type library can be loaded, its reference file path must be resolved to a full file path.</span></span> <span data-ttu-id="b1b49-131">Esto se logra a través de la [ResolveTypeLib (método)](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) proporcionada por el [ITypeLibResolver (interfaz)](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), que se pasa en el `pTlbResolver` parámetro.</span><span class="sxs-lookup"><span data-stu-id="b1b49-131">This is accomplished through the [ResolveTypeLib method](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) that is provided by the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), which is passed in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="b1b49-132">Cuando se conoce la ruta de acceso completa al archivo de la biblioteca de tipos que se hace referencia, el `LoadTypeLibWithResolver` función carga y agrega la biblioteca de tipos que se hace referencia a la biblioteca de tipos de elemento primario, crear una biblioteca de tipos combinada principal.</span><span class="sxs-lookup"><span data-stu-id="b1b49-132">When the full file path of the referenced type library is known, the `LoadTypeLibWithResolver` function loads and adds the referenced type library to the parent type library, creating a combined master type library.</span></span>  
  
 <span data-ttu-id="b1b49-133">Después de la función se resuelve y carga todas las bibliotecas de tipo de referencia internamente, devuelve una referencia a la biblioteca de tipos principal en el `pptlib` parámetro.</span><span class="sxs-lookup"><span data-stu-id="b1b49-133">After the function resolves and loads all internally referenced type libraries, it returns a reference to the master resolved type library in the `pptlib` parameter.</span></span>  
  
 <span data-ttu-id="b1b49-134">El `LoadTypeLibWithResolver` función generalmente se llama mediante el [Tlbexp.exe (exportador de biblioteca)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), que proporciona su propio interno [ITypeLibResolver (interfaz)](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementación en el `pTlbResolver` parámetro.</span><span class="sxs-lookup"><span data-stu-id="b1b49-134">The `LoadTypeLibWithResolver` function is generally called by the [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), which supplies its own internal [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementation in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="b1b49-135">Si se llama a `LoadTypeLibWithResolver` directamente, debe proporcionar su propia [ITypeLibResolver (interfaz)](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementación.</span><span class="sxs-lookup"><span data-stu-id="b1b49-135">If you call `LoadTypeLibWithResolver` directly, you must supply your own [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1b49-136">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b1b49-136">Requirements</span></span>  
 <span data-ttu-id="b1b49-137">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1b49-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1b49-138">**Encabezado:** TlbRef.h</span><span class="sxs-lookup"><span data-stu-id="b1b49-138">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="b1b49-139">**Biblioteca:** TlbRef.lib</span><span class="sxs-lookup"><span data-stu-id="b1b49-139">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="b1b49-140">**Versión de .NET framework:** 3.5, 3.0 y 2.0</span><span class="sxs-lookup"><span data-stu-id="b1b49-140">**.NET Framework Version:** 3.5, 3.0, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1b49-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1b49-141">See Also</span></span>  
 [<span data-ttu-id="b1b49-142">Funciones auxiliares Tlbexp</span><span class="sxs-lookup"><span data-stu-id="b1b49-142">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [<span data-ttu-id="b1b49-143">LoadTypeLibEx de la función</span><span class="sxs-lookup"><span data-stu-id="b1b49-143">LoadTypeLibEx Function</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)

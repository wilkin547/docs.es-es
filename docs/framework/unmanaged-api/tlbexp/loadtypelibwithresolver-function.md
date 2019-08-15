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
ms.openlocfilehash: 6b9bec757071a98e085ccdeee3fc66bfc07f52bc
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040161"
---
# <a name="loadtypelibwithresolver-function"></a><span data-ttu-id="a9fb6-102">LoadTypeLibWithResolver (Función)</span><span class="sxs-lookup"><span data-stu-id="a9fb6-102">LoadTypeLibWithResolver Function</span></span>
<span data-ttu-id="a9fb6-103">Carga una biblioteca de tipos y usa la [interfaz ITypeLibResolver (](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) proporcionada para resolver cualquier biblioteca de tipos a la que se hace referencia internamente.</span><span class="sxs-lookup"><span data-stu-id="a9fb6-103">Loads a type library and uses the supplied [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) to resolve any internally referenced type libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9fb6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9fb6-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadTypeLibWithResolver(  
    [in]  LPCOLESTR           szFile,  
    [in]  REGKIND             regkind,  
    [in]  ITypeLibResolver   *pTlbResolver,  
    [out] ITypeLib          **pptlib);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9fb6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a9fb6-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="a9fb6-106">de Ruta de acceso del archivo de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="a9fb6-106">[in] The file path of the type library.</span></span>  
  
 `regkind`  
 <span data-ttu-id="a9fb6-107">de Marca de [enumeración REGKIND](https://docs.microsoft.com/windows/win32/api/oleauto/ne-oleauto-regkind) que controla cómo se registra la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="a9fb6-107">[in] A [REGKIND enumeration](https://docs.microsoft.com/windows/win32/api/oleauto/ne-oleauto-regkind) flag that controls how the type library is registered.</span></span> <span data-ttu-id="a9fb6-108">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="a9fb6-108">Its possible values are:</span></span>  
  
- <span data-ttu-id="a9fb6-109">`REGKIND_DEFAULT`: Usar el comportamiento de registro predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a9fb6-109">`REGKIND_DEFAULT`: Use default registration behavior.</span></span>  
  
- <span data-ttu-id="a9fb6-110">`REGKIND_REGISTER`: Registre esta biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="a9fb6-110">`REGKIND_REGISTER`: Register this type library.</span></span>  
  
- <span data-ttu-id="a9fb6-111">`REGKIND_NONE`: No registre esta biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="a9fb6-111">`REGKIND_NONE`: Do not register this type library.</span></span>  
  
 `pTlbResolver`  
 <span data-ttu-id="a9fb6-112">de Puntero a la implementación de la [interfaz ITypeLibResolver (](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a9fb6-112">[in] A pointer to the implementation of the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md).</span></span>  
  
 `pptlib`  
 <span data-ttu-id="a9fb6-113">enuncia Referencia a la biblioteca de tipos que se está cargando.</span><span class="sxs-lookup"><span data-stu-id="a9fb6-113">[out] A reference to the type library that is being loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9fb6-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a9fb6-114">Return Value</span></span>  
 <span data-ttu-id="a9fb6-115">Uno de los valores HRESULT que se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="a9fb6-115">One of the HRESULT values listed in the following table.</span></span>  
  
|<span data-ttu-id="a9fb6-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a9fb6-116">Return value</span></span>|<span data-ttu-id="a9fb6-117">Significado</span><span class="sxs-lookup"><span data-stu-id="a9fb6-117">Meaning</span></span>|  
|------------------|-------------|  
|`S_OK`|<span data-ttu-id="a9fb6-118">Correcto.</span><span class="sxs-lookup"><span data-stu-id="a9fb6-118">Success.</span></span>|  
|`E_OUTOFMEMORY`|<span data-ttu-id="a9fb6-119">Memoria insuficiente</span><span class="sxs-lookup"><span data-stu-id="a9fb6-119">Out of memory.</span></span>|  
|`E_POINTER`|<span data-ttu-id="a9fb6-120">Uno o varios de los punteros no son válidos.</span><span class="sxs-lookup"><span data-stu-id="a9fb6-120">One or more of the pointers are invalid.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="a9fb6-121">Uno o varios argumentos no son válidos.</span><span class="sxs-lookup"><span data-stu-id="a9fb6-121">One or more of the arguments are invalid.</span></span>|  
|`TYPE_E_IOERROR`|<span data-ttu-id="a9fb6-122">La función no pudo escribir en el archivo.</span><span class="sxs-lookup"><span data-stu-id="a9fb6-122">The function could not write to the file.</span></span>|  
|`TYPE_E_REGISTRYACCESS`|<span data-ttu-id="a9fb6-123">No se pudo abrir la base de datos de registro del sistema.</span><span class="sxs-lookup"><span data-stu-id="a9fb6-123">The system registration database could not be opened.</span></span>|  
|`TYPE_E_INVALIDSTATE`|<span data-ttu-id="a9fb6-124">No se pudo abrir la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="a9fb6-124">The type library could not be opened.</span></span>|  
|`TYPE_E_CANTLOADLIBRARY`|<span data-ttu-id="a9fb6-125">No se pudo cargar la biblioteca de tipos o DLL.</span><span class="sxs-lookup"><span data-stu-id="a9fb6-125">The type library or DLL could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9fb6-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a9fb6-126">Remarks</span></span>  
 <span data-ttu-id="a9fb6-127">[Tlbexp. exe (exportador](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) de la biblioteca de tipos) `LoadTypeLibWithResolver` llama a la función durante el proceso de conversión de ensamblado a biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="a9fb6-127">The [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) calls the `LoadTypeLibWithResolver` function during the assembly-to-type-library conversion process.</span></span>  
  
 <span data-ttu-id="a9fb6-128">Esta función carga la biblioteca de tipos especificada con acceso mínimo al registro.</span><span class="sxs-lookup"><span data-stu-id="a9fb6-128">This function loads the specified type library with minimal access to the registry.</span></span> <span data-ttu-id="a9fb6-129">A continuación, la función examina la biblioteca de tipos para las bibliotecas de tipos a las que se hace referencia internamente, cada una de las cuales se debe cargar y agregar a la biblioteca de tipos primaria.</span><span class="sxs-lookup"><span data-stu-id="a9fb6-129">The function then examines the type library for internally referenced type libraries, each of which must be loaded and added to the parent type library.</span></span>  
  
 <span data-ttu-id="a9fb6-130">Antes de que se pueda cargar una biblioteca de tipos a la que se hace referencia, su ruta de acceso al archivo de referencia debe resolverse en una ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="a9fb6-130">Before a referenced type library can be loaded, its reference file path must be resolved to a full file path.</span></span> <span data-ttu-id="a9fb6-131">Esto se logra mediante el [método resolvetypelib (](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) que proporciona la [interfaz ITypeLibResolver (](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), que se pasa en el `pTlbResolver` parámetro.</span><span class="sxs-lookup"><span data-stu-id="a9fb6-131">This is accomplished through the [ResolveTypeLib method](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) that is provided by the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), which is passed in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="a9fb6-132">Cuando se conoce la ruta de acceso completa del archivo de la biblioteca de tipos `LoadTypeLibWithResolver` a la que se hace referencia, la función carga y agrega la biblioteca de tipos a la biblioteca de tipos primaria, y crea una biblioteca de tipos maestra combinada.</span><span class="sxs-lookup"><span data-stu-id="a9fb6-132">When the full file path of the referenced type library is known, the `LoadTypeLibWithResolver` function loads and adds the referenced type library to the parent type library, creating a combined master type library.</span></span>  
  
 <span data-ttu-id="a9fb6-133">Una vez que la función resuelve y carga todas las bibliotecas de tipos a las que se hace referencia internamente, devuelve una referencia a la biblioteca `pptlib` de tipos principal resuelta en el parámetro.</span><span class="sxs-lookup"><span data-stu-id="a9fb6-133">After the function resolves and loads all internally referenced type libraries, it returns a reference to the master resolved type library in the `pptlib` parameter.</span></span>  
  
 <span data-ttu-id="a9fb6-134">La función se llama generalmente mediante [Tlbexp. exe (exportador de la biblioteca de tipos)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), que proporciona su propia implementación interna de la `pTlbResolver` [interfaz ITypeLibResolver (](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) en el parámetro. `LoadTypeLibWithResolver`</span><span class="sxs-lookup"><span data-stu-id="a9fb6-134">The `LoadTypeLibWithResolver` function is generally called by the [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), which supplies its own internal [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementation in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="a9fb6-135">Si llama directamente `LoadTypeLibWithResolver` a, debe proporcionar su propia implementación de la [interfaz ITypeLibResolver (](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="a9fb6-135">If you call `LoadTypeLibWithResolver` directly, you must supply your own [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9fb6-136">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9fb6-136">Requirements</span></span>  
 <span data-ttu-id="a9fb6-137">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9fb6-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9fb6-138">**Encabezado**: TlbRef. h</span><span class="sxs-lookup"><span data-stu-id="a9fb6-138">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="a9fb6-139">**Biblioteca** TlbRef.lib</span><span class="sxs-lookup"><span data-stu-id="a9fb6-139">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="a9fb6-140">**Versión de .NET Framework:** 3.5, 3.0, 2.0</span><span class="sxs-lookup"><span data-stu-id="a9fb6-140">**.NET Framework Version:** 3.5, 3.0, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9fb6-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9fb6-141">See also</span></span>

- [<span data-ttu-id="a9fb6-142">Funciones del asistente Tlbexp</span><span class="sxs-lookup"><span data-stu-id="a9fb6-142">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [<span data-ttu-id="a9fb6-143">LoadTypeLibEx función)</span><span class="sxs-lookup"><span data-stu-id="a9fb6-143">LoadTypeLibEx Function</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)

---
description: 'Más información acerca de: LoadTypeLibWithResolver ((función)'
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
ms.openlocfilehash: 6747199364a549d922ad73bfac3e93b329d1172a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646223"
---
# <a name="loadtypelibwithresolver-function"></a><span data-ttu-id="2c2d9-103">LoadTypeLibWithResolver (Función)</span><span class="sxs-lookup"><span data-stu-id="2c2d9-103">LoadTypeLibWithResolver Function</span></span>

<span data-ttu-id="2c2d9-104">Carga una biblioteca de tipos y usa la [interfaz ITypeLibResolver (](itypelibresolver-interface.md) proporcionada para resolver cualquier biblioteca de tipos a la que se hace referencia internamente.</span><span class="sxs-lookup"><span data-stu-id="2c2d9-104">Loads a type library and uses the supplied [ITypeLibResolver interface](itypelibresolver-interface.md) to resolve any internally referenced type libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c2d9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2c2d9-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadTypeLibWithResolver(  
    [in]  LPCOLESTR           szFile,  
    [in]  REGKIND             regkind,  
    [in]  ITypeLibResolver   *pTlbResolver,  
    [out] ITypeLib          **pptlib);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c2d9-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2c2d9-106">Parameters</span></span>  

 `szFile`  
 <span data-ttu-id="2c2d9-107">de Ruta de acceso del archivo de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="2c2d9-107">[in] The file path of the type library.</span></span>  
  
 `regkind`  
 <span data-ttu-id="2c2d9-108">de Marca de [enumeración REGKIND](/windows/win32/api/oleauto/ne-oleauto-regkind) que controla cómo se registra la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="2c2d9-108">[in] A [REGKIND enumeration](/windows/win32/api/oleauto/ne-oleauto-regkind) flag that controls how the type library is registered.</span></span> <span data-ttu-id="2c2d9-109">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="2c2d9-109">Its possible values are:</span></span>  
  
- <span data-ttu-id="2c2d9-110">`REGKIND_DEFAULT`: Usar el comportamiento de registro predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2c2d9-110">`REGKIND_DEFAULT`: Use default registration behavior.</span></span>  
  
- <span data-ttu-id="2c2d9-111">`REGKIND_REGISTER`: Registre esta biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="2c2d9-111">`REGKIND_REGISTER`: Register this type library.</span></span>  
  
- <span data-ttu-id="2c2d9-112">`REGKIND_NONE`: No registrar esta biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="2c2d9-112">`REGKIND_NONE`: Do not register this type library.</span></span>  
  
 `pTlbResolver`  
 <span data-ttu-id="2c2d9-113">de Puntero a la implementación de la [interfaz ITypeLibResolver (](itypelibresolver-interface.md).</span><span class="sxs-lookup"><span data-stu-id="2c2d9-113">[in] A pointer to the implementation of the [ITypeLibResolver interface](itypelibresolver-interface.md).</span></span>  
  
 `pptlib`  
 <span data-ttu-id="2c2d9-114">enuncia Referencia a la biblioteca de tipos que se está cargando.</span><span class="sxs-lookup"><span data-stu-id="2c2d9-114">[out] A reference to the type library that is being loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c2d9-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2c2d9-115">Return Value</span></span>  

 <span data-ttu-id="2c2d9-116">Uno de los valores HRESULT que se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="2c2d9-116">One of the HRESULT values listed in the following table.</span></span>  
  
|<span data-ttu-id="2c2d9-117">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2c2d9-117">Return value</span></span>|<span data-ttu-id="2c2d9-118">Significado</span><span class="sxs-lookup"><span data-stu-id="2c2d9-118">Meaning</span></span>|  
|------------------|-------------|  
|`S_OK`|<span data-ttu-id="2c2d9-119">Correcto.</span><span class="sxs-lookup"><span data-stu-id="2c2d9-119">Success.</span></span>|  
|`E_OUTOFMEMORY`|<span data-ttu-id="2c2d9-120">Memoria insuficiente</span><span class="sxs-lookup"><span data-stu-id="2c2d9-120">Out of memory.</span></span>|  
|`E_POINTER`|<span data-ttu-id="2c2d9-121">Uno o varios de los punteros no son válidos.</span><span class="sxs-lookup"><span data-stu-id="2c2d9-121">One or more of the pointers are invalid.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="2c2d9-122">Uno o varios argumentos no son válidos.</span><span class="sxs-lookup"><span data-stu-id="2c2d9-122">One or more of the arguments are invalid.</span></span>|  
|`TYPE_E_IOERROR`|<span data-ttu-id="2c2d9-123">La función no pudo escribir en el archivo.</span><span class="sxs-lookup"><span data-stu-id="2c2d9-123">The function could not write to the file.</span></span>|  
|`TYPE_E_REGISTRYACCESS`|<span data-ttu-id="2c2d9-124">No se pudo abrir la base de datos de registro del sistema.</span><span class="sxs-lookup"><span data-stu-id="2c2d9-124">The system registration database could not be opened.</span></span>|  
|`TYPE_E_INVALIDSTATE`|<span data-ttu-id="2c2d9-125">No se pudo abrir la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="2c2d9-125">The type library could not be opened.</span></span>|  
|`TYPE_E_CANTLOADLIBRARY`|<span data-ttu-id="2c2d9-126">No se pudo cargar la biblioteca de tipos o DLL.</span><span class="sxs-lookup"><span data-stu-id="2c2d9-126">The type library or DLL could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c2d9-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2c2d9-127">Remarks</span></span>  

 <span data-ttu-id="2c2d9-128">El [Tlbexp.exe (exportador de la biblioteca de tipos)](../../tools/tlbexp-exe-type-library-exporter.md) llama a la `LoadTypeLibWithResolver` función durante el proceso de conversión de ensamblado a biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="2c2d9-128">The [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md) calls the `LoadTypeLibWithResolver` function during the assembly-to-type-library conversion process.</span></span>  
  
 <span data-ttu-id="2c2d9-129">Esta función carga la biblioteca de tipos especificada con acceso mínimo al registro.</span><span class="sxs-lookup"><span data-stu-id="2c2d9-129">This function loads the specified type library with minimal access to the registry.</span></span> <span data-ttu-id="2c2d9-130">A continuación, la función examina la biblioteca de tipos para las bibliotecas de tipos a las que se hace referencia internamente, cada una de las cuales se debe cargar y agregar a la biblioteca de tipos primaria.</span><span class="sxs-lookup"><span data-stu-id="2c2d9-130">The function then examines the type library for internally referenced type libraries, each of which must be loaded and added to the parent type library.</span></span>  
  
 <span data-ttu-id="2c2d9-131">Antes de que se pueda cargar una biblioteca de tipos a la que se hace referencia, su ruta de acceso al archivo de referencia debe resolverse en una ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="2c2d9-131">Before a referenced type library can be loaded, its reference file path must be resolved to a full file path.</span></span> <span data-ttu-id="2c2d9-132">Esto se logra mediante el [método resolvetypelib (](resolvetypelib-method.md) que proporciona la [interfaz ITypeLibResolver (](itypelibresolver-interface.md), que se pasa en el `pTlbResolver` parámetro.</span><span class="sxs-lookup"><span data-stu-id="2c2d9-132">This is accomplished through the [ResolveTypeLib method](resolvetypelib-method.md) that is provided by the [ITypeLibResolver interface](itypelibresolver-interface.md), which is passed in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="2c2d9-133">Cuando se conoce la ruta de acceso completa del archivo de la biblioteca de tipos a la que se hace referencia, la `LoadTypeLibWithResolver` función carga y agrega la biblioteca de tipos a la biblioteca de tipos primaria, y crea una biblioteca de tipos maestra combinada.</span><span class="sxs-lookup"><span data-stu-id="2c2d9-133">When the full file path of the referenced type library is known, the `LoadTypeLibWithResolver` function loads and adds the referenced type library to the parent type library, creating a combined master type library.</span></span>  
  
 <span data-ttu-id="2c2d9-134">Una vez que la función resuelve y carga todas las bibliotecas de tipos a las que se hace referencia internamente, devuelve una referencia a la biblioteca de tipos principal resuelta en el `pptlib` parámetro.</span><span class="sxs-lookup"><span data-stu-id="2c2d9-134">After the function resolves and loads all internally referenced type libraries, it returns a reference to the master resolved type library in the `pptlib` parameter.</span></span>  
  
 <span data-ttu-id="2c2d9-135">La `LoadTypeLibWithResolver` función suele llamarla el [Tlbexp.exe (exportador de la biblioteca de tipos)](../../tools/tlbexp-exe-type-library-exporter.md), que proporciona su propia implementación interna de la [interfaz ITypeLibResolver (](itypelibresolver-interface.md) en el `pTlbResolver` parámetro.</span><span class="sxs-lookup"><span data-stu-id="2c2d9-135">The `LoadTypeLibWithResolver` function is generally called by the [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md), which supplies its own internal [ITypeLibResolver interface](itypelibresolver-interface.md) implementation in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="2c2d9-136">Si llama `LoadTypeLibWithResolver` directamente a, debe proporcionar su propia implementación de la [interfaz ITypeLibResolver (](itypelibresolver-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="2c2d9-136">If you call `LoadTypeLibWithResolver` directly, you must supply your own [ITypeLibResolver interface](itypelibresolver-interface.md) implementation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c2d9-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2c2d9-137">Requirements</span></span>  

 <span data-ttu-id="2c2d9-138">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c2d9-138">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c2d9-139">**Encabezado:** TlbRef. h</span><span class="sxs-lookup"><span data-stu-id="2c2d9-139">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="2c2d9-140">**Biblioteca:** TlbRef. lib</span><span class="sxs-lookup"><span data-stu-id="2c2d9-140">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="2c2d9-141">**.NET Framework versión:** 3,5, 3,0, 2,0</span><span class="sxs-lookup"><span data-stu-id="2c2d9-141">**.NET Framework Version:** 3.5, 3.0, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c2d9-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c2d9-142">See also</span></span>

- [<span data-ttu-id="2c2d9-143">Funciones del asistente Tlbexp</span><span class="sxs-lookup"><span data-stu-id="2c2d9-143">Tlbexp Helper Functions</span></span>](index.md)
- [<span data-ttu-id="2c2d9-144">LoadTypeLibEx función)</span><span class="sxs-lookup"><span data-stu-id="2c2d9-144">LoadTypeLibEx Function</span></span>](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)

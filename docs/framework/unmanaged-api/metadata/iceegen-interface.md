---
title: ICeeGen (Interfaz)
ms.date: 03/30/2017
api_name:
- ICeeGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen
helpviewer_keywords:
- ICeeGen interface [.NET Framework metadata]
ms.assetid: 383d20b0-efe9-4e71-8fb8-1186b2e7d0c0
topic_type:
- apiref
ms.openlocfilehash: 2c180a135608350b0feec3f419be98f4f428b186
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704518"
---
# <a name="iceegen-interface"></a><span data-ttu-id="49216-102">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="49216-102">ICeeGen Interface</span></span>

<span data-ttu-id="49216-103">Proporciona métodos para la compilación de código dinámico.</span><span class="sxs-lookup"><span data-stu-id="49216-103">Provides methods for dynamic code compilation.</span></span>  
  
 <span data-ttu-id="49216-104">Esta interfaz está obsoleta y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="49216-104">This interface is obsolete and should not be used.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="49216-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="49216-105">Methods</span></span>  
  
|<span data-ttu-id="49216-106">Método</span><span class="sxs-lookup"><span data-stu-id="49216-106">Method</span></span>|<span data-ttu-id="49216-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="49216-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="49216-108">Método AddSectionReloc</span><span class="sxs-lookup"><span data-stu-id="49216-108">AddSectionReloc Method</span></span>](iceegen-addsectionreloc-method.md)|<span data-ttu-id="49216-109">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="49216-109">Obsolete.</span></span> <span data-ttu-id="49216-110">Agrega una instrucción. reloc al código base.</span><span class="sxs-lookup"><span data-stu-id="49216-110">Adds a .reloc instruction to the code base.</span></span>|  
|[<span data-ttu-id="49216-111">Método AllocateMethodBuffer</span><span class="sxs-lookup"><span data-stu-id="49216-111">AllocateMethodBuffer Method</span></span>](iceegen-allocatemethodbuffer-method.md)|<span data-ttu-id="49216-112">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="49216-112">Obsolete.</span></span> <span data-ttu-id="49216-113">Crea un búfer con el tamaño especificado para un método y obtiene la dirección virtual relativa del método.</span><span class="sxs-lookup"><span data-stu-id="49216-113">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>|  
|[<span data-ttu-id="49216-114">Método ComputePointer</span><span class="sxs-lookup"><span data-stu-id="49216-114">ComputePointer Method</span></span>](iceegen-computepointer-method.md)|<span data-ttu-id="49216-115">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="49216-115">Obsolete.</span></span> <span data-ttu-id="49216-116">Determina el búfer para la sección de código especificada.</span><span class="sxs-lookup"><span data-stu-id="49216-116">Determines the buffer for the specified code section.</span></span>|  
|[<span data-ttu-id="49216-117">Método EmitString</span><span class="sxs-lookup"><span data-stu-id="49216-117">EmitString Method</span></span>](iceegen-emitstring-method.md)|<span data-ttu-id="49216-118">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="49216-118">Obsolete.</span></span> <span data-ttu-id="49216-119">Emite la cadena especificada en el código base.</span><span class="sxs-lookup"><span data-stu-id="49216-119">Emits the specified string into the code base.</span></span>|  
|[<span data-ttu-id="49216-120">Método GenerateCeeFile</span><span class="sxs-lookup"><span data-stu-id="49216-120">GenerateCeeFile Method</span></span>](iceegen-generateceefile-method.md)|<span data-ttu-id="49216-121">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="49216-121">Obsolete.</span></span> <span data-ttu-id="49216-122">Genera un archivo de código base que contiene el código base cargado actualmente en este `ICeeGen` .</span><span class="sxs-lookup"><span data-stu-id="49216-122">Generates a code-base file that contains the code base currently loaded into this `ICeeGen`.</span></span>|  
|[<span data-ttu-id="49216-123">Método GenerateCeeMemoryImage</span><span class="sxs-lookup"><span data-stu-id="49216-123">GenerateCeeMemoryImage Method</span></span>](iceegen-generateceememoryimage-method.md)|<span data-ttu-id="49216-124">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="49216-124">Obsolete.</span></span> <span data-ttu-id="49216-125">Genera una imagen en memoria para la base de código.</span><span class="sxs-lookup"><span data-stu-id="49216-125">Generates an image in memory for the code base.</span></span>|  
|[<span data-ttu-id="49216-126">Método GetIlSection</span><span class="sxs-lookup"><span data-stu-id="49216-126">GetIlSection Method</span></span>](iceegen-getilsection-method.md)|<span data-ttu-id="49216-127">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="49216-127">Obsolete.</span></span> <span data-ttu-id="49216-128">Obtiene la sección de la base de código de lenguaje intermedio a la que hace referencia el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="49216-128">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>|  
|[<span data-ttu-id="49216-129">Método GetIMapTokenIface</span><span class="sxs-lookup"><span data-stu-id="49216-129">GetIMapTokenIface Method</span></span>](iceegen-getimaptokeniface-method.md)|<span data-ttu-id="49216-130">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="49216-130">Obsolete.</span></span> <span data-ttu-id="49216-131">Obtiene la interfaz a la que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="49216-131">Gets the interface referenced by the specified token.</span></span>|  
|[<span data-ttu-id="49216-132">Método GetMethodBuffer</span><span class="sxs-lookup"><span data-stu-id="49216-132">GetMethodBuffer Method</span></span>](iceegen-getmethodbuffer-method.md)|<span data-ttu-id="49216-133">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="49216-133">Obsolete.</span></span> <span data-ttu-id="49216-134">Obtiene un búfer del tamaño adecuado para el método en la dirección virtual relativa especificada.</span><span class="sxs-lookup"><span data-stu-id="49216-134">Gets a buffer of the appropriate size for the method at the specified relative virtual address.</span></span>|  
|[<span data-ttu-id="49216-135">Método GetSectionBlock</span><span class="sxs-lookup"><span data-stu-id="49216-135">GetSectionBlock Method</span></span>](iceegen-getsectionblock-method.md)|<span data-ttu-id="49216-136">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="49216-136">Obsolete.</span></span> <span data-ttu-id="49216-137">Obtiene un bloque de sección del código base.</span><span class="sxs-lookup"><span data-stu-id="49216-137">Gets a section block of the code base.</span></span>|  
|[<span data-ttu-id="49216-138">Método GetSectionCreate</span><span class="sxs-lookup"><span data-stu-id="49216-138">GetSectionCreate Method</span></span>](iceegen-getsectioncreate-method.md)|<span data-ttu-id="49216-139">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="49216-139">Obsolete.</span></span> <span data-ttu-id="49216-140">Genera y obtiene una sección de código usando el nombre y los valores de marca especificados.</span><span class="sxs-lookup"><span data-stu-id="49216-140">Generates and gets a code section using the specified name and flag values.</span></span>|  
|[<span data-ttu-id="49216-141">Método GetSectionDataLen</span><span class="sxs-lookup"><span data-stu-id="49216-141">GetSectionDataLen Method</span></span>](iceegen-getsectiondatalen-method.md)|<span data-ttu-id="49216-142">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="49216-142">Obsolete.</span></span> <span data-ttu-id="49216-143">Obtiene la longitud de la sección especificada.</span><span class="sxs-lookup"><span data-stu-id="49216-143">Gets the length of the specified section.</span></span>|  
|[<span data-ttu-id="49216-144">GetString (Método)</span><span class="sxs-lookup"><span data-stu-id="49216-144">GetString Method</span></span>](iceegen-getstring-method.md)|<span data-ttu-id="49216-145">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="49216-145">Obsolete.</span></span> <span data-ttu-id="49216-146">Obtiene la cadena almacenada en la dirección virtual relativa especificada.</span><span class="sxs-lookup"><span data-stu-id="49216-146">Gets the string stored at the specified relative virtual address.</span></span>|  
|[<span data-ttu-id="49216-147">Método GetStringSection</span><span class="sxs-lookup"><span data-stu-id="49216-147">GetStringSection Method</span></span>](iceegen-getstringsection-method.md)|<span data-ttu-id="49216-148">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="49216-148">Obsolete.</span></span> <span data-ttu-id="49216-149">Obtiene una representación de cadena de la sección de código a la que hace referencia el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="49216-149">Gets a string representation of the code section referenced by the specified handle.</span></span>|  
|[<span data-ttu-id="49216-150">Método TruncateSection</span><span class="sxs-lookup"><span data-stu-id="49216-150">TruncateSection Method</span></span>](iceegen-truncatesection-method.md)|<span data-ttu-id="49216-151">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="49216-151">Obsolete.</span></span> <span data-ttu-id="49216-152">Trunca la sección de código especificada según la longitud especificada.</span><span class="sxs-lookup"><span data-stu-id="49216-152">Truncates the specified code section by the specified length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="49216-153">Requisitos</span><span class="sxs-lookup"><span data-stu-id="49216-153">Requirements</span></span>  

 <span data-ttu-id="49216-154">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49216-154">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49216-155">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="49216-155">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="49216-156">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="49216-156">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="49216-157">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49216-157">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49216-158">Consulte también</span><span class="sxs-lookup"><span data-stu-id="49216-158">See also</span></span>

- [<span data-ttu-id="49216-159">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="49216-159">Metadata Interfaces</span></span>](metadata-interfaces.md)

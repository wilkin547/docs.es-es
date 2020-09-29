---
description: -linkresource (Opciones del compilador de C#)
title: -linkresource (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /linkresource
helpviewer_keywords:
- /linkresource compiler option [C#]
- linkres compiler option [C#]
- /linkres compiler option [C#]
- -linkres compiler option [C#]
- -linkresource compiler option [C#]
- linkresource compiler option [C#]
ms.assetid: 440c26c2-77c1-4811-a0a3-57cce3f5fc96
ms.openlocfilehash: 4efa0cbf286b40ad971bad66a7acce15e553eb39
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194107"
---
# <a name="-linkresource-c-compiler-options"></a><span data-ttu-id="d19fe-103">-linkresource (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="d19fe-103">-linkresource (C# Compiler Options)</span></span>

<span data-ttu-id="d19fe-104">Crea un vínculo a un recurso de .NET en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="d19fe-104">Creates a link to a .NET resource in the output file.</span></span> <span data-ttu-id="d19fe-105">El archivo de recursos no se agrega al archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="d19fe-105">The resource file is not added to the output file.</span></span> <span data-ttu-id="d19fe-106">Esta opción difiere de la opción [-resource](./resource-compiler-option.md), la cual sí inserta un archivo de recursos en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="d19fe-106">This differs from the [-resource](./resource-compiler-option.md) option which does embed a resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d19fe-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d19fe-107">Syntax</span></span>  
  
```console  
-linkresource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="d19fe-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d19fe-108">Arguments</span></span>  

 `filename`  
 <span data-ttu-id="d19fe-109">El archivo de recursos de .NET con el que quiere crear un vínculo desde el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d19fe-109">The .NET resource file to which you want to link from the assembly.</span></span>  
  
 <span data-ttu-id="d19fe-110">`identifier` (opcional)</span><span class="sxs-lookup"><span data-stu-id="d19fe-110">`identifier` (optional)</span></span>  
 <span data-ttu-id="d19fe-111">El nombre lógico del recurso; nombre que se usa para cargar el recurso.</span><span class="sxs-lookup"><span data-stu-id="d19fe-111">The logical name for the resource; the name that is used to load the resource.</span></span> <span data-ttu-id="d19fe-112">El valor predeterminado es el nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="d19fe-112">The default is the name of the file.</span></span>  
  
 <span data-ttu-id="d19fe-113">`accessibility-modifier` (opcional)</span><span class="sxs-lookup"><span data-stu-id="d19fe-113">`accessibility-modifier` (optional)</span></span>  
 <span data-ttu-id="d19fe-114">La accesibilidad del recurso: pública o privada.</span><span class="sxs-lookup"><span data-stu-id="d19fe-114">The accessibility of the resource: public or private.</span></span> <span data-ttu-id="d19fe-115">El valor predeterminado es public.</span><span class="sxs-lookup"><span data-stu-id="d19fe-115">The default is public.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d19fe-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d19fe-116">Remarks</span></span>  

 <span data-ttu-id="d19fe-117">De manera predeterminada, los recursos vinculados son públicos en el ensamblado cuando se crean con el compilador de C#.</span><span class="sxs-lookup"><span data-stu-id="d19fe-117">By default, linked resources are public in the assembly when they are created with the C# compiler.</span></span> <span data-ttu-id="d19fe-118">Para que sean privados, especifique el modificador de accesibilidad `private`.</span><span class="sxs-lookup"><span data-stu-id="d19fe-118">To make the resources private, specify `private` as the accessibility modifier.</span></span> <span data-ttu-id="d19fe-119">No se permite ningún otro modificador distinto de `public` o `private`.</span><span class="sxs-lookup"><span data-stu-id="d19fe-119">No other modifier other than `public` or `private` is allowed.</span></span>  
  
 <span data-ttu-id="d19fe-120">**-linkresource** requiere una de las opciones [-target](./target-compiler-option.md) distinta de **-target:module**.</span><span class="sxs-lookup"><span data-stu-id="d19fe-120">**-linkresource** requires one of the [-target](./target-compiler-option.md) options other than **-target:module**.</span></span>  
  
 <span data-ttu-id="d19fe-121">Si `filename` es un archivo de recursos de .NET creado, por ejemplo, con [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) o en el entorno de desarrollo, se puede acceder a él con miembros del espacio de nombres <xref:System.Resources>.</span><span class="sxs-lookup"><span data-stu-id="d19fe-121">If `filename` is a .NET resource file created, for example, by [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="d19fe-122">Para obtener más información, vea <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d19fe-122">For more information, see <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d19fe-123">Para todos los demás recursos, use los métodos `GetManifestResource` de la clase <xref:System.Reflection.Assembly> para tener acceso al recurso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d19fe-123">For all other resources, use the `GetManifestResource` methods in the <xref:System.Reflection.Assembly> class to access the resource at run time.</span></span>  
  
 <span data-ttu-id="d19fe-124">El archivo especificado en `filename` puede tener cualquier formato.</span><span class="sxs-lookup"><span data-stu-id="d19fe-124">The file specified in `filename` can be any format.</span></span> <span data-ttu-id="d19fe-125">Por ejemplo, se puede hacer que una DLL nativa forme parte de un ensamblado para que se pueda instalar en la caché global de ensamblados y sea accesible desde código administrado del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d19fe-125">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span> <span data-ttu-id="d19fe-126">En el segundo de los siguientes ejemplos se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="d19fe-126">The second of the following examples shows how to do this.</span></span> <span data-ttu-id="d19fe-127">También es posible realizar lo mismo en Assembly Linker.</span><span class="sxs-lookup"><span data-stu-id="d19fe-127">You can do the same thing in the Assembly Linker.</span></span> <span data-ttu-id="d19fe-128">En el tercer ejemplo se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="d19fe-128">The third of the following examples shows how to do this.</span></span> <span data-ttu-id="d19fe-129">Para obtener más información, vea [Al.exe (Assembly Linker)](../../../framework/tools/al-exe-assembly-linker.md) y [Trabajar con ensamblados y la memoria caché global de ensamblados](../../../framework/app-domains/working-with-assemblies-and-the-gac.md).</span><span class="sxs-lookup"><span data-stu-id="d19fe-129">For more information, see [Al.exe (Assembly Linker)](../../../framework/tools/al-exe-assembly-linker.md) and [Working with Assemblies and the Global Assembly Cache](../../../framework/app-domains/working-with-assemblies-and-the-gac.md).</span></span>  
  
 <span data-ttu-id="d19fe-130">**-linkres** es la forma abreviada de **-linkresource**.</span><span class="sxs-lookup"><span data-stu-id="d19fe-130">**-linkres** is the short form of **-linkresource**.</span></span>  
  
 <span data-ttu-id="d19fe-131">Esta opción del compilador no está disponible en Visual Studio y no se puede cambiar mediante programación.</span><span class="sxs-lookup"><span data-stu-id="d19fe-131">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d19fe-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d19fe-132">Example</span></span>  

 <span data-ttu-id="d19fe-133">Para compilar `in.cs` y vincularlo al archivo de recursos `rf.resource`:</span><span class="sxs-lookup"><span data-stu-id="d19fe-133">Compile `in.cs` and link to resource file `rf.resource`:</span></span>  
  
```console  
csc -linkresource:rf.resource in.cs  
```  
  
## <a name="example"></a><span data-ttu-id="d19fe-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d19fe-134">Example</span></span>  

 <span data-ttu-id="d19fe-135">Compile `A.cs` en un archivo DLL, vincúlelo a un archivo DLL nativo N.dll y coloque el resultado en la caché global de ensamblados (GAC).</span><span class="sxs-lookup"><span data-stu-id="d19fe-135">Compile `A.cs` into a DLL, link to a native DLL N.dll, and put the output in the Global Assembly Cache (GAC).</span></span> <span data-ttu-id="d19fe-136">En este ejemplo, A.dll y N.dll residen en la GAC.</span><span class="sxs-lookup"><span data-stu-id="d19fe-136">In this example, both A.dll and N.dll will reside in the GAC.</span></span>  
  
```console  
csc -linkresource:N.dll -t:library A.cs  
gacutil -i A.dll  
```  
  
## <a name="example"></a><span data-ttu-id="d19fe-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d19fe-137">Example</span></span>  

 <span data-ttu-id="d19fe-138">Este ejemplo hace lo mismo que el anterior, pero usa las opciones de Assembly Linker.</span><span class="sxs-lookup"><span data-stu-id="d19fe-138">This example does the same thing as the previous one, but by using Assembly Linker options.</span></span>  
  
```console  
csc -t:module A.cs  
al -out:A.dll A.netmodule -link:N.dll
gacutil -i A.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="d19fe-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="d19fe-139">See also</span></span>

- [<span data-ttu-id="d19fe-140">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="d19fe-140">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="d19fe-141">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="d19fe-141">Al.exe (Assembly Linker)</span></span>](../../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="d19fe-142">Trabajar con ensamblados y la memoria caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="d19fe-142">Working with Assemblies and the Global Assembly Cache</span></span>](../../../framework/app-domains/working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="d19fe-143">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="d19fe-143">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

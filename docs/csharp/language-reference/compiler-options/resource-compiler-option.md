---
description: -resource (Opciones del compilador de C#)
title: -resource (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /resource
helpviewer_keywords:
- -resource compiler option [C#]
- /resource compiler option [C#]
- -res compiler option [C#]
- /res compiler option [C#]
- res compiler option [C#]
- resource compiler option [C#]
ms.assetid: 5212666e-98ab-47e4-a497-b5545ab15c7f
ms.openlocfilehash: 6f90ce6c1590784cefbd5f15ca8a36941aad77ed
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91193782"
---
# <a name="-resource-c-compiler-options"></a><span data-ttu-id="6578e-103">-resource (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="6578e-103">-resource (C# Compiler Options)</span></span>

<span data-ttu-id="6578e-104">Inserta el recurso especificado en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="6578e-104">Embeds the specified resource into the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6578e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6578e-105">Syntax</span></span>  
  
```console  
-resource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="6578e-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6578e-106">Arguments</span></span>  

 `filename`  
 <span data-ttu-id="6578e-107">El archivo de recursos de .NET que quiere insertar en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="6578e-107">The .NET resource file that you want to embed in the output file.</span></span>  
  
 <span data-ttu-id="6578e-108">`identifier` (opcional)</span><span class="sxs-lookup"><span data-stu-id="6578e-108">`identifier` (optional)</span></span>  
 <span data-ttu-id="6578e-109">El nombre lógico del recurso; nombre que se usa para cargar el recurso.</span><span class="sxs-lookup"><span data-stu-id="6578e-109">The logical name for the resource; the name that is used to load the resource.</span></span> <span data-ttu-id="6578e-110">El valor predeterminado es el nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="6578e-110">The default is the name of the file name.</span></span>  
  
 <span data-ttu-id="6578e-111">`accessibility-modifier` (opcional)</span><span class="sxs-lookup"><span data-stu-id="6578e-111">`accessibility-modifier` (optional)</span></span>  
 <span data-ttu-id="6578e-112">La accesibilidad del recurso: pública o privada.</span><span class="sxs-lookup"><span data-stu-id="6578e-112">The accessibility of the resource: public or private.</span></span> <span data-ttu-id="6578e-113">El valor predeterminado es public.</span><span class="sxs-lookup"><span data-stu-id="6578e-113">The default is public.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6578e-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6578e-114">Remarks</span></span>  

 <span data-ttu-id="6578e-115">Use [-linkresource](./linkresource-compiler-option.md) para vincular un recurso a un ensamblado y no agregar el archivo de recursos al archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="6578e-115">Use [-linkresource](./linkresource-compiler-option.md) to link a resource to an assembly and not add the resource file to the output file.</span></span>  
  
 <span data-ttu-id="6578e-116">De manera predeterminada, los recursos son públicos en el ensamblado cuando se crean mediante el compilador de C#.</span><span class="sxs-lookup"><span data-stu-id="6578e-116">By default, resources are public in the assembly when they are created by using the C# compiler.</span></span> <span data-ttu-id="6578e-117">Para que sean privados, especifique el modificador de accesibilidad `private`.</span><span class="sxs-lookup"><span data-stu-id="6578e-117">To make the resources private, specify `private` as the accessibility modifier.</span></span> <span data-ttu-id="6578e-118">No se permite ninguna otra accesibilidad distinta de `public` o `private`.</span><span class="sxs-lookup"><span data-stu-id="6578e-118">No other accessibility other than `public` or `private` is allowed.</span></span>  
  
 <span data-ttu-id="6578e-119">Si `filename` es un archivo de recursos de .NET creado, por ejemplo, con [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) o en el entorno de desarrollo, se puede acceder a él con miembros del espacio de nombres <xref:System.Resources>.</span><span class="sxs-lookup"><span data-stu-id="6578e-119">If `filename` is a .NET resource file created, for example, by [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="6578e-120">Para obtener más información, vea <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6578e-120">For more information, see <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6578e-121">Para todos los demás recursos, use los métodos `GetManifestResource` de la clase <xref:System.Reflection.Assembly> para tener acceso al recurso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6578e-121">For all other resources, use the `GetManifestResource` methods in the <xref:System.Reflection.Assembly> class to access the resource at run time.</span></span>  
  
 <span data-ttu-id="6578e-122">**-res** es la forma abreviada de **-resource**.</span><span class="sxs-lookup"><span data-stu-id="6578e-122">**-res** is the short form of **-resource**.</span></span>  
  
 <span data-ttu-id="6578e-123">El orden de los recursos en el archivo de salida se determina a partir del orden especificado en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="6578e-123">The order of the resources in the output file is determined from the order specified on the command line.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="6578e-124">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6578e-124">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="6578e-125">Agregue un archivo de recursos al proyecto.</span><span class="sxs-lookup"><span data-stu-id="6578e-125">Add a resource file to your project.</span></span>  
  
2. <span data-ttu-id="6578e-126">Seleccione el archivo que quiere insertar en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="6578e-126">Select the file that you want to embed in **Solution Explorer**.</span></span>  
  
3. <span data-ttu-id="6578e-127">Seleccione **Acción de compilación** para el archivo en la ventana **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6578e-127">Select **Build Action** for the file in the **Properties** window.</span></span>  
  
4. <span data-ttu-id="6578e-128">Establezca **Acción de compilación** en **Recurso incrustado**.</span><span class="sxs-lookup"><span data-stu-id="6578e-128">Set **Build Action** to **Embedded Resource**.</span></span>  
  
 <span data-ttu-id="6578e-129">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.FileProperties2.BuildAction%2A>.</span><span class="sxs-lookup"><span data-stu-id="6578e-129">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.FileProperties2.BuildAction%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6578e-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6578e-130">Example</span></span>  

 <span data-ttu-id="6578e-131">Compile `in.cs` y adjunte el archivo de recursos `rf.resource`:</span><span class="sxs-lookup"><span data-stu-id="6578e-131">Compile `in.cs` and attach resource file `rf.resource`:</span></span>  
  
```console  
csc -resource:rf.resource in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="6578e-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="6578e-132">See also</span></span>

- [<span data-ttu-id="6578e-133">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="6578e-133">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="6578e-134">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="6578e-134">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

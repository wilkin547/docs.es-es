---
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
ms.openlocfilehash: 8744d0f85859367ada51e4c44e767e681a3487bf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="-resource-c-compiler-options"></a><span data-ttu-id="22690-102">-resource (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="22690-102">-resource (C# Compiler Options)</span></span>
<span data-ttu-id="22690-103">Inserta el recurso especificado en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="22690-103">Embeds the specified resource into the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22690-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="22690-104">Syntax</span></span>  
  
```console  
-resource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="22690-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="22690-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="22690-106">El archivo de recursos de .NET Framework que quiere insertar en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="22690-106">The .NET Framework resource file that you want to embed in the output file.</span></span>  
  
 <span data-ttu-id="22690-107">`identifier` (opcional)</span><span class="sxs-lookup"><span data-stu-id="22690-107">`identifier` (optional)</span></span>  
 <span data-ttu-id="22690-108">El nombre lógico del recurso; nombre que se usa para cargar el recurso.</span><span class="sxs-lookup"><span data-stu-id="22690-108">The logical name for the resource; the name that is used to load the resource.</span></span> <span data-ttu-id="22690-109">El valor predeterminado es el nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="22690-109">The default is the name of the file name.</span></span>  
  
 <span data-ttu-id="22690-110">`accessibility-modifier` (opcional)</span><span class="sxs-lookup"><span data-stu-id="22690-110">`accessibility-modifier` (optional)</span></span>  
 <span data-ttu-id="22690-111">La accesibilidad del recurso: pública o privada.</span><span class="sxs-lookup"><span data-stu-id="22690-111">The accessibility of the resource: public or private.</span></span> <span data-ttu-id="22690-112">El valor predeterminado es que sea pública.</span><span class="sxs-lookup"><span data-stu-id="22690-112">The default is public.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22690-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="22690-113">Remarks</span></span>  
 <span data-ttu-id="22690-114">Use [-linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) para vincular un recurso a un ensamblado y no agregar el archivo de recursos al archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="22690-114">Use [-linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) to link a resource to an assembly and not add the resource file to the output file.</span></span>  
  
 <span data-ttu-id="22690-115">De manera predeterminada, los recursos son públicos en el ensamblado cuando se crean mediante el compilador de C#.</span><span class="sxs-lookup"><span data-stu-id="22690-115">By default, resources are public in the assembly when they are created by using the C# compiler.</span></span> <span data-ttu-id="22690-116">Para que sean privados, especifique el modificador de accesibilidad `private`.</span><span class="sxs-lookup"><span data-stu-id="22690-116">To make the resources private, specify `private` as the accessibility modifier.</span></span> <span data-ttu-id="22690-117">No se permite ninguna otra accesibilidad distinta de `public` o `private`.</span><span class="sxs-lookup"><span data-stu-id="22690-117">No other accessibility other than `public` or `private` is allowed.</span></span>  
  
 <span data-ttu-id="22690-118">Si `filename` es un archivo de recursos de .NET Framework creado, por ejemplo, con [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) o en el entorno de desarrollo, se puede obtener acceso a él con miembros del espacio de nombres <xref:System.Resources>.</span><span class="sxs-lookup"><span data-stu-id="22690-118">If `filename` is a .NET Framework resource file created, for example, by [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="22690-119">Para obtener más información, consulta <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="22690-119">For more information, see <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span></span> <span data-ttu-id="22690-120">Para todos los demás recursos, use los métodos `GetManifestResource` de la clase <xref:System.Reflection.Assembly> para tener acceso al recurso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="22690-120">For all other resources, use the `GetManifestResource` methods in the <xref:System.Reflection.Assembly> class to access the resource at run time.</span></span>  
  
 <span data-ttu-id="22690-121">**-res** es la forma abreviada de **-resource**.</span><span class="sxs-lookup"><span data-stu-id="22690-121">**-res** is the short form of **-resource**.</span></span>  
  
 <span data-ttu-id="22690-122">El orden de los recursos en el archivo de salida se determina a partir del orden especificado en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="22690-122">The order of the resources in the output file is determined from the order specified on the command line.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="22690-123">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="22690-123">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="22690-124">Agregue un archivo de recursos al proyecto.</span><span class="sxs-lookup"><span data-stu-id="22690-124">Add a resource file to your project.</span></span>  
  
2.  <span data-ttu-id="22690-125">Seleccione el archivo que quiere insertar en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="22690-125">Select the file that you want to embed in **Solution Explorer**.</span></span>  
  
3.  <span data-ttu-id="22690-126">Seleccione **Acción de compilación** para el archivo en la ventana **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="22690-126">Select **Build Action** for the file in the **Properties** window.</span></span>  
  
4.  <span data-ttu-id="22690-127">Establezca **Acción de compilación** en **Recurso incrustado**.</span><span class="sxs-lookup"><span data-stu-id="22690-127">Set **Build Action** to **Embedded Resource**.</span></span>  
  
 <span data-ttu-id="22690-128">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.FileProperties2.BuildAction%2A>.</span><span class="sxs-lookup"><span data-stu-id="22690-128">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.FileProperties2.BuildAction%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22690-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="22690-129">Example</span></span>  
 <span data-ttu-id="22690-130">Compile `in.cs` y adjunte el archivo de recursos `rf.resource`:</span><span class="sxs-lookup"><span data-stu-id="22690-130">Compile `in.cs` and attach resource file `rf.resource`:</span></span>  
  
```console  
csc -resource:rf.resource in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="22690-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="22690-131">See Also</span></span>  
 [<span data-ttu-id="22690-132">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="22690-132">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="22690-133">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="22690-133">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

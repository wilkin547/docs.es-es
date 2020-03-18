---
title: -reference (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /reference
helpviewer_keywords:
- /r compiler option [C#]
- reference compiler option [C#]
- r compiler option [C#]
- /reference compiler option [C#]
- -r compiler option [C#]
- metadata import [C#]
- public type information [C#]
- -reference compiler option [C#]
ms.assetid: 8d13e5b0-abf6-4c46-bf71-2daf2cd0a6c4
ms.openlocfilehash: 3e6a999d528be111ba2b92886f4e6e3ebf185d5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173671"
---
# <a name="-reference-c-compiler-options"></a><span data-ttu-id="5a8de-102">-reference (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="5a8de-102">-reference (C# Compiler Options)</span></span>
<span data-ttu-id="5a8de-103">La opción **-reference** hace que el compilador importe información de tipo [public](../keywords/public.md) del archivo especificado al proyecto actual, lo que permite hacer referencia a metadatos de los archivos de ensamblado especificados.</span><span class="sxs-lookup"><span data-stu-id="5a8de-103">The **-reference** option causes the compiler to import [public](../keywords/public.md) type information in the specified file into the current project, thus enabling you to reference metadata from the specified assembly files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a8de-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a8de-104">Syntax</span></span>  
  
```console  
-reference:[alias=]filename  
-reference:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="5a8de-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="5a8de-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="5a8de-106">El nombre de un archivo que contiene un manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5a8de-106">The name of a file that contains an assembly manifest.</span></span> <span data-ttu-id="5a8de-107">Para importar más de un archivo, incluya una opción **-reference** diferente para cada archivo.</span><span class="sxs-lookup"><span data-stu-id="5a8de-107">To import more than one file, include a separate **-reference** option for each file.</span></span>  
  
 `alias`  
 <span data-ttu-id="5a8de-108">Un identificador de C# válido que representa un espacio de nombres raíz que contendrá todos los espacios de nombres del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5a8de-108">A valid C# identifier that will represent a root namespace that will contain all namespaces in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a8de-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5a8de-109">Remarks</span></span>  
 <span data-ttu-id="5a8de-110">Para importar desde más de un archivo, incluya una opción **-reference** para cada archivo.</span><span class="sxs-lookup"><span data-stu-id="5a8de-110">To import from more than one file, include a **-reference** option for each file.</span></span>  
  
 <span data-ttu-id="5a8de-111">Los archivos que se importen deben contener un manifiesto; el archivo de salida debe haberse compilado con una de las opciones [-target](./target-compiler-option.md) distinta de [-target:module](./target-module-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="5a8de-111">The files you import must contain a manifest; the output file must have been compiled with one of the [-target](./target-compiler-option.md) options other than [-target:module](./target-module-compiler-option.md).</span></span>  
  
 <span data-ttu-id="5a8de-112">**-r** es la forma abreviada de **-reference**.</span><span class="sxs-lookup"><span data-stu-id="5a8de-112">**-r** is the short form of **-reference**.</span></span>  
  
 <span data-ttu-id="5a8de-113">Use [-addmodule](./addmodule-compiler-option.md) para importar metadatos de un archivo de salida que no contenga un manifiesto de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5a8de-113">Use [-addmodule](./addmodule-compiler-option.md) to import metadata from an output file that does not contain an assembly manifest.</span></span>  
  
 <span data-ttu-id="5a8de-114">Si hace referencia a un ensamblado (ensamblado A) que hace referencia a otro ensamblado (ensamblado B), debe hacer referencia al ensamblado B si:</span><span class="sxs-lookup"><span data-stu-id="5a8de-114">If you reference an assembly (Assembly A) that references another assembly (Assembly B), you will need to reference Assembly B if:</span></span>  
  
- <span data-ttu-id="5a8de-115">Un tipo que se use del ensamblado A hereda de un tipo o implementa una interfaz del ensamblado B.</span><span class="sxs-lookup"><span data-stu-id="5a8de-115">A type you use from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
- <span data-ttu-id="5a8de-116">Se invoca un campo, una propiedad, un evento o un método que tiene un tipo de parámetro o un tipo de valor devuelto del ensamblado B.</span><span class="sxs-lookup"><span data-stu-id="5a8de-116">You invoke a field, property, event, or method that has a return type or parameter type from Assembly B.</span></span>  
  
 <span data-ttu-id="5a8de-117">Use [-lib](./lib-compiler-option.md) para especificar el directorio en el que se encuentran una o varias de las referencias de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5a8de-117">Use [-lib](./lib-compiler-option.md) to specify the directory in which one or more of your assembly references is located.</span></span> <span data-ttu-id="5a8de-118">En el tema **-lib** también se describen los directorios en los que el compilador busca ensamblados.</span><span class="sxs-lookup"><span data-stu-id="5a8de-118">The **-lib** topic also discusses the directories in which the compiler searches for assemblies.</span></span>  
  
 <span data-ttu-id="5a8de-119">Para que el compilador reconozca un tipo de un ensamblado (y no de un módulo), debe obligársele a que resuelva el tipo, lo que se puede conseguir si se define una instancia del tipo.</span><span class="sxs-lookup"><span data-stu-id="5a8de-119">In order for the compiler to recognize a type in an assembly, and not in a module, it needs to be forced to resolve the type, which you can do by defining an instance of the type.</span></span> <span data-ttu-id="5a8de-120">Existen otras formas de que el compilador resuelva nombres de tipos en un ensamblado; por ejemplo, si se hereda de un tipo de un ensamblado, el compilador reconocerá el nombre del tipo.</span><span class="sxs-lookup"><span data-stu-id="5a8de-120">There are other ways to resolve type names in an assembly for the compiler: for example, if you inherit from a type in an assembly, the type name will then be recognized by the compiler.</span></span>  
  
 <span data-ttu-id="5a8de-121">A veces es necesario hacer referencia a dos versiones diferentes del mismo componente desde un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5a8de-121">Sometimes it is necessary to reference two different versions of the same component from within one assembly.</span></span> <span data-ttu-id="5a8de-122">Para ello, use la subopción de alias en el modificador **-reference** de cada archivo para distinguir entre los dos archivos.</span><span class="sxs-lookup"><span data-stu-id="5a8de-122">To do this, use the alias suboption on the **-reference** switch for each file to distinguish between the two files.</span></span> <span data-ttu-id="5a8de-123">Este alias se usará como calificador para el nombre del componente y se resolverá en el componente de uno de los archivos.</span><span class="sxs-lookup"><span data-stu-id="5a8de-123">This alias will be used as a qualifier for the component name, and will resolve to the component in one of the files.</span></span>  
  
 <span data-ttu-id="5a8de-124">De forma predeterminada se usa el archivo de respuesta (.rsp) csc, que hace referencia a los ensamblados de .NET Framework usados habitualmente.</span><span class="sxs-lookup"><span data-stu-id="5a8de-124">The csc response (.rsp) file, which references commonly used .NET Framework assemblies, is used by default.</span></span> <span data-ttu-id="5a8de-125">Use [-noconfig](./noconfig-compiler-option.md) si no quiere que el compilador use csc.rsp.</span><span class="sxs-lookup"><span data-stu-id="5a8de-125">Use [-noconfig](./noconfig-compiler-option.md) if you do not want the compiler to use csc.rsp.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5a8de-126">En Visual Studio, use el cuadro de diálogo **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="5a8de-126">In Visual Studio, use the **Add Reference** dialog box.</span></span> <span data-ttu-id="5a8de-127">Para obtener más información, consulta [How to: Add or Remove References By Using the Reference Manager](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager).</span><span class="sxs-lookup"><span data-stu-id="5a8de-127">For more information, see [How to: Add or Remove References By Using the Reference Manager](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager).</span></span> <span data-ttu-id="5a8de-128">Para garantizar un comportamiento equivalente entre agregar referencias mediante `-reference` y agregar referencias mediante el cuadro de diálogo **Agregar referencia**, establezca la propiedad **Incrustar tipos de interoperabilidad** en **False** para el ensamblado que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="5a8de-128">To ensure equivalent behavior between adding references by using `-reference` and adding references by using the **Add Reference** dialog box, set the **Embed Interop Types** property to **False** for the assembly that you're adding.</span></span> <span data-ttu-id="5a8de-129">El valor predeterminado de la propiedad es **True**.</span><span class="sxs-lookup"><span data-stu-id="5a8de-129">**True** is the default value for the property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a8de-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5a8de-130">Example</span></span>  
 <span data-ttu-id="5a8de-131">En este ejemplo se muestra cómo usar la característica [alias externo](../keywords/extern-alias.md).</span><span class="sxs-lookup"><span data-stu-id="5a8de-131">This example shows how to use the [extern alias](../keywords/extern-alias.md) feature.</span></span>  
  
 <span data-ttu-id="5a8de-132">Compile el archivo de origen e importe los metadatos desde `grid.dll` y `grid20.dll`, que se han compilado previamente.</span><span class="sxs-lookup"><span data-stu-id="5a8de-132">You compile the source file and import metadata from `grid.dll` and `grid20.dll`, which have been compiled previously.</span></span> <span data-ttu-id="5a8de-133">Los dos archivos DLL contienen versiones independientes del mismo componente y se usan dos **-reference** con opciones de alias para compilar el archivo de origen.</span><span class="sxs-lookup"><span data-stu-id="5a8de-133">The two DLLs contain separate versions of the same component, and you use two **-reference** with alias options to compile the source file.</span></span> <span data-ttu-id="5a8de-134">Las opciones tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="5a8de-134">The options look like this:</span></span>  

```console
-reference:GridV1=grid.dll -reference:GridV2=grid20.dll  
```
  
 <span data-ttu-id="5a8de-135">Esto configura los alias externos `GridV1` y `GridV2`, que se usan en el programa por medio de una instrucción `extern`:</span><span class="sxs-lookup"><span data-stu-id="5a8de-135">This sets up the external aliases `GridV1` and `GridV2`, which you use in your program by means of an `extern` statement:</span></span>  
  
```csharp  
extern alias GridV1;  
extern alias GridV2;  
// Using statements go here.  
```  
  
 <span data-ttu-id="5a8de-136">Una vez hecho esto, se puede hacer referencia al control de cuadrícula desde `grid.dll` si se antepone `GridV1` al nombre del control, de esta forma:</span><span class="sxs-lookup"><span data-stu-id="5a8de-136">Once this is done, you can refer to the grid control from `grid.dll` by prefixing the control name with `GridV1`, like this:</span></span>  
  
```csharp  
GridV1::Grid  
```  
  
 <span data-ttu-id="5a8de-137">Además, se puede hacer referencia al control de cuadrícula desde `grid20.dll` si se antepone `GridV2` al nombre del control, de esta forma:</span><span class="sxs-lookup"><span data-stu-id="5a8de-137">In addition, you can refer to the grid control from `grid20.dll` by prefixing the control name with `GridV2` like this:</span></span>  
  
```csharp  
GridV2::Grid
```  
  
## <a name="see-also"></a><span data-ttu-id="5a8de-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a8de-138">See also</span></span>

- [<span data-ttu-id="5a8de-139">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="5a8de-139">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="5a8de-140">Administrar propiedades de proyectos y de soluciones</span><span class="sxs-lookup"><span data-stu-id="5a8de-140">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

---
description: -lib (Opciones del compilador de C#)
title: -lib (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /lib
helpviewer_keywords:
- lib compiler option [C#]
- -lib compiler option [C#]
- /lib compiler option [C#]
ms.assetid: b0efcc88-e8aa-4df4-a00b-8bdef70b7673
ms.openlocfilehash: e53c54dc446d9fea87a9b7a336a38ffaa31704e9
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125454"
---
# <a name="-lib-c-compiler-options"></a><span data-ttu-id="ddefc-103">-lib (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="ddefc-103">-lib (C# Compiler Options)</span></span>
<span data-ttu-id="ddefc-104">La opción **-lib** especifica la ubicación de los ensamblados a los que se hace referencia mediante la opción [-reference (Opciones del compilador de C#)](./reference-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="ddefc-104">The **-lib** option specifies the location of assemblies referenced by means of the [-reference (C# Compiler Options)](./reference-compiler-option.md) option.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddefc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ddefc-105">Syntax</span></span>  
  
```console  
-lib:dir1[,dir2]  
```  
  
## <a name="arguments"></a><span data-ttu-id="ddefc-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ddefc-106">Arguments</span></span>  
 `dir1`  
 <span data-ttu-id="ddefc-107">Un directorio para el compilador para buscar un ensamblado al que se hace referencia si no lo encuentra en el directorio de trabajo actual (el directorio desde el que se invoca al compilador) o en el directorio del sistema de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="ddefc-107">A directory for the compiler to look in if a referenced assembly is not found in the current working directory (the directory from which you are invoking the compiler) or in the common language runtime's system directory.</span></span>  
  
 `dir2`  
 <span data-ttu-id="ddefc-108">Uno o varios directorios adicionales para buscar las referencias a ensamblados.</span><span class="sxs-lookup"><span data-stu-id="ddefc-108">One or more additional directories to search in for assembly references.</span></span> <span data-ttu-id="ddefc-109">Separe los nombres de directorio adicionales con una coma y sin espacio en blanco entre ellos.</span><span class="sxs-lookup"><span data-stu-id="ddefc-109">Separate additional directory names with a comma, and without white space between them.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ddefc-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ddefc-110">Remarks</span></span>  
 <span data-ttu-id="ddefc-111">El compilador busca referencias a ensamblados que no presentan la ruta completa en el siguiente orden:</span><span class="sxs-lookup"><span data-stu-id="ddefc-111">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1. <span data-ttu-id="ddefc-112">Directorio de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="ddefc-112">Current working directory.</span></span> <span data-ttu-id="ddefc-113">Es el directorio desde donde se invoca al compilador.</span><span class="sxs-lookup"><span data-stu-id="ddefc-113">This is the directory from which the compiler is invoked.</span></span>  
  
2. <span data-ttu-id="ddefc-114">El directorio del sistema de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="ddefc-114">The common language runtime system directory.</span></span>  
  
3. <span data-ttu-id="ddefc-115">Directorios especificados por **-lib**.</span><span class="sxs-lookup"><span data-stu-id="ddefc-115">Directories specified by **-lib**.</span></span>  
  
4. <span data-ttu-id="ddefc-116">Directorios especificados por la variable de entorno LIB.</span><span class="sxs-lookup"><span data-stu-id="ddefc-116">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="ddefc-117">Use **-reference** para especificar una referencia a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ddefc-117">Use **-reference** to specify an assembly reference.</span></span>  
  
 <span data-ttu-id="ddefc-118">La opción **-lib** es sumatoria; si se especifica más de una vez, se anexa a valores ya existentes.</span><span class="sxs-lookup"><span data-stu-id="ddefc-118">**-lib** is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="ddefc-119">Una alternativa al uso de **-lib** consiste en copiar los ensamblados necesarios en el directorio de trabajo; esto permitirá pasar el nombre del ensamblado a **-reference**.</span><span class="sxs-lookup"><span data-stu-id="ddefc-119">An alternative to using **-lib** is to copy into the working directory any required assemblies; this will allow you to simply pass the assembly name to **-reference**.</span></span> <span data-ttu-id="ddefc-120">Después, se pueden eliminar los ensamblados del directorio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ddefc-120">You can then delete the assemblies from the working directory.</span></span> <span data-ttu-id="ddefc-121">Dado que en el manifiesto del ensamblado no se especifica la ruta al ensamblado dependiente, la aplicación puede iniciarse en el equipo de destino y desde allí buscará y usará el ensamblado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="ddefc-121">Since the path to the dependent assembly is not specified in the assembly manifest, the application can be started on the target computer and will find and use the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="ddefc-122">El hecho de que el compilador puede hacer referencia al ensamblado no implica que Common Language Runtime pueda buscar y cargar el ensamblado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ddefc-122">Because the compiler can reference the assembly does not imply the common language runtime will be able to find and load the assembly at runtime.</span></span> <span data-ttu-id="ddefc-123">Vea [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../framework/deployment/how-the-runtime-locates-assemblies.md) para obtener los detalles sobre cómo busca el motor en tiempo de ejecución los ensamblados a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="ddefc-123">See [How the Runtime Locates Assemblies](../../../framework/deployment/how-the-runtime-locates-assemblies.md) for details on how the runtime searches for referenced assemblies.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="ddefc-124">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ddefc-124">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="ddefc-125">Abra el cuadro de diálogo **Páginas de propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="ddefc-125">Open the project's **Property Pages** dialog box.</span></span>  
  
2. <span data-ttu-id="ddefc-126">Haga clic en la página de propiedades **Ruta de acceso de referencias**.</span><span class="sxs-lookup"><span data-stu-id="ddefc-126">Click the **References Path** property page.</span></span>  
  
3. <span data-ttu-id="ddefc-127">Modifique el contenido del cuadro de lista.</span><span class="sxs-lookup"><span data-stu-id="ddefc-127">Modify the contents of the list box.</span></span>  
  
 <span data-ttu-id="ddefc-128">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.ReferencePath%2A>.</span><span class="sxs-lookup"><span data-stu-id="ddefc-128">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.ReferencePath%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ddefc-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ddefc-129">Example</span></span>  
 <span data-ttu-id="ddefc-130">Compile t2.cs para crear un archivo .exe.</span><span class="sxs-lookup"><span data-stu-id="ddefc-130">Compile t2.cs to create an .exe file.</span></span> <span data-ttu-id="ddefc-131">El compilador buscará referencias a ensamblados en el directorio de trabajo y en el directorio raíz de la unidad C.</span><span class="sxs-lookup"><span data-stu-id="ddefc-131">The compiler will look in the working directory and in the root directory of the C drive for assembly references.</span></span>  
  
```console  
csc -lib:c:\ -reference:t2.dll t2.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="ddefc-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="ddefc-132">See also</span></span>

- [<span data-ttu-id="ddefc-133">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="ddefc-133">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="ddefc-134">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="ddefc-134">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

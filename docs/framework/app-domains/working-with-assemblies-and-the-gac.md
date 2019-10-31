---
title: Trabajar con ensamblados y la memoria caché global de ensamblados
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- global assembly cache, benefits
- ACLs [.NET Framework]
- GAC (global assembly cache), benefits
- access control lists [.NET Framework]
ms.assetid: 8a18e5c2-d41d-49ef-abcb-7c27e2469433
ms.openlocfilehash: 330555f907a5ee2ef9cfc11b0b5659a392c0dec7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119716"
---
# <a name="working-with-assemblies-and-the-global-assembly-cache"></a><span data-ttu-id="aba30-102">Trabajar con ensamblados y la memoria caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="aba30-102">Working with Assemblies and the Global Assembly Cache</span></span>

<span data-ttu-id="aba30-103">Si se piensa compartir un ensamblado entre varias aplicaciones, puede instalarlo en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="aba30-103">If you intend to share an assembly among several applications, you can install it into the global assembly cache.</span></span> <span data-ttu-id="aba30-104">Cada equipo tiene esta memoria caché de código donde se instala Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="aba30-104">Each computer where the common language runtime is installed has this machine-wide code cache.</span></span> <span data-ttu-id="aba30-105">La caché global de ensamblados almacena los ensamblados designados específicamente para ser compartidos por varias aplicaciones del equipo.</span><span class="sxs-lookup"><span data-stu-id="aba30-105">The global assembly cache stores assemblies specifically designated to be shared by several applications on the computer.</span></span> <span data-ttu-id="aba30-106">Un ensamblado debe tener un nombre seguro para que se pueda instalar en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="aba30-106">An assembly must have a strong name to be installed in the global assembly cache.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aba30-107">Los ensamblados ubicados en la caché global de ensamblados deben tener el mismo nombre de ensamblado y de archivo, sin contar la extensión de nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="aba30-107">Assemblies placed in the global assembly cache must have the same assembly name and file name (not including the file name extension).</span></span> <span data-ttu-id="aba30-108">Por ejemplo, un ensamblado con el nombre de ensamblado myAssembly debe tener un nombre de archivo myAssembly.exe o myAssembly.dll.</span><span class="sxs-lookup"><span data-stu-id="aba30-108">For example, an assembly with the assembly name of myAssembly must have a file name of either myAssembly.exe or myAssembly.dll.</span></span>  
  
<span data-ttu-id="aba30-109">Se recomienda compartir los ensamblados mediante su instalación en la caché global de ensamblados sólo cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="aba30-109">You should share assemblies by installing them into the global assembly cache only when necessary.</span></span> <span data-ttu-id="aba30-110">Como norma general, mantenga las dependencias de los ensamblados privadas y coloque los ensamblados en el directorio de la aplicación, a menos que sea necesario compartir un ensamblado en concreto.</span><span class="sxs-lookup"><span data-stu-id="aba30-110">As a general guideline, keep assembly dependencies private and locate assemblies in the application directory unless sharing an assembly is explicitly required.</span></span> <span data-ttu-id="aba30-111">Además, no es necesario instalar los ensamblados en la caché global de ensamblados para que pueda tener acceso a ellos el código de interoperabilidad COM o el código no administrado.</span><span class="sxs-lookup"><span data-stu-id="aba30-111">In addition, you do not have to install assemblies into the global assembly cache to make them accessible to COM interop or unmanaged code.</span></span>  
  
<span data-ttu-id="aba30-112">Existen varias razones para instalar un ensamblado en la caché global de ensamblados:</span><span class="sxs-lookup"><span data-stu-id="aba30-112">There are several reasons why you might want to install an assembly into the global assembly cache:</span></span>  
  
- <span data-ttu-id="aba30-113">Ubicación compartida.</span><span class="sxs-lookup"><span data-stu-id="aba30-113">Shared location.</span></span>  
  
     <span data-ttu-id="aba30-114">Los ensamblados que van a usar las aplicaciones se pueden poner en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="aba30-114">Assemblies that should be used by applications can be put in the global assembly cache.</span></span> <span data-ttu-id="aba30-115">Por ejemplo, si todas las aplicaciones deben usar un ensamblado ubicado en la caché global de ensamblados, se puede agregar una instrucción de directiva de versión al archivo Machine.config que redirige las referencias al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="aba30-115">For example, if all applications should use an assembly located in the global assembly cache, a version policy statement can be added to the Machine.config file that redirects references to the assembly.</span></span>  
  
- <span data-ttu-id="aba30-116">Seguridad de archivos.</span><span class="sxs-lookup"><span data-stu-id="aba30-116">File security.</span></span>  
  
     <span data-ttu-id="aba30-117">Con frecuencia, los administradores protegen el directorio systemroot con una Lista de control de acceso (ACL) para controlar el acceso de escritura y ejecución.</span><span class="sxs-lookup"><span data-stu-id="aba30-117">Administrators often protect the systemroot directory using an Access Control List (ACL) to control write and execute access.</span></span> <span data-ttu-id="aba30-118">Puesto que la caché global de ensamblados está instalada en el directorio systemroot, hereda la lista (ACL) de dicho directorio.</span><span class="sxs-lookup"><span data-stu-id="aba30-118">Because the global assembly cache is installed in the systemroot directory, it inherits that directory's ACL.</span></span> <span data-ttu-id="aba30-119">Es recomendable que sólo puedan eliminar archivos de la caché global de ensamblados los usuarios que tengan privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="aba30-119">It is recommended that only users with Administrator privileges be allowed to delete files from the global assembly cache.</span></span>  
  
- <span data-ttu-id="aba30-120">Control de versiones en paralelo.</span><span class="sxs-lookup"><span data-stu-id="aba30-120">Side-by-side versioning.</span></span>  
  
     <span data-ttu-id="aba30-121">En la caché global de ensamblados se pueden guardar muchas copias de ensamblados con el mismo nombre pero con distinta información de versión.</span><span class="sxs-lookup"><span data-stu-id="aba30-121">Multiple copies of assemblies with the same name but different version information can be maintained in the global assembly cache.</span></span>  
  
- <span data-ttu-id="aba30-122">Ubicación de búsqueda adicional.</span><span class="sxs-lookup"><span data-stu-id="aba30-122">Additional search location.</span></span>  
  
     <span data-ttu-id="aba30-123">Common Language Runtime busca en la caché global de ensamblados un ensamblado que coincida con la solicitud de ensamblado antes de buscar o utilizar la información de código base en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="aba30-123">The common language runtime checks the global assembly cache for an assembly that matches the assembly request before probing or using the codebase information in a configuration file.</span></span>  
  
 <span data-ttu-id="aba30-124">Tenga en cuenta que hay escenarios en los que no deseará instalar un ensamblado en la memoria caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="aba30-124">Note that there are scenarios where you explicitly do not want to install an assembly into the global assembly cache.</span></span> <span data-ttu-id="aba30-125">Si coloca uno de los ensamblados que componen una aplicación en la memoria caché global de ensamblados, ya no podrá replicar ni instalar la aplicación utilizando XCOPY para copiar el directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="aba30-125">If you place one of the assemblies that make up an application into the global assembly cache, you can no longer replicate or install the application by using XCOPY to copy the application directory.</span></span> <span data-ttu-id="aba30-126">En este caso, debe mover también el ensamblado a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="aba30-126">In this case, you must also move the assembly into the global assembly cache.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aba30-127">En esta sección</span><span class="sxs-lookup"><span data-stu-id="aba30-127">In This Section</span></span>  
[<span data-ttu-id="aba30-128">Instalar un ensamblado en la memoria caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="aba30-128">How to: Install an Assembly into the Global Assembly Cache</span></span>](install-assembly-into-gac.md)  
<span data-ttu-id="aba30-129">Describe las formas de instalar un ensamblado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="aba30-129">Describes the ways to install an assembly into the global assembly cache.</span></span>  
  
[<span data-ttu-id="aba30-130">Consultar el contenido de la memoria caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="aba30-130">How to: View the Contents of the Global Assembly Cache</span></span>](how-to-view-the-contents-of-the-gac.md)  
<span data-ttu-id="aba30-131">Explica cómo usar [Gacutil.exe (herramienta Caché global de ensamblados)](../tools/gacutil-exe-gac-tool.md) para ver el contenido de la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="aba30-131">Explains how to use the [Gacutil.exe (Global Assembly Cache Tool)](../tools/gacutil-exe-gac-tool.md) to view the contents of the global assembly cache.</span></span>  
  
[<span data-ttu-id="aba30-132">Quitar un ensamblado de la memoria caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="aba30-132">How to: Remove an Assembly from the Global Assembly Cache</span></span>](how-to-remove-an-assembly-from-the-gac.md)  
<span data-ttu-id="aba30-133">Explica cómo usar [Gacutil.exe (herramienta Caché global de ensamblados)](../tools/gacutil-exe-gac-tool.md) para quitar un ensamblado de la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="aba30-133">Explains how to use the [Gacutil.exe (Global Assembly Cache Tool)](../tools/gacutil-exe-gac-tool.md) to remove an assembly from the global assembly cache.</span></span>  
  
[<span data-ttu-id="aba30-134">Utilizar componentes con servicio junto con la memoria caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="aba30-134">Using Serviced Components with the Global Assembly Cache</span></span>](use-serviced-components-with-the-gac.md)  
<span data-ttu-id="aba30-135">Explica por qué se deben colocar los componentes con servicio (componentes COM+ administrados) en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="aba30-135">Explains why serviced components (managed COM+ components) should be placed in the global assembly cache.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="aba30-136">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="aba30-136">Related Sections</span></span>  

[<span data-ttu-id="aba30-137">Creación de ensamblados</span><span class="sxs-lookup"><span data-stu-id="aba30-137">Creating Assemblies</span></span>](../../standard/assembly/create.md)  
<span data-ttu-id="aba30-138">Proporciona información general sobre la creación de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="aba30-138">Provides an overview of creating assemblies.</span></span>  
  
[<span data-ttu-id="aba30-139">Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="aba30-139">Global Assembly Cache</span></span>](gac.md)  
<span data-ttu-id="aba30-140">Describe la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="aba30-140">Describes the global assembly cache.</span></span>  
  
[<span data-ttu-id="aba30-141">Ver el contenido de un ensamblado</span><span class="sxs-lookup"><span data-stu-id="aba30-141">How to: View Assembly Contents</span></span>](../../standard/assembly/view-contents.md)  
<span data-ttu-id="aba30-142">Explica cómo usar [Ildasm.exe (Desensamblador de IL)](../tools/ildasm-exe-il-disassembler.md) para ver la información del Lenguaje intermedio de Microsoft (MSIL) de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="aba30-142">Explains how to use the [Ildasm.exe (IL Disassembler)](../tools/ildasm-exe-il-disassembler.md) to view Microsoft intermediate language (MSIL) information in an assembly.</span></span>  
  
[<span data-ttu-id="aba30-143">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="aba30-143">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)  
<span data-ttu-id="aba30-144">Describe cómo Common Language Runtime busca y carga los ensamblados que conforman la aplicación.</span><span class="sxs-lookup"><span data-stu-id="aba30-144">Describes how the common language runtime locates and loads the assemblies that make up your application.</span></span>  
  
[<span data-ttu-id="aba30-145">Programar con ensamblados</span><span class="sxs-lookup"><span data-stu-id="aba30-145">Programming with Assemblies</span></span>](../../standard/assembly/program.md)  
<span data-ttu-id="aba30-146">Describe los ensamblados, los bloques de creación de las aplicaciones administradas.</span><span class="sxs-lookup"><span data-stu-id="aba30-146">Describes assemblies, the building blocks of managed applications.</span></span>

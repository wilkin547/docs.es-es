---
title: "Caché global de ensamblados"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- GAC (global assembly cache)
- ACLs [.NET Framework]
- global assembly cache
- cache [.NET Framework], global assembly cache
- global assembly cache, about
- access control lists [.NET Framework]
ms.assetid: cf5eacd0-d3ec-4879-b6da-5fd5e4372202
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9ca51a06e6e7ec89576facf3a70c789325fd893c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="global-assembly-cache"></a><span data-ttu-id="3de98-102">Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="3de98-102">Global Assembly Cache</span></span>
<span data-ttu-id="3de98-103">Cada equipo donde se instala Common Language Runtime tiene una memoria caché de código denominada caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3de98-103">Each computer where the common language runtime is installed has a machine-wide code cache called the global assembly cache.</span></span> <span data-ttu-id="3de98-104">La caché global de ensamblados almacena los ensamblados designados específicamente para ser compartidos por varias aplicaciones del equipo.</span><span class="sxs-lookup"><span data-stu-id="3de98-104">The global assembly cache stores assemblies specifically designated to be shared by several applications on the computer.</span></span>  
  
 <span data-ttu-id="3de98-105">Se recomienda compartir los ensamblados mediante su instalación en la caché global de ensamblados sólo cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="3de98-105">You should share assemblies by installing them into the global assembly cache only when you need to.</span></span> <span data-ttu-id="3de98-106">Como norma general, mantenga las dependencias de los ensamblados privadas y coloque los ensamblados en el directorio de la aplicación, a menos que sea explícitamente necesario compartir un ensamblado en concreto.</span><span class="sxs-lookup"><span data-stu-id="3de98-106">As a general guideline, keep assembly dependencies private, and locate assemblies in the application directory unless sharing an assembly is explicitly required.</span></span> <span data-ttu-id="3de98-107">Además, no es necesario instalar los ensamblados en la caché global de ensamblados para que obtenga acceso a ellos el código de interoperabilidad COM o el código no administrado.</span><span class="sxs-lookup"><span data-stu-id="3de98-107">In addition, it is not necessary to install assemblies into the global assembly cache to make them accessible to COM interop or unmanaged code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3de98-108">Habrá algunos escenarios en los que no desee instalar un ensamblado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3de98-108">There are scenarios where you explicitly do not want to install an assembly into the global assembly cache.</span></span> <span data-ttu-id="3de98-109">Si coloca uno de los ensamblados que componen una aplicación en la caché global de ensamblados, no podrá replicar ni instalar la aplicación mediante el comando **xcopy** para copiar el directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3de98-109">If you place one of the assemblies that make up an application in the global assembly cache, you can no longer replicate or install the application by using the **xcopy** command to copy the application directory.</span></span> <span data-ttu-id="3de98-110">También debe mover el ensamblado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3de98-110">You must move the assembly in the global assembly cache as well.</span></span>  
  
 <span data-ttu-id="3de98-111">Existen dos formas de implementar un ensamblado en la memoria caché global de ensamblados:</span><span class="sxs-lookup"><span data-stu-id="3de98-111">There are two ways to deploy an assembly into the global assembly cache:</span></span>  
  
-   <span data-ttu-id="3de98-112">Usar un instalador diseñado para funcionar con la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3de98-112">Use an installer designed to work with the global assembly cache.</span></span> <span data-ttu-id="3de98-113">Es la opción preferida para instalar ensamblados en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3de98-113">This is the preferred option for installing assemblies into the global assembly cache.</span></span>  
  
-   <span data-ttu-id="3de98-114">Use la herramienta de desarrollador [Caché global de ensamblados (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md), que se suministra con [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de98-114">Use a developer tool called the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md), provided by the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3de98-115">En escenarios de implementación, se recomienda utilizar Windows Installer para instalar los ensamblados en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3de98-115">In deployment scenarios, use Windows Installer to install assemblies into the global assembly cache.</span></span> <span data-ttu-id="3de98-116">Utilice la herramienta Caché global de ensamblados solo en escenarios de desarrollo, porque no proporciona funciones de recuento de referencias de ensamblados y otras características que se incluyen con Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="3de98-116">Use the Global Assembly Cache tool only in development scenarios, because it does not provide assembly reference counting and other features provided when using the Windows Installer.</span></span>  
  
 <span data-ttu-id="3de98-117">A partir de .NET Framework 4, la ubicación predeterminada de la caché global de ensamblados es **%windir%\Microsoft.NET\assembly**.</span><span class="sxs-lookup"><span data-stu-id="3de98-117">Starting with the .NET Framework 4, the default location for the global assembly cache is **%windir%\Microsoft.NET\assembly**.</span></span> <span data-ttu-id="3de98-118">En versiones anteriores de .NET Framework, la ubicación predeterminada es **%windir%\assembly**.</span><span class="sxs-lookup"><span data-stu-id="3de98-118">In earlier versions of the .NET Framework, the default location is **%windir%\assembly**.</span></span>  
  
 <span data-ttu-id="3de98-119">Con frecuencia, los administradores protegen el directorio systemroot con una lista de control de acceso (ACL) para controlar el acceso de escritura y ejecución.</span><span class="sxs-lookup"><span data-stu-id="3de98-119">Administrators often protect the systemroot directory using an access control list (ACL) to control write and execute access.</span></span> <span data-ttu-id="3de98-120">Puesto que la caché global de ensamblados está instalada en un subdirectorio del directorio systemroot, hereda la lista (ACL) de dicho directorio.</span><span class="sxs-lookup"><span data-stu-id="3de98-120">Because the global assembly cache is installed in a subdirectory of the systemroot directory, it inherits that directory's ACL.</span></span> <span data-ttu-id="3de98-121">Es recomendable que sólo puedan eliminar archivos de la caché global de ensamblados los usuarios que tengan privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="3de98-121">It is recommended that only users with Administrator privileges be allowed to delete files from the global assembly cache.</span></span>  
  
 <span data-ttu-id="3de98-122">Los ensamblados implementados en la caché global de ensamblados deben tener nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="3de98-122">Assemblies deployed in the global assembly cache must have a strong name.</span></span> <span data-ttu-id="3de98-123">Cuando se agrega un ensamblado a la caché global de ensamblados, se realizan comprobaciones de integridad de todos los archivos que componen el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3de98-123">When an assembly is added to the global assembly cache, integrity checks are performed on all files that make up the assembly.</span></span> <span data-ttu-id="3de98-124">La caché realiza estas comprobaciones de integridad para garantizar que no se ha manipulado ningún ensamblado, por ejemplo, cuando se ha modificado un archivo pero el manifiesto no refleja el cambio.</span><span class="sxs-lookup"><span data-stu-id="3de98-124">The cache performs these integrity checks to ensure that an assembly has not been tampered with, for example, when a file has changed but the manifest does not reflect the change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3de98-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="3de98-125">See Also</span></span>  
 [<span data-ttu-id="3de98-126">Ensamblados en Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="3de98-126">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 [<span data-ttu-id="3de98-127">Trabajar con ensamblados y la memoria caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="3de98-127">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [<span data-ttu-id="3de98-128">Ensamblados con nombre seguro</span><span class="sxs-lookup"><span data-stu-id="3de98-128">Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/strong-named-assemblies.md)

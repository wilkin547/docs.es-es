---
title: "Cómo: Instalar un ensamblado en la memoria caché global de ensamblados"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
caps.latest.revision: 24
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c1a0eb5034c10b84b02f493cd21bccd121c8315c
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a><span data-ttu-id="82518-102">Cómo: Instalar un ensamblado en la memoria caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="82518-102">How to: Install an Assembly into the Global Assembly Cache</span></span>
<span data-ttu-id="82518-103">Hay dos formas de instalar un ensamblado con nombre seguro en la memoria caché global de ensamblados (GAC):</span><span class="sxs-lookup"><span data-stu-id="82518-103">There are two ways to install a strong-named assembly into the global assembly cache (GAC):</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="82518-104">En la memoria caché global de ensamblados solamente se pueden instalar ensamblados con nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="82518-104">Only strong-named assemblies can be installed into the GAC.</span></span> <span data-ttu-id="82518-105">Para obtener información sobre cómo crear un ensamblado con nombre seguro, vea [How to: Sign an Assembly with a Strong Name](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md) (Cómo: Firmar un ensamblado con un nombre seguro).</span><span class="sxs-lookup"><span data-stu-id="82518-105">For information about how to create a strong-named assembly, see [How to: Sign an Assembly with a Strong Name](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
-   <span data-ttu-id="82518-106">Con [Windows Installer](http://msdn.microsoft.com/library/windows/desktop/cc185688.aspx).</span><span class="sxs-lookup"><span data-stu-id="82518-106">Using [Windows Installer](http://msdn.microsoft.com/library/windows/desktop/cc185688.aspx).</span></span>  
  
     <span data-ttu-id="82518-107">Esto se hace en Visual Studio 2012 y Visual Studio 2013 mediante la creación de un proyecto de InstallShield Limited Edition.</span><span class="sxs-lookup"><span data-stu-id="82518-107">You do this in Visual Studio 2012 and Visual Studio 2013 by creating an InstallShield Limited Edition Project.</span></span>  
  
     <span data-ttu-id="82518-108">Esta es la forma recomendada y más normal de agregar ensamblados a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="82518-108">This is the recommended and most common way to add assemblies to the global assembly cache.</span></span> <span data-ttu-id="82518-109">El instalador proporciona el recuento de referencias de los ensamblados de la caché global de ensamblados, además de otras ventajas.</span><span class="sxs-lookup"><span data-stu-id="82518-109">The installer provides reference counting of assemblies in the global assembly cache, plus other benefits.</span></span>  
  
-   <span data-ttu-id="82518-110">Con la [herramienta Caché global de ensamblados (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md).</span><span class="sxs-lookup"><span data-stu-id="82518-110">Using the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md).</span></span>  
  
     <span data-ttu-id="82518-111">Gacutil.exe se puede utilizar para agregar ensamblados con nombre seguro a la caché global de ensamblados y ver el contenido de dicha caché.</span><span class="sxs-lookup"><span data-stu-id="82518-111">You can use Gacutil.exe to add strong-named assemblies to the global assembly cache and to view the contents of the global assembly cache.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="82518-112">Gacutil.exe sólo debe usarse para programación y no para instalar ensamblados de producción en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="82518-112">Gacutil.exe is only for development purposes and should not be used to install production assemblies into the global assembly cache.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82518-113">En versiones anteriores de .NET Framework, la extensión Shfusion.dll del shell de Windows le permitía instalar ensamblados arrastrándolos en el Explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="82518-113">In earlier versions of the .NET Framework, the Shfusion.dll Windows shell extension enabled you to install assemblies by dragging them in File Explorer.</span></span> <span data-ttu-id="82518-114">A partir de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="82518-114">Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll is obsolete.</span></span>  
  
### <a name="to-use-the-global-assembly-cache-tool-gacutilexe"></a><span data-ttu-id="82518-115">Para usar la herramienta Caché global de ensamblados (Gacutil.exe)</span><span class="sxs-lookup"><span data-stu-id="82518-115">To use the Global Assembly Cache tool (Gacutil.exe)</span></span>  
  
1.  <span data-ttu-id="82518-116">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="82518-116">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="82518-117">**gacutil -i** \<*nombre del ensamblado*></span><span class="sxs-lookup"><span data-stu-id="82518-117">**gacutil -i** \<*assembly name*></span></span>  
  
     <span data-ttu-id="82518-118">En este comando, *nombre del ensamblado* es el nombre del ensamblado que se va a instalar en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="82518-118">In this command, *assembly name* is the name of the assembly to install in the global assembly cache.</span></span>  
  
 <span data-ttu-id="82518-119">En el ejemplo siguiente se instala un ensamblado con el nombre de archivo `hello.dll` en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="82518-119">The following example installs an assembly with the file name `hello.dll` into the global assembly cache.</span></span>  
  
```  
gacutil -i hello.dll  
```  
  
 <span data-ttu-id="82518-120">Para obtener más información, vea [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) (Herramienta Caché global de ensamblados (Gacutil.exe)).</span><span class="sxs-lookup"><span data-stu-id="82518-120">For more information, see [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md).</span></span>  
  
### <a name="to-use-an-installshield-limited-edition-project"></a><span data-ttu-id="82518-121">Para usar un proyecto InstallShield Limited Edition</span><span class="sxs-lookup"><span data-stu-id="82518-121">To use an InstallShield Limited Edition Project</span></span>  
  
1.  <span data-ttu-id="82518-122">Agregue un paquete de instalación e implementación a la solución. Para ello, abra el menú contextual de la solución y, después, elija **Agregar**, **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="82518-122">Add a setup and deployment package to your solution by opening the shortcut menu for your solution, and then choosing **Add**, **New Project**.</span></span>  
  
2.  <span data-ttu-id="82518-123">En la carpeta **Instalado** del cuadro de diálogo **Agregar nuevo proyecto**, elija **Otros tipos de proyectos**, **Instalación e implementación** e **InstallShield Limited Edition** y asigne un nombre al proyecto.</span><span class="sxs-lookup"><span data-stu-id="82518-123">In the **Add New Project** dialog box, in the **Installed** folder, choose **Other Project Types**,  **Setup and Deployment**, **InstallShield Limited Edition**, and give your project a name.</span></span> <span data-ttu-id="82518-124">(En caso necesario, descargue, instale y active InstallShield).</span><span class="sxs-lookup"><span data-stu-id="82518-124">(If prompted, download, install, and activate InstallShield.)</span></span>  
  
3.  <span data-ttu-id="82518-125">Aplique la configuración general del proyecto de instalación e implementación mediante el asistente para proyectos del **Explorador de soluciones** o los pasos secundarios de los pasos numerados en el **Explorador de soluciones**. Configure su instalación como si no fuese a agregar ensamblados a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="82518-125">Perform the general configuration of your setup and deployment project either by using the Project Assistant in **Solution Explorer**, or by choosing the substeps of the numbered steps in the **Solution Explorer**.Configure your setup as you would if you were not adding assemblies to the GAC.</span></span>  
  
4.  <span data-ttu-id="82518-126">Para iniciar el proceso de adición de un ensamblado a la caché global de ensamblados, elija **Archivos**, bajo el paso **Specify Application Data** (Especificar los datos de la aplicación) en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="82518-126">To begin the process of adding an assembly to the GAC, choose **Files**, which is under the **Specify Application Data** step in **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="82518-127">En el panel **Destination computer's folders** (Carpetas del equipo de destino), abra el menú contextual de **Equipo de destino** y seleccione **Show Predefined Folder** (Mostrar carpeta predefinida), **[GlobalAssemblyCache]**.</span><span class="sxs-lookup"><span data-stu-id="82518-127">In the **Destination computer's folders** pane, open the shortcut menu for **Destination Computer**, and then choose **Show Predefined Folder**, **[GlobalAssemblyCache]**.</span></span>  
  
6.  <span data-ttu-id="82518-128">Para cada proyecto de la solución que contenga un ensamblado que desee instalar en la memoria caché global de ensamblados:</span><span class="sxs-lookup"><span data-stu-id="82518-128">For each project in the solution that contains an assembly that you want to install in the global assembly cache:</span></span>  
  
    1.  <span data-ttu-id="82518-129">En el panel **Source computer's folders** (Carpetas del equipo de origen), elija el proyecto.</span><span class="sxs-lookup"><span data-stu-id="82518-129">In the **Source computer's folders** pane, choose the project.</span></span>  
  
    2.  <span data-ttu-id="82518-130">En el panel **Destination computer's folders** (Carpetas del equipo de destino), elija **[GlobalAssemblyCache]**.</span><span class="sxs-lookup"><span data-stu-id="82518-130">In the **Destination computer's folders** pane, choose **[GlobalAssemblyCache]**.</span></span>  
  
    3.  <span data-ttu-id="82518-131">En el panel **Source computer's files** (Archivos del equipo de origen), elija **Primary output from** (Salida principal de) *<nombre_proyecto>*.</span><span class="sxs-lookup"><span data-stu-id="82518-131">In the **Source computer's files** pane, choose **Primary output from** *<project_name>*.</span></span>  
  
    4.  <span data-ttu-id="82518-132">Arrastre el archivo del paso c al panel **Destination computer's files** (Archivos del equipo de destino) (o use los comandos **Copiar** y **Pegar** del menú contextual del archivo).</span><span class="sxs-lookup"><span data-stu-id="82518-132">Drag the file in step c to the **Destination computer's files** pane (or use the **Copy** and **Paste** commands from the file's shortcut menu).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82518-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="82518-133">See Also</span></span>  
 <span data-ttu-id="82518-134">[Trabajar con ensamblados y la memoria caché global de ensamblados](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md) </span><span class="sxs-lookup"><span data-stu-id="82518-134">[Working with Assemblies and the Global Assembly Cache](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md) </span></span>  
 <span data-ttu-id="82518-135">[Cómo: Quitar un ensamblado de la caché global de ensamblados](../../../docs/framework/app-domains/how-to-remove-an-assembly-from-the-gac.md) </span><span class="sxs-lookup"><span data-stu-id="82518-135">[How to: Remove an Assembly from the Global Assembly Cache](../../../docs/framework/app-domains/how-to-remove-an-assembly-from-the-gac.md) </span></span>  
 <span data-ttu-id="82518-136">[Gacutil.exe (Herramienta Caché global de ensamblados)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) </span><span class="sxs-lookup"><span data-stu-id="82518-136">[Gacutil.exe (Global Assembly Cache Tool)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) </span></span>  
 <span data-ttu-id="82518-137">[Cómo: Firmar un ensamblado con un nombre seguro](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md) </span><span class="sxs-lookup"><span data-stu-id="82518-137">[How to: Sign an Assembly with a Strong Name](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md) </span></span>  
 [<span data-ttu-id="82518-138">Implementación de Windows Installer</span><span class="sxs-lookup"><span data-stu-id="82518-138">Windows Installer Deployment</span></span>](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0)


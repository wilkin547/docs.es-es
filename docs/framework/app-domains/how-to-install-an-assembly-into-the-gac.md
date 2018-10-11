---
title: Instalación de un ensamblado en la caché global de ensamblados
ms.date: 09/20/2018
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
- windows installer, global assembly cache
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d365ac77fe6cd7fc4fca36705729ec12b06d6830
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2018
ms.locfileid: "46584586"
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a><span data-ttu-id="cb90f-102">Instalación de un ensamblado en la caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="cb90f-102">How to: Install an assembly into the global assembly cache</span></span>

<span data-ttu-id="cb90f-103">Hay dos formas de instalar un ensamblado con nombre seguro en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="cb90f-103">There are two ways to install a strong-named assembly into the global assembly cache (GAC).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb90f-104">En la memoria caché global de ensamblados solamente se pueden instalar ensamblados con nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="cb90f-104">Only strong-named assemblies can be installed into the GAC.</span></span> <span data-ttu-id="cb90f-105">Para obtener información sobre cómo crear un ensamblado con nombre seguro, vea [How to: Sign an Assembly with a Strong Name](how-to-sign-an-assembly-with-a-strong-name.md) (Cómo: Firmar un ensamblado con un nombre seguro).</span><span class="sxs-lookup"><span data-stu-id="cb90f-105">For information about how to create a strong-named assembly, see [How to: Sign an Assembly with a Strong Name](how-to-sign-an-assembly-with-a-strong-name.md).</span></span>

## <a name="windows-installer"></a><span data-ttu-id="cb90f-106">Windows Installer</span><span class="sxs-lookup"><span data-stu-id="cb90f-106">Windows Installer</span></span>

<span data-ttu-id="cb90f-107">[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), el motor de instalación de Windows, es la manera recomendada para agregar ensamblados a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="cb90f-107">[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), the Windows installation engine, is the recommended way to add assemblies to the global assembly cache.</span></span> <span data-ttu-id="cb90f-108">Windows Installer proporciona el recuento de referencias de los ensamblados de la caché global de ensamblados, además de otras ventajas.</span><span class="sxs-lookup"><span data-stu-id="cb90f-108">Windows Installer provides reference counting of assemblies in the global assembly cache and other benefits.</span></span> <span data-ttu-id="cb90f-109">Puede usar la [extensión del conjunto de herramientas de WiX para Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension) para crear un paquete de instalación para Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="cb90f-109">You can use the [WiX Toolset extension for Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension) to create an installer package for Windows Installer.</span></span>

## <a name="global-assembly-cache-tool"></a><span data-ttu-id="cb90f-110">Herramienta de caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="cb90f-110">Global assembly cache tool</span></span>

<span data-ttu-id="cb90f-111">Puede usar la [herramienta de caché global de ensamblados (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) para agregar ensamblados con nombre seguro a la caché global de ensamblados y ver el contenido de dicha caché.</span><span class="sxs-lookup"><span data-stu-id="cb90f-111">You can use the [Global assembly cache tool (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to add strong-named assemblies to the global assembly cache and to view the contents of the global assembly cache.</span></span>

   > [!NOTE]
   > <span data-ttu-id="cb90f-112">Gacutil.exe sólo debe usarse para programación y no para instalar ensamblados de producción en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="cb90f-112">Gacutil.exe is only for development purposes and should not be used to install production assemblies into the global assembly cache.</span></span>

<span data-ttu-id="cb90f-113">La sintaxis de gacutil es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="cb90f-113">The syntax for gacutil is as follows:</span></span>

```shell
gacutil -i <assembly name>
```

<span data-ttu-id="cb90f-114">En este comando, *nombre del ensamblado* es el nombre del ensamblado que se va a instalar en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="cb90f-114">In this command, *assembly name* is the name of the assembly to install in the global assembly cache.</span></span>

<span data-ttu-id="cb90f-115">En el ejemplo siguiente se instala un ensamblado con el nombre de archivo `hello.dll` en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="cb90f-115">The following example installs an assembly with the file name `hello.dll` into the global assembly cache.</span></span>

```shell
gacutil -i hello.dll
```

> [!NOTE]
> <span data-ttu-id="cb90f-116">En versiones anteriores de .NET Framework, la extensión Shfusion.dll del shell de Windows le permitía instalar ensamblados arrastrándolos en el **Explorador de archivos**.</span><span class="sxs-lookup"><span data-stu-id="cb90f-116">In earlier versions of the .NET Framework, the Shfusion.dll Windows shell extension enabled you to install assemblies by dragging them in **File Explorer**.</span></span> <span data-ttu-id="cb90f-117">A partir de .NET Framework 4, Shfusion.dll está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="cb90f-117">Beginning with the .NET Framework 4, Shfusion.dll is obsolete.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb90f-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb90f-118">See also</span></span>

- [<span data-ttu-id="cb90f-119">Trabajar con ensamblados y la memoria caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="cb90f-119">Working with Assemblies and the Global Assembly Cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="cb90f-120">Quitar un ensamblado de la memoria caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="cb90f-120">How to: Remove an Assembly from the Global Assembly Cache</span></span>](how-to-remove-an-assembly-from-the-gac.md)
- [<span data-ttu-id="cb90f-121">Gacutil.exe (Herramienta Caché global de ensamblados)</span><span class="sxs-lookup"><span data-stu-id="cb90f-121">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
- [<span data-ttu-id="cb90f-122">Cómo: Firmar un ensamblado con un nombre seguro</span><span class="sxs-lookup"><span data-stu-id="cb90f-122">How to: Sign an Assembly with a Strong Name</span></span>](how-to-sign-an-assembly-with-a-strong-name.md)
---
title: Procedimiento para quitar un ensamblado de la memoria caché global de ensamblados
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- global assembly cache, removing assemblies
- strong-named assemblies, global assembly cache
- removing assemblies from global assembly cache
- deleting assemblies in global assembly cache
- Global Assembly Cache tool
- GAC (global assembly cache), removing assemblies
ms.assetid: acdcc588-b458-436d-876c-726de68244c1
ms.openlocfilehash: c7d85222f35a61154e3eec70d8c9dad2ca6a32f3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119851"
---
# <a name="how-to-remove-an-assembly-from-the-global-assembly-cache"></a><span data-ttu-id="3597b-102">Procedimiento para quitar un ensamblado de la memoria caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="3597b-102">How to: Remove an Assembly from the Global Assembly Cache</span></span>

<span data-ttu-id="3597b-103">Hay dos formas de quitar un ensamblado de la caché global de ensamblados (GAC):</span><span class="sxs-lookup"><span data-stu-id="3597b-103">There are two ways to remove an assembly from the global assembly cache (GAC):</span></span>

- <span data-ttu-id="3597b-104">Con la [herramienta Caché global de ensamblados (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md).</span><span class="sxs-lookup"><span data-stu-id="3597b-104">By using the [Global Assembly Cache tool (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md).</span></span> <span data-ttu-id="3597b-105">Puede usar esta opción para desinstalar los ensamblados que haya colocado en la GAC durante el desarrollo y las pruebas.</span><span class="sxs-lookup"><span data-stu-id="3597b-105">You can use this option to uninstall assemblies that you've placed in the GAC during development and testing.</span></span>

- <span data-ttu-id="3597b-106">Con [Windows Installer](/windows/desktop/Msi/windows-installer-portal).</span><span class="sxs-lookup"><span data-stu-id="3597b-106">By using [Windows Installer](/windows/desktop/Msi/windows-installer-portal).</span></span> <span data-ttu-id="3597b-107">Debe usar esta opción para desinstalar ensamblados al probar los paquetes de instalación y en sistemas de producción.</span><span class="sxs-lookup"><span data-stu-id="3597b-107">You should use this option to uninstall assemblies when testing installation packages and for production systems.</span></span>

## <a name="removing-an-assembly-with-gacutilexe"></a><span data-ttu-id="3597b-108">Quitar un ensamblado con Gacutil.exe</span><span class="sxs-lookup"><span data-stu-id="3597b-108">Removing an assembly with Gacutil.exe</span></span>

<span data-ttu-id="3597b-109">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="3597b-109">At the command prompt, type the following command:</span></span>

<span data-ttu-id="3597b-110">**gacutil –u** \<*nombre del ensamblado*></span><span class="sxs-lookup"><span data-stu-id="3597b-110">**gacutil –u** \<*assembly name*></span></span>

<span data-ttu-id="3597b-111">En este comando, *nombre del ensamblado* es el nombre del ensamblado que se va a quitar de la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3597b-111">In this command, *assembly name* is the name of the assembly to remove from the global assembly cache.</span></span>

> [!WARNING]
> <span data-ttu-id="3597b-112">No debe utilizar Gacutil.exe para quitar ensamblados en sistemas de producción porque existe la posibilidad de que alguna aplicación necesite aún el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3597b-112">You should not use Gacutil.exe to remove assemblies on production systems because of the possibility that the assembly may still be required by some application.</span></span> <span data-ttu-id="3597b-113">En su lugar, debe usar el instalador de Windows, que mantiene un recuento de referencias para cada ensamblado que se instala en la GAC.</span><span class="sxs-lookup"><span data-stu-id="3597b-113">Instead, you should use the Windows Installer, which maintains a reference count for each assembly it installs in the GAC.</span></span>

<span data-ttu-id="3597b-114">En el ejemplo siguiente se quita un ensamblado llamado `hello.dll` de la caché global de ensamblados:</span><span class="sxs-lookup"><span data-stu-id="3597b-114">The following example removes an assembly named `hello.dll` from the global assembly cache:</span></span>

```console
gacutil -u hello
```

## <a name="removing-an-assembly-with-windows-installer"></a><span data-ttu-id="3597b-115">Quitar un ensamblado con Windows Installer</span><span class="sxs-lookup"><span data-stu-id="3597b-115">Removing an assembly with Windows Installer</span></span>

<span data-ttu-id="3597b-116">En la aplicación **Programas y características** del **Panel de Control**, seleccione la aplicación que quiere desinstalar.</span><span class="sxs-lookup"><span data-stu-id="3597b-116">From the **Programs and Features** app in **Control Panel**, select the app that you want to uninstall.</span></span> <span data-ttu-id="3597b-117">Si el paquete de instalación colocó ensamblados en la GAC, Windows Installer los quitará si otra aplicación no lo está usando.</span><span class="sxs-lookup"><span data-stu-id="3597b-117">If the installation package placed assemblies in the GAC, Windows Installer will remove them if they are not used by another application.</span></span>

> [!NOTE]
> <span data-ttu-id="3597b-118">Windows Installer mantiene un recuento de referencias para los ensamblados instalados en la GAC.</span><span class="sxs-lookup"><span data-stu-id="3597b-118">Windows Installer maintains a reference count for assemblies installed in the GAC.</span></span> <span data-ttu-id="3597b-119">Un ensamblado se quita de la GAC solo cuando su recuento de referencias llega a cero, lo que indica que no lo está usando ninguna aplicación instalada por un paquete de Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="3597b-119">An assembly is removed from the GAC only when its reference count reaches zero, which indicates that it is not used by any application installed by a Windows Installer package.</span></span>

## <a name="see-also"></a><span data-ttu-id="3597b-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="3597b-120">See also</span></span>

- [<span data-ttu-id="3597b-121">Trabajar con ensamblados y la memoria caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="3597b-121">Working with Assemblies and the Global Assembly Cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="3597b-122">Cómo: Instalar un ensamblado en la caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="3597b-122">How to: Install an Assembly into the Global Assembly Cache</span></span>](install-assembly-into-gac.md)
- [<span data-ttu-id="3597b-123">Gacutil.exe (Herramienta Caché global de ensamblados)</span><span class="sxs-lookup"><span data-stu-id="3597b-123">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)

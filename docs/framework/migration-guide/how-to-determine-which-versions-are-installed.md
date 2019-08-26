---
title: Procedimiento para determinar qué versiones de .NET Framework están instaladas
ms.date: 04/18/2019
dev_langs:
- csharp
- vb
ms.custom: updateeachrelease
helpviewer_keywords:
- versions, determining for .NET Framework
- .NET Framework, determining version
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5ead6db2c3df3662c4d689bd6ac2466c99b02a15
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968258"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a><span data-ttu-id="d4a63-102">Procedimiento para determinar qué versiones de .NET Framework están instaladas</span><span class="sxs-lookup"><span data-stu-id="d4a63-102">How to: Determine which .NET Framework versions are installed</span></span>

<span data-ttu-id="d4a63-103">Los usuarios pueden [instalar](https://docs.microsoft.com/dotnet/framework/install) y ejecutar varias versiones de .NET Framework en sus equipos.</span><span class="sxs-lookup"><span data-stu-id="d4a63-103">Users can [install](https://docs.microsoft.com/dotnet/framework/install) and run multiple versions of the .NET Framework on their computers.</span></span> <span data-ttu-id="d4a63-104">Al desarrollar o implementar una aplicación, puede que necesite conocer las versiones de .NET Framework que están instaladas en el equipo del usuario.</span><span class="sxs-lookup"><span data-stu-id="d4a63-104">When you develop or deploy your app, you might need to know which .NET Framework versions are installed on the user’s computer.</span></span>

<span data-ttu-id="d4a63-105">.NET Framework está formado por dos componentes principales con versiones separadas:</span><span class="sxs-lookup"><span data-stu-id="d4a63-105">The .NET Framework consists of two main components, which are versioned separately:</span></span>

- <span data-ttu-id="d4a63-106">Un conjunto de ensamblados, que son colecciones de tipos y recursos que proporcionan funciones a las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d4a63-106">A set of assemblies, which are collections of types and resources that provide the functionality for your apps.</span></span> <span data-ttu-id="d4a63-107">.NET Framework y los ensamblados comparten el mismo número de versión.</span><span class="sxs-lookup"><span data-stu-id="d4a63-107">The .NET Framework and assemblies share the same version number.</span></span>

- <span data-ttu-id="d4a63-108">Common Language Runtime (CLR), que administra y ejecuta el código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d4a63-108">The common language runtime (CLR), which manages and executes your app's code.</span></span> <span data-ttu-id="d4a63-109">El CLR se identifica mediante su propio número de versión (consulte [Versiones y dependencias](versions-and-dependencies.md)).</span><span class="sxs-lookup"><span data-stu-id="d4a63-109">The CLR is identified by its own version number (see [Versions and Dependencies](versions-and-dependencies.md)).</span></span>

> [!NOTE]
> <span data-ttu-id="d4a63-110">Cada versión de .NET Framework contiene características de versiones anteriores e incorpora nuevas características.</span><span class="sxs-lookup"><span data-stu-id="d4a63-110">Each new version of the .NET Framework retains features from the previous versions and adds new features.</span></span> <span data-ttu-id="d4a63-111">Puede cargar varias versiones de .NET Framework en un equipo al mismo tiempo, lo que significa que puede instalarlo sin tener que eliminar las versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="d4a63-111">You can load multiple versions of the .NET Framework on a single computer at the same time, which means that you can install the .NET Framework without having to uninstall previous versions.</span></span> <span data-ttu-id="d4a63-112">En general, no debe desinstalar ninguna versión anterior de .NET Framework, ya que una determinada aplicación puede depender de una versión concreta y puede dejar de funcionar si se quita esa versión.</span><span class="sxs-lookup"><span data-stu-id="d4a63-112">In general, you shouldn't uninstall previous versions of the .NET Framework, because an application you use may depend on a specific version and may break if that version is removed.</span></span>
>
> <span data-ttu-id="d4a63-113">Hay una diferencia entre la versión de .NET Framework y la versión de CLR:</span><span class="sxs-lookup"><span data-stu-id="d4a63-113">There is a difference between the .NET Framework version and the CLR version:</span></span>
> - <span data-ttu-id="d4a63-114">Las versiones de .NET Framework se basan en el conjunto de ensamblados que conforman la biblioteca de clases .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d4a63-114">The .NET Framework version is based on the set of assemblies that form the .NET Framework class library.</span></span> <span data-ttu-id="d4a63-115">Por ejemplo, las versiones de .NET Framework incluyen 4.5, 4.6.1 y 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="d4a63-115">For example, .NET Framework versions include 4.5, 4.6.1, and 4.7.2.</span></span>
>- <span data-ttu-id="d4a63-116">La versión de CLR se basa en el tiempo de ejecución en el que se ejecutan las aplicaciones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d4a63-116">The CLR version is based on the runtime on which .NET Framework applications execute.</span></span> <span data-ttu-id="d4a63-117">Normalmente, una misma versión de CLR admite varias versiones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d4a63-117">A single CLR version typically supports multiple .NET Framework versions.</span></span> <span data-ttu-id="d4a63-118">Por ejemplo, la versión de CLR 4.0.30319.*xxxxx* admite las versiones de la 4 a la 4.5.2 de .NET Framework; donde *xxxxx* es inferior a 42000, y la versión de CLR 4.0.30319.42000 admite las versiones de .NET Framework a partir de .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="d4a63-118">For example, CLR version 4.0.30319.*xxxxx* supports .NET Framework versions 4 through 4.5.2, where *xxxxx* is less than 42000, and CLR version 4.0.30319.42000 supports .NET Framework versions starting with .NET Framework 4.6.</span></span>
>
> <span data-ttu-id="d4a63-119">Para obtener más información sobre las versiones, vea [Versiones y dependencias de .NET Framework](versions-and-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="d4a63-119">For more information about versions, see [.NET Framework versions and dependencies](versions-and-dependencies.md).</span></span>

<span data-ttu-id="d4a63-120">Para obtener una lista de las versiones de .NET Framework instaladas en un equipo, debe tener acceso al Registro.</span><span class="sxs-lookup"><span data-stu-id="d4a63-120">To get a list of the .NET Framework versions installed on a computer, you access the registry.</span></span> <span data-ttu-id="d4a63-121">Puede usar el Editor del Registro para ver el Registro o usar código para consultarlo:</span><span class="sxs-lookup"><span data-stu-id="d4a63-121">You can either use the Registry Editor to view the registry or use code to query it:</span></span>

- <span data-ttu-id="d4a63-122">Búsqueda de versiones más recientes de .NET Framework (4.5 y versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="d4a63-122">Find newer .NET Framework versions (4.5 and later):</span></span>
  - [<span data-ttu-id="d4a63-123">Uso del Editor del Registro para buscar versiones de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d4a63-123">Use the Registry Editor to find .NET Framework versions</span></span>](#net_b)
  - [<span data-ttu-id="d4a63-124">Uso de código para consultar en el Registro las versiones de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d4a63-124">Use code to query the registry for .NET Framework versions</span></span>](#net_d)
  - [<span data-ttu-id="d4a63-125">Uso de PowerShell para consultar en el Registro las versiones de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d4a63-125">Use PowerShell to query the registry for .NET Framework versions</span></span>](#ps_a)
- <span data-ttu-id="d4a63-126">Búsqueda de versiones más antiguas de .NET Framework (1&#8211;4):</span><span class="sxs-lookup"><span data-stu-id="d4a63-126">Find older .NET Framework versions (1&#8211;4):</span></span>
  - [<span data-ttu-id="d4a63-127">Uso del Editor del Registro para buscar versiones de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d4a63-127">Use the Registry Editor to find .NET Framework versions</span></span>](#net_a)
  - [<span data-ttu-id="d4a63-128">Uso de código para consultar en el Registro las versiones de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d4a63-128">Use code to query the registry for .NET Framework versions</span></span>](#net_c)

<span data-ttu-id="d4a63-129">Para obtener una lista de las versiones de CLR instaladas en un equipo, use una herramienta o código:</span><span class="sxs-lookup"><span data-stu-id="d4a63-129">To get a list of the CLR versions installed on a computer, use a tool or code:</span></span>

- [<span data-ttu-id="d4a63-130">Uso de la herramienta Clrver</span><span class="sxs-lookup"><span data-stu-id="d4a63-130">Use the Clrver tool</span></span>](#clr_a)
- [<span data-ttu-id="d4a63-131">Uso de código para consultar la clase Environment</span><span class="sxs-lookup"><span data-stu-id="d4a63-131">Use code to query the Environment class</span></span>](#clr_b)

<span data-ttu-id="d4a63-132">Para obtener información sobre cómo detectar las actualizaciones instaladas de cada versión de .NET Framework, vea [Cómo: Determinar las actualizaciones de .NET Framework que están instaladas](how-to-determine-which-net-framework-updates-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="d4a63-132">For information about detecting the installed updates for each version of the .NET Framework, see [How to: Determine which .NET Framework updates are installed](how-to-determine-which-net-framework-updates-are-installed.md).</span></span>

## <a name="find-newer-net-framework-versions-45-and-later"></a><span data-ttu-id="d4a63-133">Búsqueda de versiones más recientes de .NET Framework (4.5 y versiones posteriores)</span><span class="sxs-lookup"><span data-stu-id="d4a63-133">Find newer .NET Framework versions (4.5 and later)</span></span>

<a name="net_b"></a>

### <a name="find-net-framework-versions-45-and-later-in-the-registry"></a><span data-ttu-id="d4a63-134">Búsqueda de las versiones de .NET Framework 4.5 y versiones posteriores en el Registro</span><span class="sxs-lookup"><span data-stu-id="d4a63-134">Find .NET Framework versions 4.5 and later in the registry</span></span>

1. <span data-ttu-id="d4a63-135">En el menú **Inicio**, seleccione **Ejecutar**, escriba *regedit* y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d4a63-135">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>

     <span data-ttu-id="d4a63-136">Debe tener credenciales de administrador para ejecutar regedit.</span><span class="sxs-lookup"><span data-stu-id="d4a63-136">You must have administrative credentials to run regedit.</span></span>

2. <span data-ttu-id="d4a63-137">En el Editor del Registro, abra la subclave siguiente: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span><span class="sxs-lookup"><span data-stu-id="d4a63-137">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span></span> <span data-ttu-id="d4a63-138">Si la subclave **Full** no está presente, significa que .NET Framework 4.5 (o una versión posterior) no está instalado.</span><span class="sxs-lookup"><span data-stu-id="d4a63-138">If the **Full** subkey isn't present, then you don't have the .NET Framework 4.5 or later installed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d4a63-139">La carpeta **NET Framework Setup** del Registro *no* comienza con un punto.</span><span class="sxs-lookup"><span data-stu-id="d4a63-139">The **NET Framework Setup** folder in the registry does *not* begin with a period.</span></span>

3. <span data-ttu-id="d4a63-140">Busque una entrada DWORD denominada **Release**.</span><span class="sxs-lookup"><span data-stu-id="d4a63-140">Check for a DWORD entry named **Release**.</span></span> <span data-ttu-id="d4a63-141">Si existe, significa que tiene instalado .NET Framework 4.5 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="d4a63-141">If it exists, then you have .NET Framework 4.5 or later versions installed.</span></span> <span data-ttu-id="d4a63-142">Su valor es una clave de versión que corresponde a una versión concreta de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d4a63-142">Its value is a release key that corresponds to a particular version of the .NET Framework.</span></span> <span data-ttu-id="d4a63-143">En la ilustración siguiente, por ejemplo, el valor de la entrada **Release** es *378389*, que es la clave de versión de .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="d4a63-143">In the following figure, for example, the value of the **Release** entry is *378389*, which is the release key for .NET Framework 4.5.</span></span>

     <span data-ttu-id="d4a63-144">![Entrada del Registro para .NET Framework 4.5](media/clr-installdir.png "Registry entry for the .NET Framework 4.5")</span><span class="sxs-lookup"><span data-stu-id="d4a63-144">![Registry entry for the .NET Framework 4.5](media/clr-installdir.png "Registry entry for the .NET Framework 4.5")</span></span>

<span data-ttu-id="d4a63-145">En la tabla siguiente se muestra el valor de DWORD **Release** de sistemas operativos individuales para .NET Framework 4.5 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="d4a63-145">The following table lists the value of the **Release** DWORD on individual operating systems for .NET Framework 4.5 and later versions.</span></span>

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

<a name="version_table"></a>

|<span data-ttu-id="d4a63-146">Versión de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d4a63-146">.NET Framework version</span></span>|<span data-ttu-id="d4a63-147">Valor DWORD de la versión</span><span class="sxs-lookup"><span data-stu-id="d4a63-147">Value of the Release DWORD</span></span>|
|--------------------------------|-------------|
|<span data-ttu-id="d4a63-148">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="d4a63-148">.NET Framework 4.5</span></span>|<span data-ttu-id="d4a63-149">Todos los sistemas operativos Windows: 378389</span><span class="sxs-lookup"><span data-stu-id="d4a63-149">All Windows operating systems: 378389</span></span>|
|<span data-ttu-id="d4a63-150">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="d4a63-150">.NET Framework 4.5.1</span></span>|<span data-ttu-id="d4a63-151">En Windows 8.1 y Windows Server 2012 R2: 378675</span><span class="sxs-lookup"><span data-stu-id="d4a63-151">On Windows 8.1 and Windows Server 2012 R2: 378675</span></span><br /><span data-ttu-id="d4a63-152">En todos los demás sistemas operativos Windows: 378758</span><span class="sxs-lookup"><span data-stu-id="d4a63-152">On all other Windows operating systems: 378758</span></span>|
|<span data-ttu-id="d4a63-153">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="d4a63-153">.NET Framework 4.5.2</span></span>|<span data-ttu-id="d4a63-154">Todos los sistemas operativos Windows: 379893</span><span class="sxs-lookup"><span data-stu-id="d4a63-154">All Windows operating systems: 379893</span></span>|
|<span data-ttu-id="d4a63-155">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="d4a63-155">.NET Framework 4.6</span></span>|<span data-ttu-id="d4a63-156">En Windows 10: 393295</span><span class="sxs-lookup"><span data-stu-id="d4a63-156">On Windows 10: 393295</span></span><br /><span data-ttu-id="d4a63-157">En todos los demás sistemas operativos Windows: 393297</span><span class="sxs-lookup"><span data-stu-id="d4a63-157">On all other Windows operating systems: 393297</span></span>|
|<span data-ttu-id="d4a63-158">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="d4a63-158">.NET Framework 4.6.1</span></span>|<span data-ttu-id="d4a63-159">En sistemas con la actualización de noviembre de Windows 10: 394254</span><span class="sxs-lookup"><span data-stu-id="d4a63-159">On Windows 10 November Update systems: 394254</span></span><br /><span data-ttu-id="d4a63-160">En todos los demás sistemas operativos Windows (incluido Windows 10): 394271</span><span class="sxs-lookup"><span data-stu-id="d4a63-160">On all other Windows operating systems (including Windows 10): 394271</span></span>|
|<span data-ttu-id="d4a63-161">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="d4a63-161">.NET Framework 4.6.2</span></span>|<span data-ttu-id="d4a63-162">En la Actualización de aniversario de Windows 10 y Windows Server 2016: 394802</span><span class="sxs-lookup"><span data-stu-id="d4a63-162">On Windows 10 Anniversary Update and Windows Server 2016: 394802</span></span><br /><span data-ttu-id="d4a63-163">En todos los demás sistemas operativos Windows (incluidos otros sistemas operativos Windows 10): 394806</span><span class="sxs-lookup"><span data-stu-id="d4a63-163">On all other Windows operating systems (including other Windows 10 operating systems): 394806</span></span>|
|<span data-ttu-id="d4a63-164">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="d4a63-164">.NET Framework 4.7</span></span>|<span data-ttu-id="d4a63-165">En Windows 10 Creators Update: 460798</span><span class="sxs-lookup"><span data-stu-id="d4a63-165">On Windows 10 Creators Update: 460798</span></span><br /><span data-ttu-id="d4a63-166">En todos los demás sistemas operativos Windows (incluidos otros sistemas operativos Windows 10): 460805</span><span class="sxs-lookup"><span data-stu-id="d4a63-166">On all other Windows operating systems (including other Windows 10 operating systems): 460805</span></span>|
|<span data-ttu-id="d4a63-167">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="d4a63-167">.NET Framework 4.7.1</span></span>|<span data-ttu-id="d4a63-168">En Windows 10 Fall Creators Update y Windows Server, versión 1709: 461308</span><span class="sxs-lookup"><span data-stu-id="d4a63-168">On Windows 10 Fall Creators Update and Windows Server, version 1709: 461308</span></span><br/><span data-ttu-id="d4a63-169">En todos los demás sistemas operativos Windows (incluidos otros sistemas operativos Windows 10): 461310</span><span class="sxs-lookup"><span data-stu-id="d4a63-169">On all other Windows operating systems (including other Windows 10 operating systems): 461310</span></span>|
|<span data-ttu-id="d4a63-170">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="d4a63-170">.NET Framework 4.7.2</span></span>|<span data-ttu-id="d4a63-171">En la actualización de Windows 10 de abril de 2018 y Windows Server, versión 1803: 461808</span><span class="sxs-lookup"><span data-stu-id="d4a63-171">On Windows 10 April 2018 Update and Windows Server, version 1803: 461808</span></span><br/><span data-ttu-id="d4a63-172">En todos los sistemas operativos diferentes de la Actualización de abril de 2018 de Windows 10 y Windows Server, versión 1803: 461814</span><span class="sxs-lookup"><span data-stu-id="d4a63-172">On all Windows operating systems other than Windows 10 April 2018 Update and Windows Server, version 1803: 461814</span></span>|
|<span data-ttu-id="d4a63-173">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="d4a63-173">.NET Framework 4.8</span></span>|<span data-ttu-id="d4a63-174">En la actualización del 10 de mayo de 2019 de Windows 10: 528040</span><span class="sxs-lookup"><span data-stu-id="d4a63-174">On Windows 10 May 2019 Update: 528040</span></span><br/><span data-ttu-id="d4a63-175">En todos los demás sistemas operativos Windows (incluidos otros sistemas operativos Windows 10): 528049</span><span class="sxs-lookup"><span data-stu-id="d4a63-175">On all others Windows operating systems (including other Windows 10 operating systems): 528049</span></span>|

<span data-ttu-id="d4a63-176">Puede usar estos valores de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="d4a63-176">You can use these values as follows:</span></span>

- <span data-ttu-id="d4a63-177">Para determinar si una versión específica de .NET Framework está instalada en una versión concreta del sistema operativo Windows, pruebe si el valor de DWORD **Release** es *igual al* valor que aparece en la tabla.</span><span class="sxs-lookup"><span data-stu-id="d4a63-177">To determine whether a specific version of the .NET Framework is installed on a particular version of the Windows operating system, test whether the **Release** DWORD value is *equal to* the value listed in the table.</span></span> <span data-ttu-id="d4a63-178">Por ejemplo, para determinar si .NET Framework 4.6 está presente en un sistema Windows 10, pruebe un valor de **Release** que sea *igual a* 393295.</span><span class="sxs-lookup"><span data-stu-id="d4a63-178">For example, to determine whether .NET Framework 4.6 is present on a Windows 10 system, test for the a **Release** value that is *equal to* 393295.</span></span>

- <span data-ttu-id="d4a63-179">Para determinar si existe una versión mínima de .NET Framework, utilice el valor más bajo de DWORD **Release** para dicha versión.</span><span class="sxs-lookup"><span data-stu-id="d4a63-179">To determine whether a minimum version of the .NET Framework is present, use the smaller **RELEASE** DWORD value for that version.</span></span> <span data-ttu-id="d4a63-180">Por ejemplo, si la aplicación se ejecuta en .NET Framework 4.6 o una versión posterior, pruebe un valor de DWORD **RELEASE** que sea *mayor o igual que* 393295.</span><span class="sxs-lookup"><span data-stu-id="d4a63-180">For example, if your application runs under .NET Framework 4.6 or a later version, test for a **RELEASE** DWORD value that is *greater than or equal to* 393295.</span></span> <span data-ttu-id="d4a63-181">Para una tabla que muestra solo el valor mínimo de DWORD **RELEASE** para cada versión de .NET Framework, vea [Valores mínimos de DWORD Release para .NET Framework 4.5 y versiones posteriores](minimum-release-dword.md).</span><span class="sxs-lookup"><span data-stu-id="d4a63-181">For a table that lists only the minimum **RELEASE** DWORD value for each .NET Framework version, see [The minimum values of the Release DWORD for .NET Framework 4.5 and later versions](minimum-release-dword.md).</span></span>

- <span data-ttu-id="d4a63-182">Para probar varias versiones, empiece por probar un valor que sea *mayor o igual que* el valor más bajo de DWORD para la última versión de .NET Framework y, después, compare el valor con el valor más bajo de DWORD para cada versión anterior sucesiva.</span><span class="sxs-lookup"><span data-stu-id="d4a63-182">To test for multiple versions, begin by testing for a value that is *greater than or equal to* the smaller DWORD value for the latest .NET Framework version, and then compare the value with the smaller DWORD value for each successive earlier version.</span></span> <span data-ttu-id="d4a63-183">Por ejemplo, si la aplicación requiere .NET Framework 4.7 o versiones posteriores y quiere determinar cuál es la versión específica de .NET Framework existente, empiece por probar un valor de DWORD **RELEASE** que sea *mayor o igual que* 461808 (el valor de DWORD más pequeño para .NET Framework 4.7.2).</span><span class="sxs-lookup"><span data-stu-id="d4a63-183">For example, if your application requires .NET Framework 4.7 or later and you want to determine the specific version of .NET Framework present, start by testing for a **RELEASE** DWORD value that is *great than or equal to* to 461808 (the smaller DWORD value for .NET Framework 4.7.2).</span></span> <span data-ttu-id="d4a63-184">Después, compare el valor de DWORD **RELEASE** con el valor más bajo de cada versión posterior de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d4a63-184">Then compare the **RELEASE** DWORD value with the smaller value for each later .NET Framework version.</span></span> <span data-ttu-id="d4a63-185">Para una tabla que muestra solo el valor mínimo de DWORD **RELEASE** para cada versión de .NET Framework, vea [Valores mínimos de DWORD Release para .NET Framework 4.5 y versiones posteriores](minimum-release-dword.md).</span><span class="sxs-lookup"><span data-stu-id="d4a63-185">For a table that lists only the minimum **RELEASE** DWORD value for each .NET Framework version, see [The minimum values of the Release DWORD for .NET Framework 4.5 and later versions](minimum-release-dword.md).</span></span>

<a name="net_d"></a>

### <a name="find-net-framework-versions-45-and-later-with-code"></a><span data-ttu-id="d4a63-186">Búsqueda de versiones de .NET Framework 4.5 y versiones posteriores con código</span><span class="sxs-lookup"><span data-stu-id="d4a63-186">Find .NET Framework versions 4.5 and later with code</span></span>

1. <span data-ttu-id="d4a63-187">Use los métodos <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> y <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> para obtener acceso a la subclave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** en el Registro de Windows.</span><span class="sxs-lookup"><span data-stu-id="d4a63-187">Use the <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> and <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> methods to access the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey in the Windows registry.</span></span>

    <span data-ttu-id="d4a63-188">La existencia de la entrada DWORD **Release** en la subclave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** indica que .NET Framework 4.5 (o una versión posterior) está instalado en un equipo.</span><span class="sxs-lookup"><span data-stu-id="d4a63-188">The existence of the **Release** DWORD entry in the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey indicates that the .NET Framework 4.5 or a later version is installed on a computer.</span></span>

2. <span data-ttu-id="d4a63-189">Compruebe el valor de la entrada **Release** para determinar la versión instalada.</span><span class="sxs-lookup"><span data-stu-id="d4a63-189">Check the value of the **Release** entry to determine the installed version.</span></span> <span data-ttu-id="d4a63-190">Para que sea compatible con versiones posteriores, puede buscar un valor mayor o igual que el valor que se muestra en la [tabla de versiones de .NET Framework](#version_table).</span><span class="sxs-lookup"><span data-stu-id="d4a63-190">To be forward-compatible, check for a value greater than or equal to the value listed in the [.NET Framework version table](#version_table).</span></span>

<span data-ttu-id="d4a63-191">En el ejemplo siguiente se comprueba el valor de la entrada **Release** del Registro para buscar .NET Framework 4.5 y las versiones posteriores que están instaladas:</span><span class="sxs-lookup"><span data-stu-id="d4a63-191">The following example checks the value of the **Release** entry in the registry to find the .NET Framework 4.5 and later versions that are installed:</span></span>

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

<span data-ttu-id="d4a63-192">Este ejemplo sigue la práctica recomendada para la comprobación de versión:</span><span class="sxs-lookup"><span data-stu-id="d4a63-192">This example follows the recommended practice for version checking:</span></span>

- <span data-ttu-id="d4a63-193">Comprueba si el valor de la entrada **Release** es *mayor o igual* que el valor de las claves de versión conocidas.</span><span class="sxs-lookup"><span data-stu-id="d4a63-193">It checks whether the value of the **Release** entry is *greater than or equal to* the value of the known release keys.</span></span>

- <span data-ttu-id="d4a63-194">Realiza la comprobación en orden, desde la versión más reciente hasta la más antigua.</span><span class="sxs-lookup"><span data-stu-id="d4a63-194">It checks in order from most recent version to earliest version.</span></span>

<a name="ps_a"></a>

### <a name="check-for-a-minimum-required-net-framework-version-45-and-later-with-powershell"></a><span data-ttu-id="d4a63-195">Búsqueda de una versión mínima requerida de .NET Framework (4.5 y posterior) con PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4a63-195">Check for a minimum-required .NET Framework version (4.5 and later) with PowerShell</span></span>

- <span data-ttu-id="d4a63-196">Use comandos de PowerShell para comprobar el valor de la entrada **Release** de la subclave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span><span class="sxs-lookup"><span data-stu-id="d4a63-196">Use PowerShell commands to check the value of the **Release** entry of the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey.</span></span>

<span data-ttu-id="d4a63-197">En los ejemplos siguientes se comprueba el valor de la entrada **Release** para determinar si está instalado .NET Framework 4.6.2 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="d4a63-197">The following examples check the value of the **Release** entry to determine whether the .NET Framework 4.6.2 or later is installed.</span></span> <span data-ttu-id="d4a63-198">Este código devuelve `True` si está instalado y `False` en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="d4a63-198">This code returns `True` if it's installed and `False` otherwise.</span></span>

```PowerShell
# PowerShell 5
 Get-ChildItem 'HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\' |  Get-ItemPropertyValue -Name Release | Foreach-Object { $_ -ge 394802 }
 ```

```PowerShell
# PowerShell 4
(Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -ge 394802
```

<span data-ttu-id="d4a63-199">Para comprobar si hay una versión mínima requerida de .NET Framework diferente, reemplace *394802* en estos ejemplos por un valor **Release** de la [tabla de versiones de .NET Framework](#version_table).</span><span class="sxs-lookup"><span data-stu-id="d4a63-199">To check for a different minimum-required .NET Framework version, replace *394802* in these examples with a **Release** value from the [.NET Framework version table](#version_table).</span></span>

## <a name="find-older-net-framework-versions-182114"></a><span data-ttu-id="d4a63-200">Búsqueda de versiones más antiguas de .NET Framework (1&#8211;4)</span><span class="sxs-lookup"><span data-stu-id="d4a63-200">Find older .NET Framework versions (1&#8211;4)</span></span>

<a name="net_a"></a>

### <a name="find-net-framework-versions-182114-in-the-registry"></a><span data-ttu-id="d4a63-201">Búsqueda de versiones de 1 a 4 de .NET Framework en el Registro</span><span class="sxs-lookup"><span data-stu-id="d4a63-201">Find .NET Framework versions 1&#8211;4 in the registry</span></span>

1. <span data-ttu-id="d4a63-202">En el menú **Inicio**, seleccione **Ejecutar**, escriba *regedit* y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d4a63-202">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>

    <span data-ttu-id="d4a63-203">Debe tener credenciales de administrador para ejecutar regedit.</span><span class="sxs-lookup"><span data-stu-id="d4a63-203">You must have administrative credentials to run regedit.</span></span>

2. <span data-ttu-id="d4a63-204">En el Editor del Registro, abra la subclave siguiente: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:</span><span class="sxs-lookup"><span data-stu-id="d4a63-204">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:</span></span>

    - <span data-ttu-id="d4a63-205">Para las versiones de .NET Framework de 1.1 a 3.5, cada versión instalada aparece como una subclave bajo la subclave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**.</span><span class="sxs-lookup"><span data-stu-id="d4a63-205">For .NET Framework versions 1.1 through 3.5, each installed version is listed as a subkey under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP** subkey.</span></span> <span data-ttu-id="d4a63-206">Por ejemplo, **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**.</span><span class="sxs-lookup"><span data-stu-id="d4a63-206">For example, **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**.</span></span> <span data-ttu-id="d4a63-207">El número de versión se almacena como un valor en la entrada **Version** de la subclave de versión.</span><span class="sxs-lookup"><span data-stu-id="d4a63-207">The version number is stored as a value in the version subkey's **Version** entry.</span></span>

    - <span data-ttu-id="d4a63-208">Para .NET Framework 4, la entrada **Version** se halla bajo la subclave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client**, bajo la subclave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** o bajo ambas subclaves.</span><span class="sxs-lookup"><span data-stu-id="d4a63-208">For .NET Framework 4, the **Version** entry is under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client** subkey, the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** subkey, or under both subkeys.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d4a63-209">La carpeta **NET Framework Setup** del Registro no comienza con un punto.</span><span class="sxs-lookup"><span data-stu-id="d4a63-209">The **NET Framework Setup** folder in the registry does not begin with a period.</span></span>

    <span data-ttu-id="d4a63-210">En la siguiente ilustración se muestra la subclave y su entrada **Version** para .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="d4a63-210">The following figure shows the subkey and its **Version** entry for the .NET Framework 3.5.</span></span>

    <span data-ttu-id="d4a63-211">![Entrada del Registro de .NET Framework 3.5. ](media/net-4-and-earlier.png ".NET Framework 3.5 y versiones anteriores")</span><span class="sxs-lookup"><span data-stu-id="d4a63-211">![The registry entry for the .NET Framework 3.5.](media/net-4-and-earlier.png ".NET Framework 3.5 and earlier versions")</span></span>

<a name="net_c"></a>

### <a name="find-net-framework-versions-182114-with-code"></a><span data-ttu-id="d4a63-212">Búsqueda de versiones de .NET Framework de 1 a 4 con código</span><span class="sxs-lookup"><span data-stu-id="d4a63-212">Find .NET Framework versions 1&#8211;4 with code</span></span>

- <span data-ttu-id="d4a63-213">Use la clase <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> para tener acceso a la subclave **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** en el Registro de Windows.</span><span class="sxs-lookup"><span data-stu-id="d4a63-213">Use the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** subkey in the Windows registry.</span></span>

<span data-ttu-id="d4a63-214">En el ejemplo siguiente se buscan las versiones de 1 a 4 de .NET Framework que están instaladas:</span><span class="sxs-lookup"><span data-stu-id="d4a63-214">The following example finds the .NET Framework 1&#8211;4 versions that are installed:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

## <a name="find-clr-versions"></a><span data-ttu-id="d4a63-215">Búsqueda de versiones de CLR</span><span class="sxs-lookup"><span data-stu-id="d4a63-215">Find CLR versions</span></span>

<a name="clr_a"></a>

### <a name="find-the-current-clr-version-with-clrverexe"></a><span data-ttu-id="d4a63-216">Búsqueda de la versión actual de CLR con Clrver.exe</span><span class="sxs-lookup"><span data-stu-id="d4a63-216">Find the current CLR version with Clrver.exe</span></span>

<span data-ttu-id="d4a63-217">Use la [herramienta de versión de CLR (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) para determinar qué versiones de CLR están instaladas en un equipo:</span><span class="sxs-lookup"><span data-stu-id="d4a63-217">Use the [CLR Version tool (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) to determine which versions of the CLR are installed on a computer:</span></span>

- <span data-ttu-id="d4a63-218">En un [Símbolo del sistema para desarrolladores de Visual Studio](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs), escriba `clrver`.</span><span class="sxs-lookup"><span data-stu-id="d4a63-218">From a [Developer Command Prompt for Visual Studio](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs), enter `clrver`.</span></span>

    <span data-ttu-id="d4a63-219">Salida de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d4a63-219">Sample output:</span></span>

    ```console
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

<a name="clr_b"></a>

### <a name="find-the-current-clr-version-with-the-environment-class"></a><span data-ttu-id="d4a63-220">Búsqueda de la versión actual de CLR con la clase Environment</span><span class="sxs-lookup"><span data-stu-id="d4a63-220">Find the current CLR version with the Environment class</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d4a63-221">Para .NET Framework 4.5 y versiones posteriores, no use la propiedad <xref:System.Environment.Version%2A?displayProperty=nameWithType> para detectar la versión de CLR.</span><span class="sxs-lookup"><span data-stu-id="d4a63-221">For the .NET Framework 4.5 and later versions, don't use the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to detect the version of the CLR.</span></span> <span data-ttu-id="d4a63-222">En su lugar, consultar el Registro como se describe en [Búsqueda de versiones de .NET Framework 4.5 y versiones posteriores con código](#net_d).</span><span class="sxs-lookup"><span data-stu-id="d4a63-222">Instead, query the registry as described in [Find .NET Framework versions 4.5 and later with code](#net_d).</span></span>

1. <span data-ttu-id="d4a63-223">Consulte la propiedad <xref:System.Environment.Version?displayProperty=nameWithType> para recuperar un objeto <xref:System.Version>.</span><span class="sxs-lookup"><span data-stu-id="d4a63-223">Query the <xref:System.Environment.Version?displayProperty=nameWithType> property to retrieve a <xref:System.Version> object.</span></span>

    <span data-ttu-id="d4a63-224">El objeto `System.Version` devuelto identifica la versión de tiempo de ejecución que está ejecutando el código.</span><span class="sxs-lookup"><span data-stu-id="d4a63-224">The returned `System.Version` object identifies the version of the runtime that's currently executing the code.</span></span> <span data-ttu-id="d4a63-225">No devuelve versiones de ensamblado ni otras versiones del runtime que se hayan instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="d4a63-225">It doesn't return assembly versions or other versions of the runtime that may have been installed on the computer.</span></span>

    <span data-ttu-id="d4a63-226">Para las versiones 4, 4.5, 4.5.1 y 4.5.2 de .NET Framework, la representación de cadena del objeto <xref:System.Version> devuelto tiene la forma 4.0.30319.*xxxxx*, donde *xxxxx* es inferior a 42000.</span><span class="sxs-lookup"><span data-stu-id="d4a63-226">For the .NET Framework versions 4, 4.5, 4.5.1, and 4.5.2, the string representation of the returned <xref:System.Version> object has the form 4.0.30319.*xxxxx*, where *xxxxx* is less than 42000.</span></span> <span data-ttu-id="d4a63-227">Para .NET Framework 4.6 y versiones posteriores, tiene la forma 4.0.30319.42000.</span><span class="sxs-lookup"><span data-stu-id="d4a63-227">For the .NET Framework 4.6 and later versions, it has the form 4.0.30319.42000.</span></span>

2. <span data-ttu-id="d4a63-228">Una vez que tenga el objeto `Version`, consúltelo de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="d4a63-228">After you have the `Version` object, query it as follows:</span></span>

   - <span data-ttu-id="d4a63-229">Para el identificador de versión principal (por ejemplo, *4* en la versión 4.0), use la propiedad <xref:System.Version.Major%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d4a63-229">For the major release identifier (for example, *4* for version 4.0), use the <xref:System.Version.Major%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="d4a63-230">Para el identificador de versión secundaria (por ejemplo, *0* en la versión 4.0), use la propiedad <xref:System.Version.Minor%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d4a63-230">For the minor release identifier (for example, *0* for version 4.0), use the <xref:System.Version.Minor%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="d4a63-231">Para la cadena de versión completa (por ejemplo, *4.0.30319.18010*), use el método <xref:System.Version.ToString%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d4a63-231">For the entire version string (for example, *4.0.30319.18010*), use the <xref:System.Version.ToString%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="d4a63-232">Este método devuelve un valor único que refleja la versión del runtime que está ejecutando el código.</span><span class="sxs-lookup"><span data-stu-id="d4a63-232">This method returns a single value that reflects the version of the runtime that's executing the code.</span></span> <span data-ttu-id="d4a63-233">No devuelve versiones de ensamblado ni otras versiones del runtime que se hayan instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="d4a63-233">It doesn't return assembly versions or other runtime versions that may be installed on the computer.</span></span>

<span data-ttu-id="d4a63-234">En el ejemplo siguiente se usa la propiedad <xref:System.Environment.Version%2A?displayProperty=nameWithType> para recuperar la información de la versión de CLR:</span><span class="sxs-lookup"><span data-stu-id="d4a63-234">The following example uses the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to retrieve CLR version information:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a><span data-ttu-id="d4a63-235">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4a63-235">See also</span></span>

- [<span data-ttu-id="d4a63-236">Cómo: Determinar las actualizaciones de .NET Framework que están instaladas</span><span class="sxs-lookup"><span data-stu-id="d4a63-236">How to: Determine which .NET Framework updates are installed</span></span>](how-to-determine-which-net-framework-updates-are-installed.md)
- [<span data-ttu-id="d4a63-237">Instalación de .NET Framework para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="d4a63-237">Install the .NET Framework for developers</span></span>](../install/guide-for-developers.md)
- [<span data-ttu-id="d4a63-238">Versiones y dependencias de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d4a63-238">.NET Framework versions and dependencies</span></span>](versions-and-dependencies.md)

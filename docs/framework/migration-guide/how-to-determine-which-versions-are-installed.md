---
title: Procedimiento para determinar qué versiones de .NET Framework están instaladas
ms.date: 03/18/2019
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
ms.openlocfilehash: 9c4ad3ca5694457637a82a36c8db4534df43a9d7
ms.sourcegitcommit: 8258515adc6c37ab6278e5a3d102d593246f8672
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "58504436"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a><span data-ttu-id="9c2ee-102">Procedimiento para determinar qué versiones de .NET Framework están instaladas</span><span class="sxs-lookup"><span data-stu-id="9c2ee-102">How to: Determine which .NET Framework versions are installed</span></span>

<span data-ttu-id="9c2ee-103">Los usuarios pueden [instalar](https://docs.microsoft.com/dotnet/framework/install) y ejecutar varias versiones de .NET Framework en sus equipos.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-103">Users can [install](https://docs.microsoft.com/dotnet/framework/install) and run multiple versions of the .NET Framework on their computers.</span></span> <span data-ttu-id="9c2ee-104">Al desarrollar o implementar una aplicación, puede que necesite conocer las versiones de .NET Framework que están instaladas en el equipo del usuario.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-104">When you develop or deploy your app, you might need to know which .NET Framework versions are installed on the user’s computer.</span></span> 

<span data-ttu-id="9c2ee-105">.NET Framework está formado por dos componentes principales con versiones separadas:</span><span class="sxs-lookup"><span data-stu-id="9c2ee-105">The .NET Framework consists of two main components, which are versioned separately:</span></span>  
  
- <span data-ttu-id="9c2ee-106">Un conjunto de ensamblados, que son colecciones de tipos y recursos que proporcionan funciones a las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-106">A set of assemblies, which are collections of types and resources that provide the functionality for your apps.</span></span> <span data-ttu-id="9c2ee-107">.NET Framework y los ensamblados comparten el mismo número de versión.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-107">The .NET Framework and assemblies share the same version number.</span></span>  
  
- <span data-ttu-id="9c2ee-108">Common Language Runtime (CLR), que administra y ejecuta el código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-108">The common language runtime (CLR), which manages and executes your app's code.</span></span> <span data-ttu-id="9c2ee-109">El CLR se identifica mediante su propio número de versión (consulte [Versiones y dependencias](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span><span class="sxs-lookup"><span data-stu-id="9c2ee-109">The CLR is identified by its own version number (see [Versions and Dependencies](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span></span>  

> [!NOTE]
> <span data-ttu-id="9c2ee-110">Cada versión de .NET Framework contiene características de versiones anteriores e incorpora nuevas características.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-110">Each new version of the .NET Framework retains features from the previous versions and adds new features.</span></span> <span data-ttu-id="9c2ee-111">Puede cargar varias versiones de .NET Framework en un equipo al mismo tiempo, lo que significa que puede instalarlo sin tener que eliminar las versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-111">You can load multiple versions of the .NET Framework on a single computer at the same time, which means that you can install the .NET Framework without having to uninstall previous versions.</span></span> <span data-ttu-id="9c2ee-112">En general, no debe desinstalar ninguna versión anterior de .NET Framework, ya que una determinada aplicación puede depender de una versión concreta y puede dejar de funcionar si se quita esa versión.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-112">In general, you shouldn't uninstall previous versions of the .NET Framework, because an application you use may depend on a specific version and may break if that version is removed.</span></span>
>
> <span data-ttu-id="9c2ee-113">Hay una diferencia entre la versión de .NET Framework y la versión de CLR:</span><span class="sxs-lookup"><span data-stu-id="9c2ee-113">There is a difference between the .NET Framework version and the CLR version:</span></span> 
> - <span data-ttu-id="9c2ee-114">Las versiones de .NET Framework se basan en el conjunto de ensamblados que conforman la biblioteca de clases .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-114">The .NET Framework version is based on the set of assemblies that form the .NET Framework class library.</span></span> <span data-ttu-id="9c2ee-115">Por ejemplo, las versiones de .NET Framework incluyen 4.5, 4.6.1 y 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-115">For example, .NET Framework versions include 4.5, 4.6.1, and 4.7.2.</span></span> 
>- <span data-ttu-id="9c2ee-116">La versión de CLR se basa en el tiempo de ejecución en el que se ejecutan las aplicaciones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-116">The CLR version is based on the runtime on which .NET Framework applications execute.</span></span> <span data-ttu-id="9c2ee-117">Normalmente, una misma versión de CLR admite varias versiones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-117">A single CLR version typically supports multiple .NET Framework versions.</span></span> <span data-ttu-id="9c2ee-118">Por ejemplo, la versión de CLR 4.0.30319.*xxxxx* admite las versiones de la 4 a la 4.5.2 de .NET Framework ; la versión de CLR 4.0.30319.42000 admite las versiones de .NET Framework a partir de .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-118">For example, CLR version 4.0.30319.*xxxxx* supports .NET Framework versions 4 through 4.5.2 and CLR version 4.0.30319.42000 supports .NET Framework versions starting with .NET Framework 4.6.</span></span> 
>
> <span data-ttu-id="9c2ee-119">Para obtener más información sobre las versiones, vea [Versiones y dependencias de .NET Framework](versions-and-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="9c2ee-119">For more information about versions, see [.NET Framework versions and dependencies](versions-and-dependencies.md).</span></span>


<span data-ttu-id="9c2ee-120">Para obtener una lista de las versiones de .NET Framework instaladas en un equipo, debe tener acceso al Registro.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-120">To get a list of the .NET Framework versions installed on a computer, you access the registry.</span></span> <span data-ttu-id="9c2ee-121">Puede usar el Editor del Registro para ver el Registro o usar código para consultarlo:</span><span class="sxs-lookup"><span data-stu-id="9c2ee-121">You can either use the Registry Editor to view the registry or use code to query it:</span></span>
 
- <span data-ttu-id="9c2ee-122">Búsqueda de versiones más recientes de .NET Framework (4.5 y versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="9c2ee-122">Find newer .NET Framework versions (4.5 and later):</span></span> 
     - [<span data-ttu-id="9c2ee-123">Uso del Editor del Registro para buscar versiones de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9c2ee-123">Use the Registry Editor to find .NET Framework versions</span></span>](#net_b)  
     - [<span data-ttu-id="9c2ee-124">Uso de código para consultar en el Registro las versiones de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9c2ee-124">Use code to query the registry for .NET Framework versions</span></span>](#net_d)  
     - [<span data-ttu-id="9c2ee-125">Uso de PowerShell para consultar en el Registro las versiones de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9c2ee-125">Use PowerShell to query the registry for .NET Framework versions</span></span>](#ps_a)
- <span data-ttu-id="9c2ee-126">Búsqueda de versiones más antiguas de .NET Framework (1&#8211;4):</span><span class="sxs-lookup"><span data-stu-id="9c2ee-126">Find older .NET Framework versions (1&#8211;4):</span></span>
     - [<span data-ttu-id="9c2ee-127">Uso del Editor del Registro para buscar versiones de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9c2ee-127">Use the Registry Editor to find .NET Framework versions</span></span>](#net_a)
     - [<span data-ttu-id="9c2ee-128">Uso de código para consultar en el Registro las versiones de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9c2ee-128">Use code to query the registry for .NET Framework versions</span></span>](#net_c)   

<span data-ttu-id="9c2ee-129">Para obtener una lista de las versiones de CLR instaladas en un equipo, use una herramienta o código:</span><span class="sxs-lookup"><span data-stu-id="9c2ee-129">To get a list of the CLR versions installed on a computer, use a tool or code:</span></span>  
  
- [<span data-ttu-id="9c2ee-130">Uso de la herramienta Clrver</span><span class="sxs-lookup"><span data-stu-id="9c2ee-130">Use the Clrver tool</span></span>](#clr_a)  
- [<span data-ttu-id="9c2ee-131">Uso de código para consultar la clase Environment</span><span class="sxs-lookup"><span data-stu-id="9c2ee-131">Use code to query the Environment class</span></span>](#clr_b)  

<span data-ttu-id="9c2ee-132">Para obtener información sobre cómo detectar las actualizaciones instaladas de cada versión de .NET Framework, vea [Cómo: Determinar las actualizaciones de .NET Framework que están instaladas](how-to-determine-which-net-framework-updates-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="9c2ee-132">For information about detecting the installed updates for each version of the .NET Framework, see [How to: Determine which .NET Framework updates are installed](how-to-determine-which-net-framework-updates-are-installed.md).</span></span> 
  

## <a name="find-newer-net-framework-versions-45-and-later"></a><span data-ttu-id="9c2ee-133">Búsqueda de versiones más recientes de .NET Framework (4.5 y versiones posteriores)</span><span class="sxs-lookup"><span data-stu-id="9c2ee-133">Find newer .NET Framework versions (4.5 and later)</span></span>

<a name="net_b"></a> 
### <a name="find-net-framework-versions-45-and-later-in-the-registry"></a><span data-ttu-id="9c2ee-134">Búsqueda de las versiones de .NET Framework 4.5 y versiones posteriores en el Registro</span><span class="sxs-lookup"><span data-stu-id="9c2ee-134">Find .NET Framework versions 4.5 and later in the registry</span></span>

1. <span data-ttu-id="9c2ee-135">En el menú **Inicio**, seleccione **Ejecutar**, escriba *regedit* y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-135">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>

     <span data-ttu-id="9c2ee-136">Debe tener credenciales de administrador para ejecutar regedit.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-136">You must have administrative credentials to run regedit.</span></span>

2. <span data-ttu-id="9c2ee-137">En el Editor del Registro, abra la subclave siguiente: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-137">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span></span> <span data-ttu-id="9c2ee-138">Si la subclave **Full** no está presente, significa que .NET Framework 4.5 (o una versión posterior) no está instalado.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-138">If the **Full** subkey isn't present, then you don't have the .NET Framework 4.5 or later installed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9c2ee-139">La carpeta **NET Framework Setup** del Registro no comienza con un punto.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-139">The **NET Framework Setup** folder in the registry does not begin with a period.</span></span>

3. <span data-ttu-id="9c2ee-140">Busque una entrada DWORD denominada **Release**.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-140">Check for a DWORD entry named **Release**.</span></span> <span data-ttu-id="9c2ee-141">Si existe, significa que tiene instalado .NET Framework 4.5 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-141">If it exists, then you have .NET Framework 4.5 or later versions installed.</span></span> <span data-ttu-id="9c2ee-142">Su valor es una clave de versión que corresponde a una versión concreta de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-142">Its value is a release key that corresponds to a particular version of the .NET Framework.</span></span> <span data-ttu-id="9c2ee-143">En la ilustración siguiente, por ejemplo, el valor de la entrada **Release** es *378389*, que es la clave de versión de .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-143">In the following figure, for example, the value of the **Release** entry is *378389*, which is the release key for .NET Framework 4.5.</span></span> 

     <span data-ttu-id="9c2ee-144">![Entrada del Registro para .NET Framework 4.5](media/clr-installdir.png "Registry entry for the .NET Framework 4.5")</span><span class="sxs-lookup"><span data-stu-id="9c2ee-144">![Registry entry for the .NET Framework 4.5](media/clr-installdir.png "Registry entry for the .NET Framework 4.5")</span></span>

<span data-ttu-id="9c2ee-145">En la tabla siguiente se muestra el valor mínimo del valor de la entrada **Release** para cada versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-145">The following table lists the minimum value of the **Release** entry for each .NET Framework version.</span></span> <span data-ttu-id="9c2ee-146">Puede usar estos valores de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="9c2ee-146">You can use these values as follows:</span></span>

- <span data-ttu-id="9c2ee-147">Para determinar si existe una versión mínima de .NET Framework, pruebe si el valor DWORD **Release** que se encuentra en el Registro es *mayor o igual* que el valor que aparece en la tabla.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-147">To determine whether a minimum .NET Framework version is present, test whether the **Release** DWORD value found in the registry is *greater than or equal to* the value listed in the table.</span></span> <span data-ttu-id="9c2ee-148">Por ejemplo, si la aplicación requiere .NET Framework 4.7 o versiones posteriores, debe probar si el valor de versión mínimo es *460798*.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-148">For example, if your application requires the .NET Framework 4.7 or later, you test for a minimum release key value of *460798*.</span></span>

- <span data-ttu-id="9c2ee-149">Para probar varias versiones, comience con la versión más reciente de .NET Framework y, luego, pruebe las versiones anteriores sucesivas.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-149">To test for multiple versions, begin with the latest .NET Framework version, and then test for each successive earlier version.</span></span>

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

<a name="version_table"></a>

|<span data-ttu-id="9c2ee-150">Versión de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9c2ee-150">.NET Framework version</span></span>|<span data-ttu-id="9c2ee-151">Valor DWORD de la versión</span><span class="sxs-lookup"><span data-stu-id="9c2ee-151">Value of the Release DWORD</span></span>|
|--------------------------------|-------------|
|<span data-ttu-id="9c2ee-152">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="9c2ee-152">.NET Framework 4.5</span></span>|<span data-ttu-id="9c2ee-153">378389</span><span class="sxs-lookup"><span data-stu-id="9c2ee-153">378389</span></span>|
|<span data-ttu-id="9c2ee-154">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="9c2ee-154">.NET Framework 4.5.1</span></span>|<span data-ttu-id="9c2ee-155">378675</span><span class="sxs-lookup"><span data-stu-id="9c2ee-155">378675</span></span>|
|<span data-ttu-id="9c2ee-156">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="9c2ee-156">.NET Framework 4.5.2</span></span>|<span data-ttu-id="9c2ee-157">379893</span><span class="sxs-lookup"><span data-stu-id="9c2ee-157">379893</span></span>|
|<span data-ttu-id="9c2ee-158">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="9c2ee-158">.NET Framework 4.6</span></span>|<span data-ttu-id="9c2ee-159">393295</span><span class="sxs-lookup"><span data-stu-id="9c2ee-159">393295</span></span>|
|<span data-ttu-id="9c2ee-160">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="9c2ee-160">.NET Framework 4.6.1</span></span>|<span data-ttu-id="9c2ee-161">394254</span><span class="sxs-lookup"><span data-stu-id="9c2ee-161">394254</span></span>|
|<span data-ttu-id="9c2ee-162">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="9c2ee-162">.NET Framework 4.6.2</span></span>|<span data-ttu-id="9c2ee-163">394802</span><span class="sxs-lookup"><span data-stu-id="9c2ee-163">394802</span></span>|
|<span data-ttu-id="9c2ee-164">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="9c2ee-164">.NET Framework 4.7</span></span>|<span data-ttu-id="9c2ee-165">460798</span><span class="sxs-lookup"><span data-stu-id="9c2ee-165">460798</span></span>|
|<span data-ttu-id="9c2ee-166">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="9c2ee-166">.NET Framework 4.7.1</span></span>|<span data-ttu-id="9c2ee-167">461308</span><span class="sxs-lookup"><span data-stu-id="9c2ee-167">461308</span></span>|
|<span data-ttu-id="9c2ee-168">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="9c2ee-168">.NET Framework 4.7.2</span></span>|<span data-ttu-id="9c2ee-169">461808</span><span class="sxs-lookup"><span data-stu-id="9c2ee-169">461808</span></span>|

<span data-ttu-id="9c2ee-170">Para obtener una tabla completa de claves de versión de .NET Framework para versiones específicas del sistema operativo Windows, consulte [.NET Framework release keys and Windows operating system versions](release-keys-and-os-versions.md) (Claves de versión de .NET Framework y versiones del sistema operativo Windows).</span><span class="sxs-lookup"><span data-stu-id="9c2ee-170">For a complete table of release keys for the .NET Framework for specific Windows operating system versions, see [.NET Framework release keys and Windows operating system versions](release-keys-and-os-versions.md).</span></span>


<a name="net_d"></a> 
### <a name="find-net-framework-versions-45-and-later-with-code"></a><span data-ttu-id="9c2ee-171">Búsqueda de versiones de .NET Framework 4.5 y versiones posteriores con código</span><span class="sxs-lookup"><span data-stu-id="9c2ee-171">Find .NET Framework versions 4.5 and later with code</span></span>

1. <span data-ttu-id="9c2ee-172">Use los métodos <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> y <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> para obtener acceso a la subclave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** en el Registro de Windows.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-172">Use the <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> and <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> methods to access the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey in the Windows registry.</span></span>

    <span data-ttu-id="9c2ee-173">La existencia de la entrada DWORD **Release** en la subclave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** indica que .NET Framework 4.5 (o una versión posterior) está instalado en un equipo.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-173">The existence of the **Release** DWORD entry in the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey indicates that the .NET Framework 4.5 or a later version is installed on a computer.</span></span> 

2. <span data-ttu-id="9c2ee-174">Compruebe el valor de la entrada **Release** para determinar la versión instalada.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-174">Check the value of the **Release** entry to determine the installed version.</span></span> <span data-ttu-id="9c2ee-175">Para que sea compatible con versiones posteriores, puede buscar un valor mayor o igual que el valor que se muestra en la [tabla de versiones de .NET Framework](#version_table).</span><span class="sxs-lookup"><span data-stu-id="9c2ee-175">To be forward-compatible, check for a value greater than or equal to the value listed in the [.NET Framework version table](#version_table).</span></span>

<span data-ttu-id="9c2ee-176">En el ejemplo siguiente se comprueba el valor de la entrada **Release** del Registro para buscar .NET Framework 4.5 y las versiones posteriores que están instaladas:</span><span class="sxs-lookup"><span data-stu-id="9c2ee-176">The following example checks the value of the **Release** entry in the registry to find the .NET Framework 4.5 and later versions that are installed:</span></span>

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

<span data-ttu-id="9c2ee-177">Este ejemplo sigue la práctica recomendada para la comprobación de versión:</span><span class="sxs-lookup"><span data-stu-id="9c2ee-177">This example follows the recommended practice for version checking:</span></span>

- <span data-ttu-id="9c2ee-178">Comprueba si el valor de la entrada **Release** es *mayor o igual* que el valor de las claves de versión conocidas.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-178">It checks whether the value of the **Release** entry is *greater than or equal to* the value of the known release keys.</span></span>

- <span data-ttu-id="9c2ee-179">Realiza la comprobación en orden, desde la versión más reciente hasta la más antigua.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-179">It checks in order from most recent version to earliest version.</span></span>

<a name="ps_a"></a> 
### <a name="check-for-a-minimum-required-net-framework-version-45-and-later-with-powershell"></a><span data-ttu-id="9c2ee-180">Búsqueda de una versión mínima requerida de .NET Framework (4.5 y posterior) con PowerShell</span><span class="sxs-lookup"><span data-stu-id="9c2ee-180">Check for a minimum-required .NET Framework version (4.5 and later) with PowerShell</span></span>

- <span data-ttu-id="9c2ee-181">Use comandos de PowerShell para comprobar el valor de la entrada **Release** de la subclave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-181">Use PowerShell commands to check the value of the **Release** entry of the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey.</span></span>

<span data-ttu-id="9c2ee-182">En los ejemplos siguientes se comprueba el valor de la entrada **Release** para determinar si está instalado .NET Framework 4.6.2 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-182">The following examples check the value of the **Release** entry to determine whether the .NET Framework 4.6.2 or later is installed.</span></span> <span data-ttu-id="9c2ee-183">Este código devuelve `True` si está instalado y `False` en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-183">This code returns `True` if it's installed and `False` otherwise.</span></span>

```PowerShell
# PowerShell 5
 Get-ChildItem 'HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\' |  Get-ItemPropertyValue -Name Release | Foreach-Object { $_ -ge 394802 } 
 ```

```PowerShell
# PowerShell 4
(Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -ge 394802
```

<span data-ttu-id="9c2ee-184">Para comprobar si hay una versión mínima requerida de .NET Framework diferente, reemplace *394802* en estos ejemplos por un valor **Release** de la [tabla de versiones de .NET Framework](#version_table).</span><span class="sxs-lookup"><span data-stu-id="9c2ee-184">To check for a different minimum-required .NET Framework version, replace *394802* in these examples with a **Release** value from the [.NET Framework version table](#version_table).</span></span>

## <a name="find-older-net-framework-versions-182114"></a><span data-ttu-id="9c2ee-185">Búsqueda de versiones más antiguas de .NET Framework (1&#8211;4)</span><span class="sxs-lookup"><span data-stu-id="9c2ee-185">Find older .NET Framework versions (1&#8211;4)</span></span>

<a name="net_a"></a>
### <a name="find-net-framework-versions-182114-in-the-registry"></a><span data-ttu-id="9c2ee-186">Búsqueda de versiones de 1 a 4 de .NET Framework en el Registro</span><span class="sxs-lookup"><span data-stu-id="9c2ee-186">Find .NET Framework versions 1&#8211;4 in the registry</span></span> 
  
1. <span data-ttu-id="9c2ee-187">En el menú **Inicio**, seleccione **Ejecutar**, escriba *regedit* y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-187">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>
  
    <span data-ttu-id="9c2ee-188">Debe tener credenciales de administrador para ejecutar regedit.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-188">You must have administrative credentials to run regedit.</span></span>  

2. <span data-ttu-id="9c2ee-189">En el Editor del Registro, abra la subclave siguiente: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:</span><span class="sxs-lookup"><span data-stu-id="9c2ee-189">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:</span></span>  

    - <span data-ttu-id="9c2ee-190">Para las versiones de .NET Framework de 1.1 a 3.5, cada versión instalada aparece como una subclave bajo la subclave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-190">For .NET Framework versions 1.1 through 3.5, each installed version is listed as a subkey under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP** subkey.</span></span> <span data-ttu-id="9c2ee-191">Por ejemplo, **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-191">For example, **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**.</span></span> <span data-ttu-id="9c2ee-192">El número de versión se almacena como un valor en la entrada **Version** de la subclave de versión.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-192">The version number is stored as a value in the version subkey's **Version** entry.</span></span> 
     
    - <span data-ttu-id="9c2ee-193">Para .NET Framework 4, la entrada **Version** se halla bajo la subclave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client**, bajo la subclave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** o bajo ambas subclaves.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-193">For .NET Framework 4, the **Version** entry is under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client** subkey, the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** subkey, or under both subkeys.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9c2ee-194">La carpeta **NET Framework Setup** del Registro no comienza con un punto.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-194">The **NET Framework Setup** folder in the registry does not begin with a period.</span></span>

    <span data-ttu-id="9c2ee-195">En la siguiente ilustración se muestra la subclave y su entrada **Version** para .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-195">The following figure shows the subkey and its **Version** entry for the .NET Framework 3.5.</span></span>

    <span data-ttu-id="9c2ee-196">![Entrada del Registro de .NET Framework 3.5. ](media/net-4-and-earlier.png ".NET Framework 3.5 y versiones anteriores")</span><span class="sxs-lookup"><span data-stu-id="9c2ee-196">![The registry entry for the .NET Framework 3.5.](media/net-4-and-earlier.png ".NET Framework 3.5 and earlier versions")</span></span>

<a name="net_c"></a> 
### <a name="find-net-framework-versions-182114-with-code"></a><span data-ttu-id="9c2ee-197">Búsqueda de versiones de .NET Framework de 1 a 4 con código</span><span class="sxs-lookup"><span data-stu-id="9c2ee-197">Find .NET Framework versions 1&#8211;4 with code</span></span>

- <span data-ttu-id="9c2ee-198">Use la clase <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> para tener acceso a la subclave **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** en el Registro de Windows.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-198">Use the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** subkey in the Windows registry.</span></span>

<span data-ttu-id="9c2ee-199">En el ejemplo siguiente se buscan las versiones de 1 a 4 de .NET Framework que están instaladas:</span><span class="sxs-lookup"><span data-stu-id="9c2ee-199">The following example finds the .NET Framework 1&#8211;4 versions that are installed:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]


## <a name="find-clr-versions"></a><span data-ttu-id="9c2ee-200">Búsqueda de versiones de CLR</span><span class="sxs-lookup"><span data-stu-id="9c2ee-200">Find CLR versions</span></span>
  
<a name="clr_a"></a> 
### <a name="find-the-current-clr-version-with-clrverexe"></a><span data-ttu-id="9c2ee-201">Búsqueda de la versión actual de CLR con Clrver.exe</span><span class="sxs-lookup"><span data-stu-id="9c2ee-201">Find the current CLR version with Clrver.exe</span></span>

<span data-ttu-id="9c2ee-202">Use la [herramienta de versión de CLR (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) para determinar qué versiones de CLR están instaladas en un equipo:</span><span class="sxs-lookup"><span data-stu-id="9c2ee-202">Use the [CLR Version tool (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) to determine which versions of the CLR are installed on a computer:</span></span>

- <span data-ttu-id="9c2ee-203">En un [Símbolo del sistema para desarrolladores de Visual Studio](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs), escriba `clrver`.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-203">From a [Developer Command Prompt for Visual Studio](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs), enter `clrver`.</span></span>

    <span data-ttu-id="9c2ee-204">Salida de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9c2ee-204">Sample output:</span></span>

    ```console
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

<a name="clr_b"></a> 
### <a name="find-the-current-clr-version-with-the-environment-class"></a><span data-ttu-id="9c2ee-205">Búsqueda de la versión actual de CLR con la clase Environment</span><span class="sxs-lookup"><span data-stu-id="9c2ee-205">Find the current CLR version with the Environment class</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9c2ee-206">Para .NET Framework 4.5 y versiones posteriores, no use la propiedad <xref:System.Environment.Version%2A?displayProperty=nameWithType> para detectar la versión de CLR.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-206">For the .NET Framework 4.5 and later versions, don't use the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to detect the version of the CLR.</span></span> <span data-ttu-id="9c2ee-207">En su lugar, consultar el Registro como se describe en [Búsqueda de versiones de .NET Framework 4.5 y versiones posteriores con código](#net_d).</span><span class="sxs-lookup"><span data-stu-id="9c2ee-207">Instead, query the registry as described in [Find .NET Framework versions 4.5 and later with code](#net_d).</span></span>

1. <span data-ttu-id="9c2ee-208">Consulte la propiedad <xref:System.Environment.Version?displayProperty=nameWithType> para recuperar un objeto <xref:System.Version>.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-208">Query the <xref:System.Environment.Version?displayProperty=nameWithType> property to retrieve a <xref:System.Version> object.</span></span> 

    <span data-ttu-id="9c2ee-209">El objeto `System.Version` devuelto identifica la versión de tiempo de ejecución que está ejecutando el código.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-209">The returned `System.Version` object identifies the version of the runtime that's currently executing the code.</span></span> <span data-ttu-id="9c2ee-210">No devuelve versiones de ensamblado ni otras versiones del runtime que se hayan instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-210">It doesn't return assembly versions or other versions of the runtime that may have been installed on the computer.</span></span>

    <span data-ttu-id="9c2ee-211">Para las versiones 4, 4.5, 4.5.1 y 4.5.2 de .NET Framework, la representación de cadena del objeto <xref:System.Version> devuelto tiene la forma 4.0.30319.*xxxxx*.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-211">For the .NET Framework versions 4, 4.5, 4.5.1, and 4.5.2, the string representation of the returned <xref:System.Version> object has the form 4.0.30319.*xxxxx*.</span></span> <span data-ttu-id="9c2ee-212">Para .NET Framework 4.6 y versiones posteriores, tiene la forma 4.0.30319.42000.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-212">For the .NET Framework 4.6 and later versions, it has the form 4.0.30319.42000.</span></span>    

2. <span data-ttu-id="9c2ee-213">Una vez que tenga el objeto `Version`, consúltelo de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="9c2ee-213">After you have the `Version` object, query it as follows:</span></span>

   - <span data-ttu-id="9c2ee-214">Para el identificador de versión principal (por ejemplo, *4* en la versión 4.0), use la propiedad <xref:System.Version.Major%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-214">For the major release identifier (for example, *4* for version 4.0), use the <xref:System.Version.Major%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="9c2ee-215">Para el identificador de versión secundaria (por ejemplo, *0* en la versión 4.0), use la propiedad <xref:System.Version.Minor%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-215">For the minor release identifier (for example, *0* for version 4.0), use the <xref:System.Version.Minor%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="9c2ee-216">Para la cadena de versión completa (por ejemplo, *4.0.30319.18010*), use el método <xref:System.Version.ToString%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-216">For the entire version string (for example, *4.0.30319.18010*), use the <xref:System.Version.ToString%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9c2ee-217">Este método devuelve un valor único que refleja la versión del runtime que está ejecutando el código.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-217">This method returns a single value that reflects the version of the runtime that's executing the code.</span></span> <span data-ttu-id="9c2ee-218">No devuelve versiones de ensamblado ni otras versiones del runtime que se hayan instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="9c2ee-218">It doesn't return assembly versions or other runtime versions that may be installed on the computer.</span></span>



<span data-ttu-id="9c2ee-219">En el ejemplo siguiente se usa la propiedad <xref:System.Environment.Version%2A?displayProperty=nameWithType> para recuperar la información de la versión de CLR:</span><span class="sxs-lookup"><span data-stu-id="9c2ee-219">The following example uses the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to retrieve CLR version information:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a><span data-ttu-id="9c2ee-220">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c2ee-220">See also</span></span>

- [<span data-ttu-id="9c2ee-221">Cómo: Determinar las actualizaciones de .NET Framework que están instaladas</span><span class="sxs-lookup"><span data-stu-id="9c2ee-221">How to: Determine which .NET Framework updates are installed</span></span>](how-to-determine-which-net-framework-updates-are-installed.md)
- [<span data-ttu-id="9c2ee-222">Instalación de .NET Framework para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="9c2ee-222">Install the .NET Framework for developers</span></span>](../install/guide-for-developers.md)
- [<span data-ttu-id="9c2ee-223">Versiones y dependencias de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9c2ee-223">.NET Framework versions and dependencies</span></span>](versions-and-dependencies.md)

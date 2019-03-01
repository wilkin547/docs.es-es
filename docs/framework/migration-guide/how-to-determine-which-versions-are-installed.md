---
title: Procedimiento para determinar qué versiones de .NET Framework están instaladas
ms.date: 02/20/2019
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
ms.openlocfilehash: d7661b3ebaa8f29d6d3b2adbc56c405c8f0945f3
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56584179"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a><span data-ttu-id="bc9dc-102">Filtrar para determinar qué versiones de .NET Framework están instaladas</span><span class="sxs-lookup"><span data-stu-id="bc9dc-102">How to: Determine which .NET Framework versions are installed</span></span>

<span data-ttu-id="bc9dc-103">Los usuarios pueden instalar y ejecutar varias versiones de .NET Framework en sus equipos.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-103">Users can install and run multiple versions of the .NET Framework on their computers.</span></span> <span data-ttu-id="bc9dc-104">Al desarrollar o implementar una aplicación, puede que necesite conocer las versiones de .NET Framework que están instaladas en el equipo del usuario.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-104">When you develop or deploy your app, you might need to know which .NET Framework versions are installed on the user’s computer.</span></span> <span data-ttu-id="bc9dc-105">.NET Framework está formado por dos componentes principales con versiones separadas:</span><span class="sxs-lookup"><span data-stu-id="bc9dc-105">Note that the .NET Framework consists of two main components, which are versioned separately:</span></span>  
  
- <span data-ttu-id="bc9dc-106">Un conjunto de ensamblados, que son colecciones de tipos y recursos que proporcionan funciones a las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-106">A set of assemblies, which are collections of types and resources that provide the functionality for your apps.</span></span> <span data-ttu-id="bc9dc-107">.NET Framework y los ensamblados comparten el mismo número de versión.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-107">The .NET Framework and assemblies share the same version number.</span></span>  
  
- <span data-ttu-id="bc9dc-108">Common Language Runtime (CLR), que administra y ejecuta el código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-108">The common language runtime (CLR), which manages and executes your app's code.</span></span> <span data-ttu-id="bc9dc-109">El CLR se identifica mediante su propio número de versión (consulte [Versiones y dependencias](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span><span class="sxs-lookup"><span data-stu-id="bc9dc-109">The CLR is identified by its own version number (see [Versions and Dependencies](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span></span>  
  
<span data-ttu-id="bc9dc-110">Para obtener una lista precisa de las versiones de .NET Framework instaladas en un equipo, visualice el Registro o consúltelo mediante código:</span><span class="sxs-lookup"><span data-stu-id="bc9dc-110">To get an accurate list of the .NET Framework versions installed on a computer, you can view the registry or query the registry in code:</span></span>  
  
 [<span data-ttu-id="bc9dc-111">Búsqueda de versiones 1 a 4 de .NET Framework en el Registro</span><span class="sxs-lookup"><span data-stu-id="bc9dc-111">Find .NET Framework versions 1-4 in the registry</span></span>](#net_a)  
 [<span data-ttu-id="bc9dc-112">Búsqueda de versiones de .NET Framework 4.5 y versiones posteriores en el Registro</span><span class="sxs-lookup"><span data-stu-id="bc9dc-112">Find .NET Framework versions 4.5 and later in the registry)</span></span>](#net_b)  
 [<span data-ttu-id="bc9dc-113">Consultar el Registro mediante código (versiones 1 a 4)</span><span class="sxs-lookup"><span data-stu-id="bc9dc-113">Using code to query the registry (versions 1-4)</span></span>](#net_c)  
 [<span data-ttu-id="bc9dc-114">Consultar el Registro mediante código (versión 4.5 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="bc9dc-114">Using code to query the registry (version 4.5 and later)</span></span>](#net_d)  
 [<span data-ttu-id="bc9dc-115">Consultar el Registro mediante PowerShell (versión 4.5 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="bc9dc-115">Using PowerShell to query the registry (version 4.5 and later)</span></span>](#ps_a)  

 <span data-ttu-id="bc9dc-116">Para identificar la versión de CRL puede usar una herramienta o código:</span><span class="sxs-lookup"><span data-stu-id="bc9dc-116">To find the CLR version, you can use a tool or code:</span></span>  
  
 [<span data-ttu-id="bc9dc-117">Uso de la herramienta Clrver</span><span class="sxs-lookup"><span data-stu-id="bc9dc-117">Using the Clrver tool</span></span>](#clr_a)  
 [<span data-ttu-id="bc9dc-118">Uso de código para consultar la clase System.Environment</span><span class="sxs-lookup"><span data-stu-id="bc9dc-118">Using code to query the System.Environment class</span></span>](#clr_b)  

> [!NOTE]
> <span data-ttu-id="bc9dc-119">Hay una diferencia entre la versión de .NET Framework y la versión de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="bc9dc-119">There is a difference between the .NET Framework version and the common language runtime (CLR) version.</span></span> <span data-ttu-id="bc9dc-120">Las versiones de .NET Framework se basan en el conjunto de ensamblados que conforman la biblioteca de clases .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-120">The .NET Framework is versioned based on the set of assemblies that form the .NET Framework Class Library.</span></span> <span data-ttu-id="bc9dc-121">Por ejemplo, las versiones de .NET Framework incluyen 4.5, 4.6.1 y 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-121">For example, .NET Framework versions include 4.5, 4.6.1, and 4.7.2.</span></span> <span data-ttu-id="bc9dc-122">Las versiones de CLR se basan en el entorno de ejecución en el que se ejecutan las aplicaciones .NET Framework, y una única versión de CLR admite normalmente varias versiones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-122">The CLR is versioned based on the runtime on which .NET Framework applications execute, and a single CLR version typically supports multiple .NET Framework versions.</span></span> <span data-ttu-id="bc9dc-123">La versión 4.30319 de CLR *xxxxx* admite las versiones 4 a 4.5.2 de .NET Framework ; la versión de CLR 4.30319.42000 admite las versiones de .NET Framework a partir de .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-123">CLR version 4.30319.*xxxxx* supports .NET Framework versions 4 through 4.5.2; CLR version 4.30319.42000 supports .NET Framework versions starting with .NET Framework 4.6.</span></span> <span data-ttu-id="bc9dc-124">Para obtener más información, vea la propiedad <xref:System.Environment.Version?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-124">For more information, see the <xref:System.Environment.Version?displayProperty=nameWithType> property.</span></span>

 <span data-ttu-id="bc9dc-125">Para obtener información sobre cómo detectar las actualizaciones instaladas de cada versión de .NET Framework, vea [Cómo: Determinar qué actualizaciones de .NET Framework están instaladas](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="bc9dc-125">For information about detecting the installed updates for each version of the .NET Framework, see [How to: Determine Which .NET Framework Updates Are Installed](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md).</span></span> <span data-ttu-id="bc9dc-126">Para obtener información sobre cómo instalar .NET Framework, consulte [Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md) (Instalar .NET Framework para desarrolladores).</span><span class="sxs-lookup"><span data-stu-id="bc9dc-126">For information about installing the .NET Framework, see [Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md).</span></span>  
  
<a name="net_a"></a>   
## <a name="find-net-framework-versions-1-4-in-the-registry"></a><span data-ttu-id="bc9dc-127">Búsqueda de versiones 1 a 4 de .NET Framework en el Registro</span><span class="sxs-lookup"><span data-stu-id="bc9dc-127">Find .NET Framework versions 1-4 in the registry</span></span> 
  
1.  <span data-ttu-id="bc9dc-128">En el menú **Inicio**, elija **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-128">On the **Start** menu, choose **Run**.</span></span>  
  
2.  <span data-ttu-id="bc9dc-129">En el cuadro **Abrir**, escriba **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-129">In the **Open** box, enter **regedit.exe**.</span></span>  
  
     <span data-ttu-id="bc9dc-130">Debe tener credenciales de administrador para ejecutar regedit.exe.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-130">You must have administrative credentials to run regedit.exe.</span></span>  
  
3.  <span data-ttu-id="bc9dc-131">En el Editor del Registro, abra la subclave siguiente:</span><span class="sxs-lookup"><span data-stu-id="bc9dc-131">In the Registry Editor, open the following subkey:</span></span>  
  
     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP`  
  
     <span data-ttu-id="bc9dc-132">Para las versiones 1.1 a 3.5 de .NET Framework, las versiones instaladas se muestran como subclaves en la subclave `NDP`.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-132">For .NET Framework versions 1.1 through 3.5, the installed versions are listed as subkeys under the `NDP` subkey.</span></span> <span data-ttu-id="bc9dc-133">El número de versión se indica en la entrada **Version** de la subclave de versión.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-133">The version number is stored in the version subkey's **Version** entry.</span></span> 
     
     <span data-ttu-id="bc9dc-134">En .NET Framework 4, la entrada **Version** se encuentra en la subclave `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client`, en la subclave `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full` o en ambas.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-134">For .NET Framework 4, the **Version** entry is under the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client` subkey, the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full` subkey, or under both subkeys.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bc9dc-135">La carpeta “NET Framework Setup” del Registro no comienza con un punto.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-135">The "NET Framework Setup" folder in the registry does not begin with a period.</span></span>

    <span data-ttu-id="bc9dc-136">En la siguiente ilustración se muestra la subclave de .NET Framework 3.5, junto con su entrada **Version**.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-136">The following figure shows that the subkey for the .NET Framework 3.5 along with its **Version** entry.</span></span>

     <span data-ttu-id="bc9dc-137">![La entrada del Registro de .NET Framework 3.5. ](../../../docs/framework/migration-guide/media/net-4-and-earlier.png ".NET Framework 4 y versiones anteriores")</span><span class="sxs-lookup"><span data-stu-id="bc9dc-137">![The registry entry for the .NET Framework 3.5.](../../../docs/framework/migration-guide/media/net-4-and-earlier.png ".NET Framework 4 and earlier versions")</span></span>

<a name="net_b"></a> 
## <a name="find-net-framework-versions-45-and-later-in-the-registry"></a><span data-ttu-id="bc9dc-138">Búsqueda de las versiones de .NET Framework 4.5 y versiones posteriores en el Registro</span><span class="sxs-lookup"><span data-stu-id="bc9dc-138">Find .NET Framework versions 4.5 and later in the registry</span></span>

1. <span data-ttu-id="bc9dc-139">En el menú **Inicio**, elija **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-139">On the **Start** menu, choose **Run**.</span></span>

2. <span data-ttu-id="bc9dc-140">En el cuadro **Abrir**, escriba **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-140">In the **Open** box, enter **regedit.exe**.</span></span>

     <span data-ttu-id="bc9dc-141">Debe tener credenciales de administrador para ejecutar regedit.exe.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-141">You must have administrative credentials to run regedit.exe.</span></span>

3. <span data-ttu-id="bc9dc-142">En el Editor del Registro, abra la subclave siguiente:</span><span class="sxs-lookup"><span data-stu-id="bc9dc-142">In the Registry Editor, open the following subkey:</span></span>

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`

     <span data-ttu-id="bc9dc-143">Tenga en cuenta que la ruta de acceso a la subclave `Full` incluye la subclave `Net Framework` en lugar de la `.NET Framework`.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-143">Note that the path to the `Full` subkey includes the subkey `Net Framework` rather than `.NET Framework`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bc9dc-144">Si la subclave `Full` no está presente, significa que .NET Framework 4.5 (o una versión posterior) no está instalado.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-144">If the `Full` subkey is not present, then you do not have the .NET Framework 4.5 or later installed.</span></span>

     <span data-ttu-id="bc9dc-145">Compruebe si existe un valor DWORD denominado `Release`.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-145">Check for a DWORD value named `Release`.</span></span> <span data-ttu-id="bc9dc-146">La existencia del valor DWORD `Release` indica que ya se ha instalado .NET Framework 4.5 o posterior en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-146">The existence of the `Release` DWORD indicates that .NET Framework 4.5 or later has been installed on that computer.</span></span> <span data-ttu-id="bc9dc-147">Su valor es una clave de versión que corresponde a una versión concreta de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-147">Its value is a release key that corresponds to a particular version of .NET Framework.</span></span> <span data-ttu-id="bc9dc-148">En la ilustración siguiente, por ejemplo, el valor DWORD `Release` es 378389, que es la clave de versión de .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-148">In the following figure, for example, the value of the `Release` DWORD is 378389, which is the release key for .NET Framework 4.5.</span></span> 

     <span data-ttu-id="bc9dc-149">![Entrada del Registro para .NET Framework 4.5](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")</span><span class="sxs-lookup"><span data-stu-id="bc9dc-149">![The registry entry for the .NET Framework 4.5.](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")</span></span>

<span data-ttu-id="bc9dc-150">En la tabla siguiente se muestra el valor mínimo del valor DWORD `Release` para cada versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-150">The following table lists the minimum value of the `Release` DWORD for each .NET Framework version.</span></span> <span data-ttu-id="bc9dc-151">Puede usar estos valores de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="bc9dc-151">You can use these values as follows:</span></span>

- <span data-ttu-id="bc9dc-152">Para determinar si existe una versión mínima de .NET Framework, pruebe si el valor DWORD `Release` que se encuentra en el Registro es *mayor o igual que* el valor que aparece en la tabla.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-152">To determine whether a minimum .NET Framework version is present, test whether the `Release` DWORD value found in the registry is *greater than or equal to* the value listed in the table.</span></span> <span data-ttu-id="bc9dc-153">Por ejemplo, si la aplicación requiere .NET Framework 4.7 o versiones posteriores, probaría si el valor de versión mínimo es 460798.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-153">For example, if your application requires .NET Framework 4.7 or later, you would test for a minimum release key value of 460798.</span></span>

- <span data-ttu-id="bc9dc-154">Para probar varias versiones, comience con la versión más reciente de .NET Framework y, luego, pruebe las versiones anteriores sucesivas.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-154">To test for multiple versions, begin with the latest .NET Framework version, and then test for each successive earlier version.</span></span>

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

|<span data-ttu-id="bc9dc-155">Versión de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bc9dc-155">.NET Framework Version</span></span>|<span data-ttu-id="bc9dc-156">Valor DWORD de la versión</span><span class="sxs-lookup"><span data-stu-id="bc9dc-156">Value of the Release DWORD</span></span>|
|--------------------------------|-------------|
|<span data-ttu-id="bc9dc-157">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="bc9dc-157">.NET Framework 4.5</span></span>|<span data-ttu-id="bc9dc-158">378389</span><span class="sxs-lookup"><span data-stu-id="bc9dc-158">378389</span></span>|
|<span data-ttu-id="bc9dc-159">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="bc9dc-159">.NET Framework 4.5.1</span></span>|<span data-ttu-id="bc9dc-160">378675</span><span class="sxs-lookup"><span data-stu-id="bc9dc-160">378675</span></span>|
|<span data-ttu-id="bc9dc-161">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="bc9dc-161">.NET Framework 4.5.2</span></span>|<span data-ttu-id="bc9dc-162">379893</span><span class="sxs-lookup"><span data-stu-id="bc9dc-162">379893</span></span>|
|<span data-ttu-id="bc9dc-163">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="bc9dc-163">.NET Framework 4.6</span></span>|<span data-ttu-id="bc9dc-164">393295</span><span class="sxs-lookup"><span data-stu-id="bc9dc-164">393295</span></span>|
|<span data-ttu-id="bc9dc-165">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="bc9dc-165">.NET Framework 4.6.1</span></span>|<span data-ttu-id="bc9dc-166">394254</span><span class="sxs-lookup"><span data-stu-id="bc9dc-166">394254</span></span>|
|<span data-ttu-id="bc9dc-167">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="bc9dc-167">.NET Framework 4.6.2</span></span>|<span data-ttu-id="bc9dc-168">394802</span><span class="sxs-lookup"><span data-stu-id="bc9dc-168">394802</span></span>|
|<span data-ttu-id="bc9dc-169">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="bc9dc-169">.NET Framework 4.7</span></span>|<span data-ttu-id="bc9dc-170">460798</span><span class="sxs-lookup"><span data-stu-id="bc9dc-170">460798</span></span>|
|<span data-ttu-id="bc9dc-171">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="bc9dc-171">.NET Framework 4.7.1</span></span>|<span data-ttu-id="bc9dc-172">461308</span><span class="sxs-lookup"><span data-stu-id="bc9dc-172">461308</span></span>|
|<span data-ttu-id="bc9dc-173">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="bc9dc-173">.NET Framework 4.7.2</span></span>|<span data-ttu-id="bc9dc-174">461808</span><span class="sxs-lookup"><span data-stu-id="bc9dc-174">461808</span></span>|

<span data-ttu-id="bc9dc-175">Para obtener una tabla completa de claves de versión de .NET Framework para versiones específicas del sistema operativo Windows, consulte [.NET Framework release keys and Windows operating system versions](release-keys-and-os-versions.md) (Claves de versión de .NET Framework y versiones del sistema operativo Windows).</span><span class="sxs-lookup"><span data-stu-id="bc9dc-175">For a complete table of release keys for the .NET Framework for specific Windows operating system versions, see [.NET Framework release keys and Windows operating system versions](release-keys-and-os-versions.md).</span></span>

<a name="net_c"></a> 
## <a name="find-net-framework-versions-1-4-with-code"></a><span data-ttu-id="bc9dc-176">Búsqueda de versiones de .NET Framework 1 a 4 con código</span><span class="sxs-lookup"><span data-stu-id="bc9dc-176">Find .NET Framework versions 1-4 with code</span></span>

- <span data-ttu-id="bc9dc-177">Use la clase <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> para acceder a la subclave `Software\Microsoft\NET Framework Setup\NDP\` en la rama `HKEY_LOCAL_MACHINE` del Registro de Windows.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-177">Use the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the `Software\Microsoft\NET Framework Setup\NDP\` subkey under `HKEY_LOCAL_MACHINE` branch in the Windows registry.</span></span>

     <span data-ttu-id="bc9dc-178">El código siguiente ilustra un ejemplo de esta consulta.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-178">The following code shows an example of this query.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bc9dc-179">Este código no muestra cómo detectar .NET Framework 4.5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-179">This code does not show how to detect .NET Framework 4.5 or later.</span></span> <span data-ttu-id="bc9dc-180">Compruebe el valor DWORD `Release` para detectar estas versiones, tal y como se describe en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-180">Check the `Release` DWORD to detect those versions, as described in the previous section.</span></span> <span data-ttu-id="bc9dc-181">Para información sobre el código que detecta .NET Framework 4.5 o versiones posteriores, consulte la sección siguiente de este artículo.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-181">For code that detects .NET Framework 4.5 or later versions, see the next section in this article.</span></span>

     [!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
     [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

<a name="net_d"></a> 
## <a name="find-net-framework-versions-45-and-later-with-code"></a><span data-ttu-id="bc9dc-182">Búsqueda de versiones de .NET Framework 4.5 y versiones posteriores con código</span><span class="sxs-lookup"><span data-stu-id="bc9dc-182">Find .NET Framework versions 4.5 and later with code</span></span>

1. <span data-ttu-id="bc9dc-183">La existencia del valor DWORD `Release` en la clave `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` indica que ya se ha instalado .NET Framework 4.5 o posterior en un equipo.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-183">The existence of the `Release` DWORD in the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` key indicates that the .NET Framework 4.5 or later is installed on a computer.</span></span> <span data-ttu-id="bc9dc-184">El valor de la palabra clave indica la versión instalada.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-184">The value of the keyword indicates the installed version.</span></span> <span data-ttu-id="bc9dc-185">Para comprobar esta palabra clave, use los métodos <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> y <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> para acceder a la subclave del Registro de Windows.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-185">To check this keyword, use the <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> and <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> methods to access the subkey in the Windows registry.</span></span>

2. <span data-ttu-id="bc9dc-186">Compruebe el valor de la palabra clave `Release` para determinar la versión instalada.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-186">Check the value of the `Release` keyword to determine the installed version.</span></span> <span data-ttu-id="bc9dc-187">Para ser compatible con el reenvío, puede buscar un valor mayor o igual que el valor que aparece en la tabla en la sección [Búsqueda de versiones de .NET Framework 4.5 y versiones posteriores en el Registro](#net_b).</span><span class="sxs-lookup"><span data-stu-id="bc9dc-187">To be forward-compatible, you can check for a value greater than or equal to the value listed in the table in the [Find .NET Framework versions 4.5 and later in the registry](#net_b) section.</span></span>

<span data-ttu-id="bc9dc-188">En el ejemplo siguiente se comprueba el valor `Release` en el Registro para determinar si está instalado .NET Framework o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-188">The following example checks the `Release` value in the registry to determine whether .NET Framework 4.5 or a later version is installed.</span></span>

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

<span data-ttu-id="bc9dc-189">Este ejemplo sigue la práctica recomendada para la comprobación de versión:</span><span class="sxs-lookup"><span data-stu-id="bc9dc-189">This example follows the recommended practice for version checking:</span></span>

- <span data-ttu-id="bc9dc-190">Comprueba si el valor de la entrada `Release` es *mayor o igual que* el valor de las claves conocidas de versión.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-190">It checks whether the value of the `Release` entry is *greater than or equal to* the value of the known release keys.</span></span>

- <span data-ttu-id="bc9dc-191">Realiza la comprobación en orden, desde la versión más reciente hasta la más antigua.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-191">It checks in order from most recent version to earliest version.</span></span>

<a name="ps_a"></a> 
## <a name="check-for-a-minimum-required-net-framework-version-45-and-later-with-powershell"></a><span data-ttu-id="bc9dc-192">Búsqueda de una versión mínima requerida de .NET Framework (4.5 y posterior) con PowerShell</span><span class="sxs-lookup"><span data-stu-id="bc9dc-192">Check for a minimum required .NET Framework version (4.5 and later) with PowerShell</span></span>

<span data-ttu-id="bc9dc-193">En el ejemplo siguiente se comprueba el valor de la palabra clave `Release` para determinar si .NET Framework 4.6.2 o posterior está instalado (si lo está, se devuelve `True`; en caso contrario, `False`).</span><span class="sxs-lookup"><span data-stu-id="bc9dc-193">The following example checks the value of the `Release` keyword to determine whether .NET Framework 4.6.2 or higher is installed (returning `True` if it is and `False` otherwise).</span></span>

    ```PowerShell
    # PowerShell 5
    Get-ChildItem 'HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\' | Get-ItemPropertyValue -Name Release | Foreach-Object { $_ -ge 394802 } 
    ```

    ```PowerShell
    # PowerShell 4
    (Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -gt 394802
    ```

    You can replace `394802` in the previous example with another value from the following table in the [Find .NET Framework versions 4.5 and later in the registry](#net_b) section to check for a different minimum required .NET Framework version.
  
<a name="clr_a"></a> 
## <a name="find-the-current-clr-version-with-clrverexe"></a><span data-ttu-id="bc9dc-194">Búsqueda de la versión actual de CLR con Clrver.exe</span><span class="sxs-lookup"><span data-stu-id="bc9dc-194">Find the current CLR version with Clrver.exe</span></span>

<span data-ttu-id="bc9dc-195">Use la herramienta de versión de CLR (Clrver.exe) para determinar qué versiones de Common Language Runtime (CLR) están instaladas en un equipo.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-195">Use the CLR Version Tool (Clrver.exe) to determine which versions of the common language runtime are installed on a computer.</span></span>

<span data-ttu-id="bc9dc-196">En Símbolo del sistema para desarrolladores de Visual Studio, escriba `clrver`.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-196">From a Developer Command Prompt for Visual Studio, enter `clrver`.</span></span> <span data-ttu-id="bc9dc-197">Este comando produce un resultado similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="bc9dc-197">This command produces output similar to the following:</span></span>

```console
Versions installed on the machine:
v2.0.50727
v4.0.30319
```

<span data-ttu-id="bc9dc-198">Para obtener más información sobre el uso de esta herramienta, consulte [Clrver.exe (herramienta de versión de CLR)](~/docs/framework/tools/clrver-exe-clr-version-tool.md).</span><span class="sxs-lookup"><span data-stu-id="bc9dc-198">For more information about using this tool, see [Clrver.exe (CLR Version Tool)](~/docs/framework/tools/clrver-exe-clr-version-tool.md).</span></span>

<a name="clr_b"></a> 
## <a name="find-the-current-clr-version-with-the-environment-class"></a><span data-ttu-id="bc9dc-199">Búsqueda de la versión actual de CLR con la clase Environment</span><span class="sxs-lookup"><span data-stu-id="bc9dc-199">Find the current CLR version with the Environment class</span></span>

<span data-ttu-id="bc9dc-200">Puede recuperar el valor de la propiedad <xref:System.Environment.Version?displayProperty=nameWithType> para recuperar un objeto <xref:System.Version> que identifica la versión del entorno de ejecución que ejecuta actualmente el código.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-200">You can retrieve the value of the <xref:System.Environment.Version?displayProperty=nameWithType> property to retrieve a <xref:System.Version> object that identifies the version of the runtime that is currently executing the code.</span></span> <span data-ttu-id="bc9dc-201">Esta propiedad devuelve un valor único que refleja la versión del entorno de ejecución que ejecuta actualmente el código; no devuelve versiones de ensamblado ni otras versiones del entorno de ejecución que se puedan haber instalado en el equipo. Puede usar la propiedad <xref:System.Version.Major%2A?displayProperty=nameWithType> para obtener el identificador de versión principal (por ejemplo, "4" para la versión 4.0), la propiedad <xref:System.Version.Minor%2A?displayProperty=nameWithType> para obtener el identificador de versión secundaria (por ejemplo, "0" para la versión 4.0) o el método <xref:System.Version.ToString%2A?displayProperty=nameWithType> para obtener la cadena de versión completa (por ejemplo, "4.0.30319.18010", tal como se muestra en el código siguiente).</span><span class="sxs-lookup"><span data-stu-id="bc9dc-201">This property returns a single value that reflects the version of the runtime that is currently executing the code; it does not return assembly versions or other versions of the runtime that may have been installed on the computer.You can use the <xref:System.Version.Major%2A?displayProperty=nameWithType> property to get the major release identifier (for example, "4" for version 4.0), the <xref:System.Version.Minor%2A?displayProperty=nameWithType> property to get the minor release identifier (for example, "0" for version 4.0), or the <xref:System.Version.ToString%2A?displayProperty=nameWithType> method to get the entire version string (for example, "4.0.30319.18010", as shown in the following code).</span></span> 

<span data-ttu-id="bc9dc-202">Para las versiones 4, 4.5, 4.5.1 y 4.5.2 de .NET Framework, la propiedad <xref:System.Environment.Version%2A?displayProperty=nameWithType> devuelve un objeto <xref:System.Version> cuya representación de cadena tiene la forma `4.0.30319.xxxxx`.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-202">For the .NET Framework Versions 4, 4.5, 4.5.1, and 4.5.2, the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property returns a <xref:System.Version> object whose string representation has the form `4.0.30319.xxxxx`.</span></span> <span data-ttu-id="bc9dc-203">Para .NET Framework 4.6 y posterior, tiene la forma `4.0.30319.42000`.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-203">For the .NET Framework 4.6 and later, it has the form `4.0.30319.42000`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bc9dc-204">Para .NET Framework 4.5 y versiones posteriores, no se recomienda usar la propiedad <xref:System.Environment.Version%2A?displayProperty=nameWithType> para detectar la versión del entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="bc9dc-204">For the .NET Framework 4.5 and later, we do not recommend using the  <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to detect the version of the runtime.</span></span> <span data-ttu-id="bc9dc-205">En su lugar, se recomienda consultar el Registro, como se describe en la sección anterior de este artículo [Para identificar las versiones de .NET Framework con consultas en el Registro mediante código (.NET Framework 4.5 y posterior)](#net_d).</span><span class="sxs-lookup"><span data-stu-id="bc9dc-205">Instead, we recommend that you query the registry, as described in the [To find .NET Framework versions by querying the registry in code (.NET Framework 4.5 and later)](#net_d) section earlier in this article.</span></span>

<span data-ttu-id="bc9dc-206">En el ejemplo siguiente se usa la propiedad <xref:System.Environment.Version%2A?displayProperty=nameWithType> para recuperar la información de la versión del entorno de ejecución:</span><span class="sxs-lookup"><span data-stu-id="bc9dc-206">The following example used the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to retrieve runtime version information:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a><span data-ttu-id="bc9dc-207">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc9dc-207">See also</span></span>

- [<span data-ttu-id="bc9dc-208">Cómo: Determinar qué actualizaciones de .NET Framework están instaladas</span><span class="sxs-lookup"><span data-stu-id="bc9dc-208">How to: Determine Which .NET Framework Updates Are Installed</span></span>](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)
- [<span data-ttu-id="bc9dc-209">Instalación de .NET Framework para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="bc9dc-209">Install the .NET Framework for developers</span></span>](../../../docs/framework/install/guide-for-developers.md)
- [<span data-ttu-id="bc9dc-210">Versiones y dependencias</span><span class="sxs-lookup"><span data-stu-id="bc9dc-210">Versions and Dependencies</span></span>](~/docs/framework/migration-guide/versions-and-dependencies.md)

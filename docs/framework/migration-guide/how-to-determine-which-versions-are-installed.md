---
title: 'Cómo: Determinar qué versiones de .NET Framework están instaladas'
ms.date: 04/10/2018
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
ms.openlocfilehash: 3677ff7cc27847d56802206c793a574d61b1464c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33391643"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a><span data-ttu-id="70155-102">Cómo: Determinar qué versiones de .NET Framework están instaladas</span><span class="sxs-lookup"><span data-stu-id="70155-102">How to: Determine which .NET Framework versions are installed</span></span>

<span data-ttu-id="70155-103">Los usuarios pueden instalar y ejecutar varias versiones de .NET Framework en sus equipos.</span><span class="sxs-lookup"><span data-stu-id="70155-103">Users can install and run multiple versions of the .NET Framework on their computers.</span></span> <span data-ttu-id="70155-104">Al desarrollar o implementar una aplicación, puede que necesite conocer las versiones de .NET Framework que están instaladas en el equipo del usuario.</span><span class="sxs-lookup"><span data-stu-id="70155-104">When you develop or deploy your app, you might need to know which .NET Framework versions are installed on the user’s computer.</span></span> <span data-ttu-id="70155-105">.NET Framework está formado por dos componentes principales con versiones separadas:</span><span class="sxs-lookup"><span data-stu-id="70155-105">Note that the .NET Framework consists of two main components, which are versioned separately:</span></span>  
  
-   <span data-ttu-id="70155-106">Un conjunto de ensamblados, que son colecciones de tipos y recursos que proporcionan funciones a las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="70155-106">A set of assemblies, which are collections of types and resources that provide the functionality for your apps.</span></span> <span data-ttu-id="70155-107">.NET Framework y los ensamblados comparten el mismo número de versión.</span><span class="sxs-lookup"><span data-stu-id="70155-107">The .NET Framework and assemblies share the same version number.</span></span>  
  
-   <span data-ttu-id="70155-108">Common Language Runtime (CLR), que administra y ejecuta el código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="70155-108">The common language runtime (CLR), which manages and executes your app's code.</span></span> <span data-ttu-id="70155-109">El CLR se identifica mediante su propio número de versión (consulte [Versiones y dependencias](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span><span class="sxs-lookup"><span data-stu-id="70155-109">The CLR is identified by its own version number (see [Versions and Dependencies](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span></span>  
  
 <span data-ttu-id="70155-110">Para obtener una lista precisa de las versiones de .NET Framework instaladas en un equipo, visualice el Registro o consúltelo mediante código:</span><span class="sxs-lookup"><span data-stu-id="70155-110">To get an accurate list of the .NET Framework versions installed on a computer, you can view the registry or query the registry in code:</span></span>  
  
 [<span data-ttu-id="70155-111">Ver el Registro (versiones 1 a 4)</span><span class="sxs-lookup"><span data-stu-id="70155-111">Viewing the registry (versions 1-4)</span></span>](#net_a)  
 [<span data-ttu-id="70155-112">Ver el Registro (versión 4.5 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="70155-112">Viewing the registry (version 4.5 and later)</span></span>](#net_b)  
 [<span data-ttu-id="70155-113">Consultar el Registro mediante código (versiones 1 a 4)</span><span class="sxs-lookup"><span data-stu-id="70155-113">Using code to query the registry (versions 1-4)</span></span>](#net_c)  
 [<span data-ttu-id="70155-114">Consultar el Registro mediante código (versión 4.5 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="70155-114">Using code to query the registry (version 4.5 and later)</span></span>](#net_d)  
 [<span data-ttu-id="70155-115">Consultar el Registro mediante PowerShell (versión 4.5 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="70155-115">Using PowerShell to query the registry (version 4.5 and later)</span></span>](#ps_a)  
  
 <span data-ttu-id="70155-116">Para identificar la versión de CRL puede usar una herramienta o código:</span><span class="sxs-lookup"><span data-stu-id="70155-116">To find the CLR version, you can use a tool or code:</span></span>  
  
 [<span data-ttu-id="70155-117">Uso de la herramienta Clrver</span><span class="sxs-lookup"><span data-stu-id="70155-117">Using the Clrver tool</span></span>](#clr_a)  
 [<span data-ttu-id="70155-118">Uso de código para consultar la clase System.Environment</span><span class="sxs-lookup"><span data-stu-id="70155-118">Using code to query the System.Environment class</span></span>](#clr_b)  
  
 <span data-ttu-id="70155-119">Para obtener información sobre cómo detectar las actualizaciones instaladas de cada versión de .NET Framework, vea [Cómo: Determinar qué actualizaciones de .NET Framework están instaladas](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="70155-119">For information about detecting the installed updates for each version of the .NET Framework, see [How to: Determine Which .NET Framework Updates Are Installed](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md).</span></span> <span data-ttu-id="70155-120">Para obtener información sobre cómo instalar .NET Framework, consulte [Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md) (Instalar .NET Framework para desarrolladores).</span><span class="sxs-lookup"><span data-stu-id="70155-120">For information about installing the .NET Framework, see [Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md).</span></span>  
  
<a name="net_a"></a>   
## <a name="to-find-net-framework-versions-by-viewing-the-registry-net-framework-1-4"></a><span data-ttu-id="70155-121">Para identificar las versiones de .NET Framework mediante la visualización del Registro (.NET Framework 1 a 4)</span><span class="sxs-lookup"><span data-stu-id="70155-121">To find .NET Framework versions by viewing the registry (.NET Framework 1-4)</span></span>  
  
1.  <span data-ttu-id="70155-122">En el menú **Inicio**, elija **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="70155-122">On the **Start** menu, choose **Run**.</span></span>  
  
2.  <span data-ttu-id="70155-123">En el cuadro **Abrir**, escriba **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="70155-123">In the **Open** box, enter **regedit.exe**.</span></span>  
  
     <span data-ttu-id="70155-124">Debe tener credenciales de administrador para ejecutar regedit.exe.</span><span class="sxs-lookup"><span data-stu-id="70155-124">You must have administrative credentials to run regedit.exe.</span></span>  
  
3.  <span data-ttu-id="70155-125">En el Editor del Registro, abra la subclave siguiente:</span><span class="sxs-lookup"><span data-stu-id="70155-125">In the Registry Editor, open the following subkey:</span></span>  
  
     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP`  
  
     <span data-ttu-id="70155-126">Las versiones instaladas se muestran bajo la subclave NDP.</span><span class="sxs-lookup"><span data-stu-id="70155-126">The installed versions are listed under the NDP subkey.</span></span> <span data-ttu-id="70155-127">El número de versión se indica en la entrada **Versión**.</span><span class="sxs-lookup"><span data-stu-id="70155-127">The version number is stored in the **Version** entry.</span></span> <span data-ttu-id="70155-128">En [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], la entrada **Versión** está en la subclave Client o Full (en NDP), o en ambas subclaves.</span><span class="sxs-lookup"><span data-stu-id="70155-128">For the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] the **Version** entry is under the Client or Full subkey (under NDP), or under both subkeys.</span></span>  
  

    > [!NOTE]
    > <span data-ttu-id="70155-129">La carpeta “NET Framework Setup” del Registro no comienza con un punto.</span><span class="sxs-lookup"><span data-stu-id="70155-129">The "NET Framework Setup" folder in the registry does not begin with a period.</span></span>

<a name="net_b"></a> 
## <a name="to-find-net-framework-versions-by-viewing-the-registry-net-framework-45-and-later"></a><span data-ttu-id="70155-130">Para identificar las versiones de .NET Framework mediante la visualización del Registro (.NET Framework 4.5 y posterior)</span><span class="sxs-lookup"><span data-stu-id="70155-130">To find .NET Framework versions by viewing the registry (.NET Framework 4.5 and later)</span></span>

1. <span data-ttu-id="70155-131">En el menú **Inicio**, elija **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="70155-131">On the **Start** menu, choose **Run**.</span></span>

2. <span data-ttu-id="70155-132">En el cuadro **Abrir**, escriba **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="70155-132">In the **Open** box, enter **regedit.exe**.</span></span>

     <span data-ttu-id="70155-133">Debe tener credenciales de administrador para ejecutar regedit.exe.</span><span class="sxs-lookup"><span data-stu-id="70155-133">You must have administrative credentials to run regedit.exe.</span></span>

3. <span data-ttu-id="70155-134">En el Editor del Registro, abra la subclave siguiente:</span><span class="sxs-lookup"><span data-stu-id="70155-134">In the Registry Editor, open the following subkey:</span></span>

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`

     <span data-ttu-id="70155-135">Tenga en cuenta que la ruta de acceso a la subclave `Full` incluye la subclave `Net Framework` en lugar de la `.NET Framework`.</span><span class="sxs-lookup"><span data-stu-id="70155-135">Note that the path to the `Full` subkey includes the subkey `Net Framework` rather than `.NET Framework`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="70155-136">Si la subclave `Full` no está presente, significa que .NET Framework 4.5 (o una versión posterior) no está instalado.</span><span class="sxs-lookup"><span data-stu-id="70155-136">If the `Full` subkey is not present, then you do not have the .NET Framework 4.5 or later installed.</span></span>

     <span data-ttu-id="70155-137">Compruebe si existe un valor DWORD denominado `Release`.</span><span class="sxs-lookup"><span data-stu-id="70155-137">Check for a DWORD value named `Release`.</span></span> <span data-ttu-id="70155-138">La existencia de un valor DWORD `Release` indica que en ese equipo está instalado [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o una versión anterior.</span><span class="sxs-lookup"><span data-stu-id="70155-138">The existence of the `Release` DWORD indicates that the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or newer has been installed on that computer.</span></span>

     <span data-ttu-id="70155-139">![Entrada del Registro para .NET Framework 4.5](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")</span><span class="sxs-lookup"><span data-stu-id="70155-139">![The registry entry for the .NET Framework 4.5.](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")</span></span>

     <span data-ttu-id="70155-140">El valor DWORD `Release` indica qué versión de .NET Framework está instalada.</span><span class="sxs-lookup"><span data-stu-id="70155-140">The value of the `Release` DWORD indicates which version of the .NET Framework is installed.</span></span>

    [!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

    |<span data-ttu-id="70155-141">Valor DWORD de la versión</span><span class="sxs-lookup"><span data-stu-id="70155-141">Value of the Release DWORD</span></span>|<span data-ttu-id="70155-142">Versión</span><span class="sxs-lookup"><span data-stu-id="70155-142">Version</span></span>|
    |--------------------------------|-------------|
    |<span data-ttu-id="70155-143">378389</span><span class="sxs-lookup"><span data-stu-id="70155-143">378389</span></span>|<span data-ttu-id="70155-144">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="70155-144">.NET Framework 4.5</span></span>|
    |<span data-ttu-id="70155-145">378675</span><span class="sxs-lookup"><span data-stu-id="70155-145">378675</span></span>|<span data-ttu-id="70155-146">.NET Framework 4.5.1 instalado con Windows 8.1 o Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="70155-146">.NET Framework 4.5.1 installed with Windows 8.1 or Windows Server 2012 R2</span></span>|
    |<span data-ttu-id="70155-147">378758</span><span class="sxs-lookup"><span data-stu-id="70155-147">378758</span></span>|<span data-ttu-id="70155-148">.NET Framework 4.5.1 instalado en Windows 8, Windows 7 SP1 o Windows Vista SP2</span><span class="sxs-lookup"><span data-stu-id="70155-148">.NET Framework 4.5.1 installed on Windows 8, Windows 7 SP1, or Windows Vista SP2</span></span>|
    |<span data-ttu-id="70155-149">379893</span><span class="sxs-lookup"><span data-stu-id="70155-149">379893</span></span>|<span data-ttu-id="70155-150">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="70155-150">.NET Framework 4.5.2</span></span>|
    |<span data-ttu-id="70155-151">Solo en sistemas Windows 10: 393295</span><span class="sxs-lookup"><span data-stu-id="70155-151">On Windows 10 systems only: 393295</span></span><br /><br /> <span data-ttu-id="70155-152">En las demás versiones de sistema operativo: 393297</span><span class="sxs-lookup"><span data-stu-id="70155-152">On all other OS versions: 393297</span></span>|[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]|
    |<span data-ttu-id="70155-153">Solo en sistemas con la actualización de noviembre de Windows 10: 394254</span><span class="sxs-lookup"><span data-stu-id="70155-153">On Windows 10 November Update systems only: 394254</span></span><br /><br /> <span data-ttu-id="70155-154">En las demás versiones del sistema operativo: 394271</span><span class="sxs-lookup"><span data-stu-id="70155-154">On all other OS versions: 394271</span></span>|[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]|
    |<span data-ttu-id="70155-155">Solo en la actualización de aniversario de Windows 10: 394802</span><span class="sxs-lookup"><span data-stu-id="70155-155">On Windows 10 Anniversary Update only: 394802</span></span><br /><br /> <span data-ttu-id="70155-156">En las demás versiones del sistema operativo: 394806</span><span class="sxs-lookup"><span data-stu-id="70155-156">On all other OS versions: 394806</span></span>|[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]| 
    |<span data-ttu-id="70155-157">Solo en Windows 10 Creators Update: 460798</span><span class="sxs-lookup"><span data-stu-id="70155-157">On Windows 10 Creators Update only: 460798</span></span><br/><br/> <span data-ttu-id="70155-158">En las demás versiones de sistema operativo: 460805</span><span class="sxs-lookup"><span data-stu-id="70155-158">On all other OS versions: 460805</span></span> | <span data-ttu-id="70155-159">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="70155-159">.NET Framework 4.7</span></span> |
    |<span data-ttu-id="70155-160">Solo en Windows 10 Fall Creators Update: 461308</span><span class="sxs-lookup"><span data-stu-id="70155-160">On Windows 10 Fall Creators Update only: 461308</span></span><br/><br/> <span data-ttu-id="70155-161">En las demás versiones del sistema operativo: 461310</span><span class="sxs-lookup"><span data-stu-id="70155-161">On all other OS versions: 461310</span></span> | <span data-ttu-id="70155-162">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="70155-162">.NET Framework 4.7.1</span></span> |
    |<span data-ttu-id="70155-163">Solo en la Actualización de abril de 2018 de Windows 10: 461808</span><span class="sxs-lookup"><span data-stu-id="70155-163">On Windows 10 April 2018 Update only: 461808</span></span><br/><br/> <span data-ttu-id="70155-164">En las demás versiones del sistema operativo: 461814</span><span class="sxs-lookup"><span data-stu-id="70155-164">On all other OS versions: 461814</span></span>| <span data-ttu-id="70155-165">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="70155-165">.NET Framework 4.7.2</span></span> |
    
<a name="net_c"></a> 
## <a name="to-find-net-framework-versions-by-querying-the-registry-in-code-net-framework-1-4"></a><span data-ttu-id="70155-166">Para identificar las versiones de .NET Framework con consultas en el Registro mediante código (.NET Framework 1 a 4)</span><span class="sxs-lookup"><span data-stu-id="70155-166">To find .NET Framework versions by querying the registry in code (.NET Framework 1-4)</span></span>

- <span data-ttu-id="70155-167">Utilice la clase <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> para tener acceso a la subclave Software\Microsoft\NET Framework Setup\NDP\ en HKEY_LOCAL_MACHINE en el Registro de Windows.</span><span class="sxs-lookup"><span data-stu-id="70155-167">Use the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the Software\Microsoft\NET Framework Setup\NDP\ subkey under HKEY_LOCAL_MACHINE in the Windows registry.</span></span>

     <span data-ttu-id="70155-168">El código siguiente ilustra un ejemplo de esta consulta.</span><span class="sxs-lookup"><span data-stu-id="70155-168">The following code shows an example of this query.</span></span>

    > [!NOTE]
    > <span data-ttu-id="70155-169">En este código no se muestra cómo detectar [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="70155-169">This code does not show how to detect the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or later.</span></span> <span data-ttu-id="70155-170">Compruebe el valor DWORD `Release` para detectar estas versiones, tal y como se describe en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="70155-170">Check the `Release` DWORD to detect those versions, as described in the previous section.</span></span> <span data-ttu-id="70155-171">Puede consultar el código que sí detecta [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o versiones posteriores en la sección siguiente de este artículo.</span><span class="sxs-lookup"><span data-stu-id="70155-171">For code that does detect the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or later versions, see the next section in this article.</span></span>

     [!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
     [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

     <span data-ttu-id="70155-172">El ejemplo genera un resultado similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="70155-172">The example produces output that's similar to the following:</span></span>

    ```
    v2.0.50727  2.0.50727.4016  SP2
    v3.0  3.0.30729.4037  SP2
    v3.5  3.5.30729.01  SP1
    v4
      Client  4.0.30319
      Full  4.0.30319
    ```

<a name="net_d"></a> 
## <a name="to-find-net-framework-versions-by-querying-the-registry-in-code-net-framework-45-and-later"></a><span data-ttu-id="70155-173">Para identificar las versiones de .NET Framework con consultas en el Registro mediante código (.NET Framework 4.5 y posterior)</span><span class="sxs-lookup"><span data-stu-id="70155-173">To find .NET Framework versions by querying the registry in code (.NET Framework 4.5 and later)</span></span>

1. <span data-ttu-id="70155-174">La existencia de un valor DWORD `Release` indica que ya se ha instalado .NET Framework 4.5 o posterior en un equipo.</span><span class="sxs-lookup"><span data-stu-id="70155-174">The existence of the `Release` DWORD indicates that the .NET Framework 4.5 or later has been installed on a computer.</span></span> <span data-ttu-id="70155-175">El valor de la palabra clave indica la versión instalada.</span><span class="sxs-lookup"><span data-stu-id="70155-175">The value of the keyword indicates the installed version.</span></span> <span data-ttu-id="70155-176">Para comprobar esta palabra clave, use los métodos <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A> y <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> de la clase <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> para obtener acceso a la subclave Software\Microsoft\NET Framework Setup\NDP\v4\Full, en HKEY_LOCAL_MACHINE, del Registro de Windows.</span><span class="sxs-lookup"><span data-stu-id="70155-176">To check this keyword, use the <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A> and <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> methods of the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the Software\Microsoft\NET Framework Setup\NDP\v4\Full subkey under HKEY_LOCAL_MACHINE in the Windows registry.</span></span>

2. <span data-ttu-id="70155-177">Compruebe el valor de la palabra clave `Release` para determinar la versión instalada.</span><span class="sxs-lookup"><span data-stu-id="70155-177">Check the value of the `Release` keyword to determine the installed version.</span></span> <span data-ttu-id="70155-178">Para que sea compatible con el reenvío, puede buscar un valor mayor o igual que los valores que se muestran en la tabla.</span><span class="sxs-lookup"><span data-stu-id="70155-178">To be forward-compatible, you can check for a value greater than or equal to the values listed in the table.</span></span> <span data-ttu-id="70155-179">Estas son las versiones de .NET Framework y las palabras clave de `Release` asociadas.</span><span class="sxs-lookup"><span data-stu-id="70155-179">Here are the .NET Framework versions and associated `Release` keywords.</span></span>

    [!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

    |<span data-ttu-id="70155-180">Versión</span><span class="sxs-lookup"><span data-stu-id="70155-180">Version</span></span>|<span data-ttu-id="70155-181">Valor DWORD de la versión</span><span class="sxs-lookup"><span data-stu-id="70155-181">Value of the Release DWORD</span></span>|
    |-------------|--------------------------------|
    |<span data-ttu-id="70155-182">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="70155-182">.NET Framework 4.5</span></span>|<span data-ttu-id="70155-183">378389</span><span class="sxs-lookup"><span data-stu-id="70155-183">378389</span></span>|
    |<span data-ttu-id="70155-184">.NET Framework 4.5.1 instalado con Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="70155-184">.NET Framework 4.5.1 installed with Windows 8.1</span></span>|<span data-ttu-id="70155-185">378675</span><span class="sxs-lookup"><span data-stu-id="70155-185">378675</span></span>|
    |<span data-ttu-id="70155-186">.NET Framework 4.5.1 instalado en Windows 8, Windows 7 SP1 o Windows Vista SP2</span><span class="sxs-lookup"><span data-stu-id="70155-186">.NET Framework 4.5.1 installed on Windows 8, Windows 7 SP1, or Windows Vista SP2</span></span>|<span data-ttu-id="70155-187">378758</span><span class="sxs-lookup"><span data-stu-id="70155-187">378758</span></span>|
    |<span data-ttu-id="70155-188">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="70155-188">.NET Framework 4.5.2</span></span>|<span data-ttu-id="70155-189">379893</span><span class="sxs-lookup"><span data-stu-id="70155-189">379893</span></span>|
    |<span data-ttu-id="70155-190">.NET Framework 4.6 instalado con Windows 10</span><span class="sxs-lookup"><span data-stu-id="70155-190">.NET Framework 4.6 installed with Windows 10</span></span>|<span data-ttu-id="70155-191">393295</span><span class="sxs-lookup"><span data-stu-id="70155-191">393295</span></span>|
    |<span data-ttu-id="70155-192">.NET Framework 4.6 instalado en las demás versiones del sistema operativo Windows</span><span class="sxs-lookup"><span data-stu-id="70155-192">.NET Framework 4.6 installed on all other Windows OS versions</span></span>|<span data-ttu-id="70155-193">393297</span><span class="sxs-lookup"><span data-stu-id="70155-193">393297</span></span>|
    |<span data-ttu-id="70155-194">.NET Framework 4.6.1 instalado en Windows 10</span><span class="sxs-lookup"><span data-stu-id="70155-194">.NET Framework 4.6.1 installed on Windows 10</span></span>|<span data-ttu-id="70155-195">394254</span><span class="sxs-lookup"><span data-stu-id="70155-195">394254</span></span>|
    |<span data-ttu-id="70155-196">.NET Framework 4.6.1 instalado en las demás versiones del sistema operativo Windows</span><span class="sxs-lookup"><span data-stu-id="70155-196">.NET Framework 4.6.1 installed on all other Windows OS versions</span></span>|<span data-ttu-id="70155-197">394271</span><span class="sxs-lookup"><span data-stu-id="70155-197">394271</span></span>|
    |<span data-ttu-id="70155-198">.NET Framework 4.6.2 instalado en la Actualización de aniversario de Windows 10</span><span class="sxs-lookup"><span data-stu-id="70155-198">.NET Framework 4.6.2 installed on Windows 10 Anniversary Update</span></span>|<span data-ttu-id="70155-199">394802</span><span class="sxs-lookup"><span data-stu-id="70155-199">394802</span></span>|
    |<span data-ttu-id="70155-200">.NET Framework 4.6.2 instalado en las demás versiones del sistema operativo Windows</span><span class="sxs-lookup"><span data-stu-id="70155-200">.NET Framework 4.6.2 installed on all other Windows OS versions</span></span>|<span data-ttu-id="70155-201">394806</span><span class="sxs-lookup"><span data-stu-id="70155-201">394806</span></span>|
    |<span data-ttu-id="70155-202">.NET Framework 4.7 instalado en Windows 10 Creators Update</span><span class="sxs-lookup"><span data-stu-id="70155-202">.NET Framework 4.7 installed on Windows 10 Creators Update</span></span>|<span data-ttu-id="70155-203">460798</span><span class="sxs-lookup"><span data-stu-id="70155-203">460798</span></span>|
    |<span data-ttu-id="70155-204">.NET Framework 4.7 instalado en las demás versiones del sistema operativo Windows</span><span class="sxs-lookup"><span data-stu-id="70155-204">.NET Framework 4.7 installed on all other Windows OS versions</span></span>|<span data-ttu-id="70155-205">460805</span><span class="sxs-lookup"><span data-stu-id="70155-205">460805</span></span>|
    |<span data-ttu-id="70155-206">.NET Framework 4.7.1 instalado en Windows 10 Fall Creators Update</span><span class="sxs-lookup"><span data-stu-id="70155-206">.NET Framework 4.7.1 installed on Windows 10 Fall Creators Update</span></span>|<span data-ttu-id="70155-207">461308</span><span class="sxs-lookup"><span data-stu-id="70155-207">461308</span></span>|
    |<span data-ttu-id="70155-208">.NET Framework 4.7.1 instalado en las demás versiones del sistema operativo Windows</span><span class="sxs-lookup"><span data-stu-id="70155-208">.NET Framework 4.7.1 installed on all other Windows OS versions</span></span>|<span data-ttu-id="70155-209">461310</span><span class="sxs-lookup"><span data-stu-id="70155-209">461310</span></span>|
    |<span data-ttu-id="70155-210">.NET Framework 4.7.2 instalado en la Actualización de abril de 2018 de Windows 10</span><span class="sxs-lookup"><span data-stu-id="70155-210">.NET Framework 4.7.2 installed on Windows 10 April 2018 Update</span></span>|<span data-ttu-id="70155-211">461808</span><span class="sxs-lookup"><span data-stu-id="70155-211">461808</span></span>|
    |<span data-ttu-id="70155-212">.NET Framework 4.7.2 instalado en las demás versiones del sistema operativo Windows</span><span class="sxs-lookup"><span data-stu-id="70155-212">.NET Framework 4.7.2 installed on all other Windows OS versions</span></span>|<span data-ttu-id="70155-213">461814</span><span class="sxs-lookup"><span data-stu-id="70155-213">461814</span></span>|
    
     <span data-ttu-id="70155-214">El ejemplo siguiente comprueba el valor `Release` en el Registro para determinar si [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o una versión posterior de .NET Framework está instalada.</span><span class="sxs-lookup"><span data-stu-id="70155-214">The following example checks the `Release` value in the registry to determine whether the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or a later version of the .NET Framework is installed.</span></span>

     [!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
     [!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

     <span data-ttu-id="70155-215">Este ejemplo sigue la práctica recomendada para la comprobación de versión:</span><span class="sxs-lookup"><span data-stu-id="70155-215">This example follows the recommended practice for version checking:</span></span>

    - <span data-ttu-id="70155-216">Comprueba si el valor de la entrada `Release` es *mayor o igual que* el valor de las claves conocidas de versión.</span><span class="sxs-lookup"><span data-stu-id="70155-216">It checks whether the value of the `Release` entry is *greater than or equal to* the value of the known release keys.</span></span>

    - <span data-ttu-id="70155-217">Realiza la comprobación en orden, desde la versión más reciente hasta la más antigua.</span><span class="sxs-lookup"><span data-stu-id="70155-217">It checks in order from most recent version to earliest version.</span></span>

<a name="ps_a"></a> 
## <a name="to-check-for-a-minimum-required-net-framework-version-by-querying-the-registry-in-powershell-net-framework-45-and-later"></a><span data-ttu-id="70155-218">Comprobación de una versión mínima requerida de .NET Framework realizando una consulta al registro en PowerShell (.NET Framework 4.5 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="70155-218">To check for a minimum-required .NET Framework version by querying the registry in PowerShell (.NET Framework 4.5 and later)</span></span>

- <span data-ttu-id="70155-219">En el ejemplo siguiente se comprueba el valor de la palabra clave `Release` para determinar si .NET Framework 4.6.2 o posterior está instalado, independientemente de la versión del sistema operativo Windows (se devolverá `True` si es así o `False` en caso contrario).</span><span class="sxs-lookup"><span data-stu-id="70155-219">The following example checks the value of the `Release` keyword to determine whether .NET Framework 4.6.2 or higher is installed, regardless of Windows OS version (returning `True` if it is and `False` otherwise).</span></span>

    ```PowerShell
    Get-ChildItem "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\" | Get-ItemPropertyValue -Name Release | ForEach-Object { $_ -ge 394802 } 
    ```

    <span data-ttu-id="70155-220">Puede reemplazar `394802` en el ejemplo anterior con otro valor de la tabla siguiente para comprobar si hay otra versión de .NET Framework mínima requerida.</span><span class="sxs-lookup"><span data-stu-id="70155-220">You can replace `394802` in the previous example with another value from the following table to check for a different minimum-required .NET Framework version.</span></span>
  
    |<span data-ttu-id="70155-221">Versión</span><span class="sxs-lookup"><span data-stu-id="70155-221">Version</span></span>|<span data-ttu-id="70155-222">Valor mínimo de DWORD de la versión</span><span class="sxs-lookup"><span data-stu-id="70155-222">Minimum value of the Release DWORD</span></span>|
    |-------------|--------------------------------|
    |<span data-ttu-id="70155-223">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="70155-223">.NET Framework 4.5</span></span>|<span data-ttu-id="70155-224">378389</span><span class="sxs-lookup"><span data-stu-id="70155-224">378389</span></span>|
    |<span data-ttu-id="70155-225">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="70155-225">.NET Framework 4.5.1</span></span>|<span data-ttu-id="70155-226">378675</span><span class="sxs-lookup"><span data-stu-id="70155-226">378675</span></span>|
    |<span data-ttu-id="70155-227">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="70155-227">.NET Framework 4.5.2</span></span>|<span data-ttu-id="70155-228">379893</span><span class="sxs-lookup"><span data-stu-id="70155-228">379893</span></span>|
    |[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]|<span data-ttu-id="70155-229">393295</span><span class="sxs-lookup"><span data-stu-id="70155-229">393295</span></span>|
    |[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]|<span data-ttu-id="70155-230">394254</span><span class="sxs-lookup"><span data-stu-id="70155-230">394254</span></span>|
    |[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]|<span data-ttu-id="70155-231">394802</span><span class="sxs-lookup"><span data-stu-id="70155-231">394802</span></span>|
    |<span data-ttu-id="70155-232">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="70155-232">.NET Framework 4.7</span></span>|<span data-ttu-id="70155-233">460798</span><span class="sxs-lookup"><span data-stu-id="70155-233">460798</span></span>|
    |<span data-ttu-id="70155-234">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="70155-234">.NET Framework 4.7.1</span></span>|<span data-ttu-id="70155-235">461308</span><span class="sxs-lookup"><span data-stu-id="70155-235">461308</span></span>|
    |<span data-ttu-id="70155-236">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="70155-236">.NET Framework 4.7.2</span></span>|<span data-ttu-id="70155-237">461808</span><span class="sxs-lookup"><span data-stu-id="70155-237">461808</span></span>|

<a name="clr_a"></a> 
## <a name="to-find-the-current-runtime-version-by-using-the-clrver-tool"></a><span data-ttu-id="70155-238">Para identificar la versión de runtime actual mediante la herramienta Clrver</span><span class="sxs-lookup"><span data-stu-id="70155-238">To find the current runtime version by using the Clrver tool</span></span>

- <span data-ttu-id="70155-239">Use la herramienta de versión de CLR (Clrver.exe) para determinar qué versiones de Common Language Runtime (CLR) están instaladas en un equipo.</span><span class="sxs-lookup"><span data-stu-id="70155-239">Use the CLR Version Tool (Clrver.exe) to determine which versions of the common language runtime are installed on a computer.</span></span>

     <span data-ttu-id="70155-240">En un símbolo del sistema de Visual Studio, escriba `clrver`.</span><span class="sxs-lookup"><span data-stu-id="70155-240">From a Visual Studio Command Prompt, enter `clrver`.</span></span> <span data-ttu-id="70155-241">Este comando produce un resultado similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="70155-241">This command produces output similar to the following:</span></span>

    ```
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

     <span data-ttu-id="70155-242">Para obtener más información sobre el uso de esta herramienta, consulte [Clrver.exe (herramienta de versión de CLR)](~/docs/framework/tools/clrver-exe-clr-version-tool.md).</span><span class="sxs-lookup"><span data-stu-id="70155-242">For more information about using this tool, see [Clrver.exe (CLR Version Tool)](~/docs/framework/tools/clrver-exe-clr-version-tool.md).</span></span>

<a name="clr_b"></a> 
## <a name="to-find-the-current-runtime-version-by-querying-the-environment-class-in-code"></a><span data-ttu-id="70155-243">Para buscar la versión de runtime actual consultando la clase Environment en el código</span><span class="sxs-lookup"><span data-stu-id="70155-243">To find the current runtime version by querying the Environment class in code</span></span>

- <span data-ttu-id="70155-244">Consulte la propiedad <xref:System.Environment.Version%2A?displayProperty=nameWithType> para recuperar un objeto <xref:System.Version> que identifique la versión de tiempo de ejecución que está ejecutando el código.</span><span class="sxs-lookup"><span data-stu-id="70155-244">Query the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to retrieve a <xref:System.Version> object that identifies the version of the runtime that is currently executing the code.</span></span> <span data-ttu-id="70155-245">Puede utilizar la propiedad <xref:System.Version.Major%2A?displayProperty=nameWithType> para obtener el identificador de versión principal (por ejemplo, "4" para la versión 4,0), la propiedad <xref:System.Version.Minor%2A?displayProperty=nameWithType> para obtener el identificador de versión secundaria (por ejemplo, "0" para la versión 4,0) o el método <xref:System.Object.ToString%2A?displayProperty=nameWithType> para obtener la cadena completa de la versión (por ejemplo, "4.0.30319.18010", como se muestra en el código siguiente).</span><span class="sxs-lookup"><span data-stu-id="70155-245">You can use the <xref:System.Version.Major%2A?displayProperty=nameWithType> property to get the major release identifier (for example, "4" for version 4.0), the <xref:System.Version.Minor%2A?displayProperty=nameWithType> property to get the minor release identifier (for example, "0" for version 4.0), or the <xref:System.Object.ToString%2A?displayProperty=nameWithType> method to get the entire version string (for example, "4.0.30319.18010", as shown in the following code).</span></span> <span data-ttu-id="70155-246">Esta propiedad devuelve un valor único que refleja la versión del runtime que está ejecutando el código actualmente; no devuelve versiones de ensamblado ni otras versiones del runtime que se hayan podido instalar en el equipo.</span><span class="sxs-lookup"><span data-stu-id="70155-246">This property returns a single value that reflects the version of the runtime that is currently executing the code; it does not return assembly versions or other versions of the runtime that may have been installed on the computer.</span></span>

     <span data-ttu-id="70155-247">Para las versiones 4, 4.5, 4.5.1 y 4.5.2 de .NET Framework, la propiedad <xref:System.Environment.Version%2A?displayProperty=nameWithType> devuelve un objeto <xref:System.Version> cuya representación de cadena tiene la forma `4.0.30319.xxxxx`.</span><span class="sxs-lookup"><span data-stu-id="70155-247">For the .NET Framework Versions 4, 4.5, 4.5.1, and 4.5.2, the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property returns a <xref:System.Version> object whose string representation has the form `4.0.30319.xxxxx`.</span></span> <span data-ttu-id="70155-248">Para .NET Framework 4.6 y posterior, tiene la forma `4.0.30319.42000`.</span><span class="sxs-lookup"><span data-stu-id="70155-248">For the .NET Framework 4.6 and later, it has the form `4.0.30319.42000`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="70155-249">Para [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] y versiones posteriores, no se recomienda usar la propiedad <xref:System.Environment.Version%2A?displayProperty=nameWithType> para detectar la versión del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="70155-249">For the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] and later, we do not recommend using the  <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to detect the version of the runtime.</span></span> <span data-ttu-id="70155-250">En su lugar, se recomienda consultar el Registro, como se describe en la sección anterior de este artículo [Para identificar las versiones de .NET Framework con consultas en el Registro mediante código (.NET Framework 4.5 y posterior)](#net_d).</span><span class="sxs-lookup"><span data-stu-id="70155-250">Instead, we recommend that you query the registry, as described in the [To find .NET Framework versions by querying the registry in code (.NET Framework 4.5 and later)](#net_d) section earlier in this article.</span></span>

     <span data-ttu-id="70155-251">A continuación se muestra un ejemplo de cómo consultar la propiedad <xref:System.Environment.Version%2A?displayProperty=nameWithType> para obtener información de la versión del runtime:</span><span class="sxs-lookup"><span data-stu-id="70155-251">Here's an example of querying the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property for runtime version information:</span></span>

     [!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
     [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

     <span data-ttu-id="70155-252">El ejemplo genera un resultado similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="70155-252">The example produces output that's similar to the following:</span></span>

    ```
    Version: 4.0.30319.18010
    ```

## <a name="see-also"></a><span data-ttu-id="70155-253">Vea también</span><span class="sxs-lookup"><span data-stu-id="70155-253">See also</span></span>

[<span data-ttu-id="70155-254">Determinar qué actualizaciones de .NET Framework están instaladas</span><span class="sxs-lookup"><span data-stu-id="70155-254">How to: Determine Which .NET Framework Updates Are Installed</span></span>](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)  
[<span data-ttu-id="70155-255">Instalación de .NET Framework para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="70155-255">Install the .NET Framework for developers</span></span>](../../../docs/framework/install/guide-for-developers.md)  
[<span data-ttu-id="70155-256">Versiones y dependencias</span><span class="sxs-lookup"><span data-stu-id="70155-256">Versions and Dependencies</span></span>](~/docs/framework/migration-guide/versions-and-dependencies.md)  

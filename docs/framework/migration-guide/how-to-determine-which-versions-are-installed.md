---
title: "Cómo: Determinar qué versiones de .NET Framework están instaladas"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- versions, determining for .NET Framework
- .NET Framework, determining version
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
caps.latest.revision: 62
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: cddee407d1245568054871d71f2840f463859535
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a><span data-ttu-id="5448c-102">Cómo: Determinar qué versiones de .NET Framework están instaladas</span><span class="sxs-lookup"><span data-stu-id="5448c-102">How to: Determine Which .NET Framework Versions Are Installed</span></span>
<span data-ttu-id="5448c-103">Los usuarios pueden instalar y ejecutar varias versiones de .NET Framework en sus equipos.</span><span class="sxs-lookup"><span data-stu-id="5448c-103">Users can install and run multiple versions of the .NET Framework on their computers.</span></span> <span data-ttu-id="5448c-104">Al desarrollar o implementar una aplicación, puede que necesite conocer las versiones de .NET Framework que están instaladas en el equipo del usuario.</span><span class="sxs-lookup"><span data-stu-id="5448c-104">When you develop or deploy your app, you might need to know which .NET Framework versions are installed on the user’s computer.</span></span> <span data-ttu-id="5448c-105">.NET Framework está formado por dos componentes principales con versiones separadas:</span><span class="sxs-lookup"><span data-stu-id="5448c-105">Note that the .NET Framework consists of two main components, which are versioned separately:</span></span>  
  
-   <span data-ttu-id="5448c-106">Un conjunto de ensamblados, que son colecciones de tipos y recursos que proporcionan funciones a las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="5448c-106">A set of assemblies, which are collections of types and resources that provide the functionality for your apps.</span></span> <span data-ttu-id="5448c-107">.NET Framework y los ensamblados comparten el mismo número de versión.</span><span class="sxs-lookup"><span data-stu-id="5448c-107">The .NET Framework and assemblies share the same version number.</span></span>  
  
-   <span data-ttu-id="5448c-108">Common Language Runtime (CLR), que administra y ejecuta el código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5448c-108">The common language runtime (CLR), which manages and executes your app's code.</span></span> <span data-ttu-id="5448c-109">El CLR se identifica mediante su propio número de versión (consulte [Versiones y dependencias](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span><span class="sxs-lookup"><span data-stu-id="5448c-109">The CLR is identified by its own version number (see [Versions and Dependencies](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span></span>  
  
 <span data-ttu-id="5448c-110">Para obtener una lista precisa de las versiones de .NET Framework instaladas en un equipo, visualice el Registro o consúltelo mediante código:</span><span class="sxs-lookup"><span data-stu-id="5448c-110">To get an accurate list of the .NET Framework versions installed on a computer, you can view the registry or query the registry in code:</span></span>  
  
 [<span data-ttu-id="5448c-111">Ver el Registro (versiones 1 a 4)</span><span class="sxs-lookup"><span data-stu-id="5448c-111">Viewing the registry (versions 1-4)</span></span>](#net_a)  
 [<span data-ttu-id="5448c-112">Ver el Registro (versión 4.5 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="5448c-112">Viewing the registry (version 4.5 and later)</span></span>](#net_b)  
 [<span data-ttu-id="5448c-113">Consultar el Registro mediante código (versiones 1 a 4)</span><span class="sxs-lookup"><span data-stu-id="5448c-113">Using code to query the registry (versions 1-4)</span></span>](#net_c)  
 [<span data-ttu-id="5448c-114">Consultar el Registro mediante código (versión 4.5 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="5448c-114">Using code to query the registry (version 4.5 and later)</span></span>](#net_d)  
  
 <span data-ttu-id="5448c-115">Para identificar la versión de CRL puede usar una herramienta o código:</span><span class="sxs-lookup"><span data-stu-id="5448c-115">To find the CLR version, you can use a tool or code:</span></span>  
  
 [<span data-ttu-id="5448c-116">Uso de la herramienta Clrver</span><span class="sxs-lookup"><span data-stu-id="5448c-116">Using the Clrver tool</span></span>](#clr_a)  
 [<span data-ttu-id="5448c-117">Uso de código para consultar la clase System.Environment</span><span class="sxs-lookup"><span data-stu-id="5448c-117">Using code to query the System.Environment class</span></span>](#clr_b)  
  
 <span data-ttu-id="5448c-118">Para obtener información sobre cómo detectar las actualizaciones instaladas de cada versión de .NET Framework, vea [Cómo: Determinar qué actualizaciones de .NET Framework están instaladas](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="5448c-118">For information about detecting the installed updates for each version of the .NET Framework, see [How to: Determine Which .NET Framework Updates Are Installed](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md).</span></span> <span data-ttu-id="5448c-119">Para obtener información sobre cómo instalar .NET Framework, consulte [Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md) (Instalar .NET Framework para desarrolladores).</span><span class="sxs-lookup"><span data-stu-id="5448c-119">For information about installing the .NET Framework, see [Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md).</span></span>  
  
<a name="net_a"></a>   
#### <a name="to-find-net-framework-versions-by-viewing-the-registry-net-framework-1-4"></a><span data-ttu-id="5448c-120">Para identificar las versiones de .NET Framework mediante la visualización del Registro (.NET Framework 1 a 4)</span><span class="sxs-lookup"><span data-stu-id="5448c-120">To find .NET Framework versions by viewing the registry (.NET Framework 1-4)</span></span>  
  
1.  <span data-ttu-id="5448c-121">En el menú **Inicio**, elija **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="5448c-121">On the **Start** menu, choose **Run**.</span></span>  
  
2.  <span data-ttu-id="5448c-122">En el cuadro **Abrir**, escriba **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="5448c-122">In the **Open** box, enter **regedit.exe**.</span></span>  
  
     <span data-ttu-id="5448c-123">Debe tener credenciales de administrador para ejecutar regedit.exe.</span><span class="sxs-lookup"><span data-stu-id="5448c-123">You must have administrative credentials to run regedit.exe.</span></span>  
  
3.  <span data-ttu-id="5448c-124">En el Editor del Registro, abra la subclave siguiente:</span><span class="sxs-lookup"><span data-stu-id="5448c-124">In the Registry Editor, open the following subkey:</span></span>  
  
     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP`  
  
     <span data-ttu-id="5448c-125">Las versiones instaladas se muestran bajo la subclave NDP.</span><span class="sxs-lookup"><span data-stu-id="5448c-125">The installed versions are listed under the NDP subkey.</span></span> <span data-ttu-id="5448c-126">El número de versión se indica en la entrada **Versión**.</span><span class="sxs-lookup"><span data-stu-id="5448c-126">The version number is stored in the **Version** entry.</span></span> <span data-ttu-id="5448c-127">En [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], la entrada **Versión** está en la subclave Client o Full (en NDP), o en ambas subclaves.</span><span class="sxs-lookup"><span data-stu-id="5448c-127">For the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] the **Version** entry is under the Client or Full subkey (under NDP), or under both subkeys.</span></span>  
  

    > [!NOTE]
    > <span data-ttu-id="5448c-128">La carpeta “NET Framework Setup” del Registro no comienza con un punto.</span><span class="sxs-lookup"><span data-stu-id="5448c-128">The "NET Framework Setup" folder in the registry does not begin with a period.</span></span>

<a name="net_b"></a> 
#### <a name="to-find-net-framework-versions-by-viewing-the-registry-net-framework-45-and-later"></a><span data-ttu-id="5448c-129">Para identificar las versiones de .NET Framework mediante la visualización del Registro (.NET Framework 4.5 y posterior)</span><span class="sxs-lookup"><span data-stu-id="5448c-129">To find .NET Framework versions by viewing the registry (.NET Framework 4.5 and later)</span></span>

1. <span data-ttu-id="5448c-130">En el menú **Inicio**, elija **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="5448c-130">On the **Start** menu, choose **Run**.</span></span>

2. <span data-ttu-id="5448c-131">En el cuadro **Abrir**, escriba **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="5448c-131">In the **Open** box, enter **regedit.exe**.</span></span>

     <span data-ttu-id="5448c-132">Debe tener credenciales de administrador para ejecutar regedit.exe.</span><span class="sxs-lookup"><span data-stu-id="5448c-132">You must have administrative credentials to run regedit.exe.</span></span>

3. <span data-ttu-id="5448c-133">En el Editor del Registro, abra la subclave siguiente:</span><span class="sxs-lookup"><span data-stu-id="5448c-133">In the Registry Editor, open the following subkey:</span></span>

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`

     <span data-ttu-id="5448c-134">Tenga en cuenta que la ruta de acceso a la subclave `Full` incluye la subclave `Net Framework` en lugar de la `.NET Framework`.</span><span class="sxs-lookup"><span data-stu-id="5448c-134">Note that the path to the `Full` subkey includes the subkey `Net Framework` rather than `.NET Framework`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5448c-135">Si la subclave `Full` no está presente, significa que .NET Framework 4.5 (o una versión posterior) no está instalado.</span><span class="sxs-lookup"><span data-stu-id="5448c-135">If the `Full` subkey is not present, then you do not have the .NET Framework 4.5 or later installed.</span></span>

     <span data-ttu-id="5448c-136">Compruebe si existe un valor DWORD denominado `Release`.</span><span class="sxs-lookup"><span data-stu-id="5448c-136">Check for a DWORD value named `Release`.</span></span> <span data-ttu-id="5448c-137">La existencia de un valor DWORD `Release` indica que en ese equipo está instalado [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o una versión anterior.</span><span class="sxs-lookup"><span data-stu-id="5448c-137">The existence of the `Release` DWORD indicates that the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or newer has been installed on that computer.</span></span>

     <span data-ttu-id="5448c-138">![Entrada del Registro para .NET Framework 4.5](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")</span><span class="sxs-lookup"><span data-stu-id="5448c-138">![The registry entry for the .NET Framework 4.5.](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")</span></span>

     <span data-ttu-id="5448c-139">El valor DWORD `Release` indica qué versión de .NET Framework está instalada.</span><span class="sxs-lookup"><span data-stu-id="5448c-139">The value of the `Release` DWORD indicates which version of the .NET Framework is installed.</span></span>

    |<span data-ttu-id="5448c-140">Valor DWORD de la versión</span><span class="sxs-lookup"><span data-stu-id="5448c-140">Value of the Release DWORD</span></span>|<span data-ttu-id="5448c-141">Versión</span><span class="sxs-lookup"><span data-stu-id="5448c-141">Version</span></span>|
    |--------------------------------|-------------|
    |<span data-ttu-id="5448c-142">378389</span><span class="sxs-lookup"><span data-stu-id="5448c-142">378389</span></span>|<span data-ttu-id="5448c-143">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="5448c-143">.NET Framework 4.5</span></span>|
    |<span data-ttu-id="5448c-144">378675</span><span class="sxs-lookup"><span data-stu-id="5448c-144">378675</span></span>|<span data-ttu-id="5448c-145">.NET Framework 4.5.1 instalado con Windows 8.1 o Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="5448c-145">.NET Framework 4.5.1 installed with Windows 8.1 or Windows Server 2012 R2</span></span>|
    |<span data-ttu-id="5448c-146">378758</span><span class="sxs-lookup"><span data-stu-id="5448c-146">378758</span></span>|<span data-ttu-id="5448c-147">.NET Framework 4.5.1 instalado en Windows 8, Windows 7 SP1 o Windows Vista SP2</span><span class="sxs-lookup"><span data-stu-id="5448c-147">.NET Framework 4.5.1 installed on Windows 8, Windows 7 SP1, or Windows Vista SP2</span></span>|
    |<span data-ttu-id="5448c-148">379893</span><span class="sxs-lookup"><span data-stu-id="5448c-148">379893</span></span>|<span data-ttu-id="5448c-149">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="5448c-149">.NET Framework 4.5.2</span></span>|
    |<span data-ttu-id="5448c-150">En sistemas Windows 10: 393295</span><span class="sxs-lookup"><span data-stu-id="5448c-150">On Windows 10 systems: 393295</span></span><br /><br /> <span data-ttu-id="5448c-151">En las demás versiones de sistema operativo: 393297</span><span class="sxs-lookup"><span data-stu-id="5448c-151">On all other OS versions: 393297</span></span>|[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]|
    |<span data-ttu-id="5448c-152">En sistemas con la actualización de noviembre de Windows 10: 394254</span><span class="sxs-lookup"><span data-stu-id="5448c-152">On Windows 10 November Update systems: 394254</span></span><br /><br /> <span data-ttu-id="5448c-153">En las demás versiones del sistema operativo: 394271</span><span class="sxs-lookup"><span data-stu-id="5448c-153">On all other OS versions: 394271</span></span>|[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]|
    |<span data-ttu-id="5448c-154">En la actualización de aniversario de Windows 10: 394802</span><span class="sxs-lookup"><span data-stu-id="5448c-154">On Windows 10 Anniversary Update: 394802</span></span><br /><br /> <span data-ttu-id="5448c-155">En las demás versiones del sistema operativo: 394806</span><span class="sxs-lookup"><span data-stu-id="5448c-155">On all other OS versions: 394806</span></span>|[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]| 
    |<span data-ttu-id="5448c-156">En Windows 10 Creators Update: 460798</span><span class="sxs-lookup"><span data-stu-id="5448c-156">On Windows 10 Creators Update: 460798</span></span><br/><br/> <span data-ttu-id="5448c-157">En las demás versiones de sistema operativo: 460805</span><span class="sxs-lookup"><span data-stu-id="5448c-157">On all other OS versions: 460805</span></span> | <span data-ttu-id="5448c-158">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="5448c-158">.NET Framework 4.7</span></span> |

<a name="net_c"></a> 
#### <a name="to-find-net-framework-versions-by-querying-the-registry-in-code-net-framework-1-4"></a><span data-ttu-id="5448c-159">Para identificar las versiones de .NET Framework con consultas en el Registro mediante código (.NET Framework 1 a 4)</span><span class="sxs-lookup"><span data-stu-id="5448c-159">To find .NET Framework versions by querying the registry in code (.NET Framework 1-4)</span></span>

- <span data-ttu-id="5448c-160">Utilice la clase <xref:Microsoft.Win32.RegistryKey?displayProperty=fullName> para tener acceso a la subclave Software\Microsoft\NET Framework Setup\NDP\ en HKEY_LOCAL_MACHINE en el Registro de Windows.</span><span class="sxs-lookup"><span data-stu-id="5448c-160">Use the <xref:Microsoft.Win32.RegistryKey?displayProperty=fullName> class to access the Software\Microsoft\NET Framework Setup\NDP\ subkey under HKEY_LOCAL_MACHINE in the Windows registry.</span></span>

     <span data-ttu-id="5448c-161">El código siguiente ilustra un ejemplo de esta consulta.</span><span class="sxs-lookup"><span data-stu-id="5448c-161">The following code shows an example of this query.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5448c-162">En este código no se muestra cómo detectar [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="5448c-162">This code does not show how to detect the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or later.</span></span> <span data-ttu-id="5448c-163">Compruebe el valor DWORD `Release` para detectar estas versiones, tal y como se describe en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="5448c-163">Check the `Release` DWORD to detect those versions, as described in the previous section.</span></span> <span data-ttu-id="5448c-164">Puede consultar el código que sí detecta [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o versiones posteriores en la sección siguiente de este artículo.</span><span class="sxs-lookup"><span data-stu-id="5448c-164">For code that does detect the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or later versions, see the next section in this article.</span></span>

     <span data-ttu-id="5448c-165">[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]    [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]</span><span class="sxs-lookup"><span data-stu-id="5448c-165">[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]    [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]</span></span>

     <span data-ttu-id="5448c-166">El ejemplo genera un resultado similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="5448c-166">The example produces output that's similar to the following:</span></span>

    ```
    v2.0.50727  2.0.50727.4016  SP2
    v3.0  3.0.30729.4037  SP2
    v3.5  3.5.30729.01  SP1
    v4
      Client  4.0.30319
      Full  4.0.30319
    ```

<a name="net_d"></a> 
#### <a name="to-find-net-framework-versions-by-querying-the-registry-in-code-net-framework-45-and-later"></a><span data-ttu-id="5448c-167">Para identificar las versiones de .NET Framework con consultas en el Registro mediante código (.NET Framework 4.5 y posterior)</span><span class="sxs-lookup"><span data-stu-id="5448c-167">To find .NET Framework versions by querying the registry in code (.NET Framework 4.5 and later)</span></span>

1. <span data-ttu-id="5448c-168">La existencia de un valor DWORD `Release` indica que ya se ha instalado .NET Framework 4.5 o posterior en un equipo.</span><span class="sxs-lookup"><span data-stu-id="5448c-168">The existence of the `Release` DWORD indicates that the .NET Framework 4.5 or later has been installed on a computer.</span></span> <span data-ttu-id="5448c-169">El valor de la palabra clave indica la versión instalada.</span><span class="sxs-lookup"><span data-stu-id="5448c-169">The value of the keyword indicates the installed version.</span></span> <span data-ttu-id="5448c-170">Para comprobar esta palabra clave, use los métodos <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A> y <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> de la clase <xref:Microsoft.Win32.RegistryKey?displayProperty=fullName> para obtener acceso a la subclave Software\Microsoft\NET Framework Setup\NDP\v4\Full, en HKEY_LOCAL_MACHINE, del Registro de Windows.</span><span class="sxs-lookup"><span data-stu-id="5448c-170">To check this keyword, use the <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A> and <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> methods of the <xref:Microsoft.Win32.RegistryKey?displayProperty=fullName> class to access the Software\Microsoft\NET Framework Setup\NDP\v4\Full subkey under HKEY_LOCAL_MACHINE in the Windows registry.</span></span>

2. <span data-ttu-id="5448c-171">Compruebe el valor de la palabra clave `Release` para determinar la versión instalada.</span><span class="sxs-lookup"><span data-stu-id="5448c-171">Check the value of the `Release` keyword to determine the installed version.</span></span> <span data-ttu-id="5448c-172">Para que sea compatible con el reenvío, puede buscar un valor mayor o igual que los valores que se muestran en la tabla.</span><span class="sxs-lookup"><span data-stu-id="5448c-172">To be forward-compatible, you can check for a value greater than or equal to the values listed in the table.</span></span> <span data-ttu-id="5448c-173">Estas son las versiones de .NET Framework y las palabras clave de `Release` asociadas.</span><span class="sxs-lookup"><span data-stu-id="5448c-173">Here are the .NET Framework versions and associated `Release` keywords.</span></span>

    |<span data-ttu-id="5448c-174">Versión</span><span class="sxs-lookup"><span data-stu-id="5448c-174">Version</span></span>|<span data-ttu-id="5448c-175">Valor DWORD de la versión</span><span class="sxs-lookup"><span data-stu-id="5448c-175">Value of the Release DWORD</span></span>|
    |-------------|--------------------------------|
    |<span data-ttu-id="5448c-176">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="5448c-176">.NET Framework 4.5</span></span>|<span data-ttu-id="5448c-177">378389</span><span class="sxs-lookup"><span data-stu-id="5448c-177">378389</span></span>|
    |<span data-ttu-id="5448c-178">.NET Framework 4.5.1 instalado con Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="5448c-178">.NET Framework 4.5.1 installed with Windows 8.1</span></span>|<span data-ttu-id="5448c-179">378675</span><span class="sxs-lookup"><span data-stu-id="5448c-179">378675</span></span>|
    |<span data-ttu-id="5448c-180">.NET Framework 4.5.1 instalado en Windows 8, Windows 7 SP1 o Windows Vista SP2</span><span class="sxs-lookup"><span data-stu-id="5448c-180">.NET Framework 4.5.1 installed on Windows 8, Windows 7 SP1, or Windows Vista SP2</span></span>|<span data-ttu-id="5448c-181">378758</span><span class="sxs-lookup"><span data-stu-id="5448c-181">378758</span></span>|
    |<span data-ttu-id="5448c-182">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="5448c-182">.NET Framework 4.5.2</span></span>|<span data-ttu-id="5448c-183">379893</span><span class="sxs-lookup"><span data-stu-id="5448c-183">379893</span></span>|
    |[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<span data-ttu-id="5448c-184"> instalado con Windows 10</span><span class="sxs-lookup"><span data-stu-id="5448c-184"> installed with Windows 10</span></span>|<span data-ttu-id="5448c-185">393295</span><span class="sxs-lookup"><span data-stu-id="5448c-185">393295</span></span>|
    |[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<span data-ttu-id="5448c-186"> instalado en las demás versiones del sistema operativo Windows</span><span class="sxs-lookup"><span data-stu-id="5448c-186"> installed on all other Windows OS versions</span></span>|<span data-ttu-id="5448c-187">393297</span><span class="sxs-lookup"><span data-stu-id="5448c-187">393297</span></span>|
    |[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]<span data-ttu-id="5448c-188"> instalado en Windows 10</span><span class="sxs-lookup"><span data-stu-id="5448c-188"> installed on Windows 10</span></span>|<span data-ttu-id="5448c-189">394254</span><span class="sxs-lookup"><span data-stu-id="5448c-189">394254</span></span>|
    |[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]<span data-ttu-id="5448c-190"> instalado en las demás versiones del sistema operativo Windows</span><span class="sxs-lookup"><span data-stu-id="5448c-190"> installed on all other Windows OS versions</span></span>|<span data-ttu-id="5448c-191">394271</span><span class="sxs-lookup"><span data-stu-id="5448c-191">394271</span></span>|
    |[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]<span data-ttu-id="5448c-192"> instalado en la actualización de aniversario de Windows 10</span><span class="sxs-lookup"><span data-stu-id="5448c-192"> installed on Windows 10 Anniversary Update</span></span>|<span data-ttu-id="5448c-193">394802</span><span class="sxs-lookup"><span data-stu-id="5448c-193">394802</span></span>|
    |[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]<span data-ttu-id="5448c-194"> instalado en las demás versiones del sistema operativo Windows</span><span class="sxs-lookup"><span data-stu-id="5448c-194"> installed on all other Windows OS versions</span></span>|<span data-ttu-id="5448c-195">394806</span><span class="sxs-lookup"><span data-stu-id="5448c-195">394806</span></span>|
    |<span data-ttu-id="5448c-196">.NET Framework 4.7 instalado en Windows 10 Creators Update</span><span class="sxs-lookup"><span data-stu-id="5448c-196">.NET Framework 4.7 installed on Windows 10 Creators Update</span></span>|<span data-ttu-id="5448c-197">460798</span><span class="sxs-lookup"><span data-stu-id="5448c-197">460798</span></span>|
    |<span data-ttu-id="5448c-198">.NET Framework 4.7 instalado en las demás versiones del sistema operativo Windows</span><span class="sxs-lookup"><span data-stu-id="5448c-198">.NET Framework 4.7 installed on all other Windows OS versions</span></span>|<span data-ttu-id="5448c-199">460805</span><span class="sxs-lookup"><span data-stu-id="5448c-199">460805</span></span>|

     <span data-ttu-id="5448c-200">El ejemplo siguiente comprueba el valor `Release` en el Registro para determinar si [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o una versión posterior de .NET Framework está instalada.</span><span class="sxs-lookup"><span data-stu-id="5448c-200">The following example checks the `Release` value in the registry to determine whether the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or a later version of the .NET Framework is installed.</span></span>

     <span data-ttu-id="5448c-201">[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]   [!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]</span><span class="sxs-lookup"><span data-stu-id="5448c-201">[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]   [!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]</span></span>

     <span data-ttu-id="5448c-202">Este ejemplo sigue la práctica recomendada para la comprobación de versión:</span><span class="sxs-lookup"><span data-stu-id="5448c-202">This example follows the recommended practice for version checking:</span></span>

    - <span data-ttu-id="5448c-203">Comprueba si el valor de la entrada `Release` es *mayor o igual que* el valor de las claves conocidas de versión.</span><span class="sxs-lookup"><span data-stu-id="5448c-203">It checks whether the value of the `Release` entry is *greater than or equal to* the value of the known release keys.</span></span>

    - <span data-ttu-id="5448c-204">Realiza la comprobación en orden, desde la versión más reciente hasta la más antigua.</span><span class="sxs-lookup"><span data-stu-id="5448c-204">It checks in order from most recent version to earliest version.</span></span>

<a name="clr_a"></a> 
#### <a name="to-find-the-current-runtime-version-by-using-the-clrver-tool"></a><span data-ttu-id="5448c-205">Para identificar la versión de runtime actual mediante la herramienta Clrver</span><span class="sxs-lookup"><span data-stu-id="5448c-205">To find the current runtime version by using the Clrver tool</span></span>

- <span data-ttu-id="5448c-206">Use la herramienta de versión de CLR (Clrver.exe) para determinar qué versiones de Common Language Runtime (CLR) están instaladas en un equipo.</span><span class="sxs-lookup"><span data-stu-id="5448c-206">Use the CLR Version Tool (Clrver.exe) to determine which versions of the common language runtime are installed on a computer.</span></span>

     <span data-ttu-id="5448c-207">En un símbolo del sistema de Visual Studio, escriba `clrver`.</span><span class="sxs-lookup"><span data-stu-id="5448c-207">From a Visual Studio Command Prompt, enter `clrver`.</span></span> <span data-ttu-id="5448c-208">Este comando produce un resultado similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="5448c-208">This command produces output similar to the following:</span></span>

    ```
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

     <span data-ttu-id="5448c-209">Para obtener más información sobre el uso de esta herramienta, consulte [Clrver.exe (herramienta de versión de CLR)](~/docs/framework/tools/clrver-exe-clr-version-tool.md).</span><span class="sxs-lookup"><span data-stu-id="5448c-209">For more information about using this tool, see [Clrver.exe (CLR Version Tool)](~/docs/framework/tools/clrver-exe-clr-version-tool.md).</span></span>

<a name="clr_b"></a> 
#### <a name="to-find-the-current-runtime-version-by-querying-the-environment-class-in-code"></a><span data-ttu-id="5448c-210">Para buscar la versión de runtime actual consultando la clase Environment en el código</span><span class="sxs-lookup"><span data-stu-id="5448c-210">To find the current runtime version by querying the Environment class in code</span></span>

- <span data-ttu-id="5448c-211">Consulte la propiedad <xref:System.Environment.Version%2A?displayProperty=fullName> para recuperar un objeto <xref:System.Version> que identifique la versión de tiempo de ejecución que está ejecutando el código.</span><span class="sxs-lookup"><span data-stu-id="5448c-211">Query the <xref:System.Environment.Version%2A?displayProperty=fullName> property to retrieve a <xref:System.Version> object that identifies the version of the runtime that is currently executing the code.</span></span> <span data-ttu-id="5448c-212">Puede utilizar la propiedad <xref:System.Version.Major%2A?displayProperty=fullName> para obtener el identificador de versión principal (por ejemplo, "4" para la versión 4,0), la propiedad <xref:System.Version.Minor%2A?displayProperty=fullName> para obtener el identificador de versión secundaria (por ejemplo, "0" para la versión 4,0) o el método <xref:System.Object.ToString%2A?displayProperty=fullName> para obtener la cadena completa de la versión (por ejemplo, "4.0.30319.18010", como se muestra en el código siguiente).</span><span class="sxs-lookup"><span data-stu-id="5448c-212">You can use the <xref:System.Version.Major%2A?displayProperty=fullName> property to get the major release identifier (for example, "4" for version 4.0), the <xref:System.Version.Minor%2A?displayProperty=fullName> property to get the minor release identifier (for example, "0" for version 4.0), or the <xref:System.Object.ToString%2A?displayProperty=fullName> method to get the entire version string (for example, "4.0.30319.18010", as shown in the following code).</span></span> <span data-ttu-id="5448c-213">Esta propiedad devuelve un valor único que refleja la versión del runtime que está ejecutando el código actualmente; no devuelve versiones de ensamblado ni otras versiones del runtime que se hayan podido instalar en el equipo.</span><span class="sxs-lookup"><span data-stu-id="5448c-213">This property returns a single value that reflects the version of the runtime that is currently executing the code; it does not return assembly versions or other versions of the runtime that may have been installed on the computer.</span></span>

     <span data-ttu-id="5448c-214">Para las versiones 4, 4.5, 4.5.1 y 4.5.2 de .NET Framework, la propiedad <xref:System.Environment.Version%2A?displayProperty=fullName> devuelve un objeto <xref:System.Version> cuya representación de cadena tiene la forma `4.0.30319.xxxxx`.</span><span class="sxs-lookup"><span data-stu-id="5448c-214">For the .NET Framework Versions 4, 4.5, 4.5.1, and 4.5.2, the <xref:System.Environment.Version%2A?displayProperty=fullName> property returns a <xref:System.Version> object whose string representation has the form `4.0.30319.xxxxx`.</span></span> <span data-ttu-id="5448c-215">Para .NET Framework 4.6 y posterior, tiene la forma `4.0.30319.42000`.</span><span class="sxs-lookup"><span data-stu-id="5448c-215">For the .NET Framework 4.6 and later, it has the form `4.0.30319.42000`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5448c-216">Para [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] y versiones posteriores, no se recomienda usar la propiedad <xref:System.Environment.Version%2A?displayProperty=fullName> para detectar la versión del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5448c-216">For the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] and later, we do not recommend using the  <xref:System.Environment.Version%2A?displayProperty=fullName> property to detect the version of the runtime.</span></span> <span data-ttu-id="5448c-217">En su lugar, se recomienda consultar el Registro, como se describe en la sección anterior de este artículo [Para identificar las versiones de .NET Framework con consultas en el Registro mediante código (.NET Framework 4.5 y posterior)](#net_d).</span><span class="sxs-lookup"><span data-stu-id="5448c-217">Instead, we recommend that you query the registry, as described in the [To find .NET Framework versions by querying the registry in code (.NET Framework 4.5 and later)](#net_d) section earlier in this article.</span></span>

     <span data-ttu-id="5448c-218">A continuación se muestra un ejemplo de cómo consultar la propiedad <xref:System.Environment.Version%2A?displayProperty=fullName> para obtener información de la versión del runtime:</span><span class="sxs-lookup"><span data-stu-id="5448c-218">Here's an example of querying the <xref:System.Environment.Version%2A?displayProperty=fullName> property for runtime version information:</span></span>

     <span data-ttu-id="5448c-219">[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]    [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]</span><span class="sxs-lookup"><span data-stu-id="5448c-219">[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]    [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]</span></span>

     <span data-ttu-id="5448c-220">El ejemplo genera un resultado similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="5448c-220">The example produces output that's similar to the following:</span></span>

    ```
    Version: 4.0.30319.18010
    ```

## <a name="see-also"></a><span data-ttu-id="5448c-221">Vea también</span><span class="sxs-lookup"><span data-stu-id="5448c-221">See Also</span></span>
 <span data-ttu-id="5448c-222">[Cómo: Determinar qué actualizaciones de .NET Framework están instaladas](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md) </span><span class="sxs-lookup"><span data-stu-id="5448c-222">[How to: Determine Which .NET Framework Updates Are Installed](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md) </span></span>  
 <span data-ttu-id="5448c-223">[Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md)  (Instalar .NET Framework para desarrolladores)</span><span class="sxs-lookup"><span data-stu-id="5448c-223">[Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md) </span></span>  
 [<span data-ttu-id="5448c-224">Versiones y dependencias</span><span class="sxs-lookup"><span data-stu-id="5448c-224">Versions and Dependencies</span></span>](~/docs/framework/migration-guide/versions-and-dependencies.md)


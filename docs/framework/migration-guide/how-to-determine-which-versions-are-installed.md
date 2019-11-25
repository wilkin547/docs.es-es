---
title: para determinar qué versiones de .NET Framework están instaladas
ms.date: 04/18/2019
dev_langs:
- csharp
- vb
ms.custom: updateeachrelease
helpviewer_keywords:
- versions, determining for .NET Framework
- .NET Framework, determining version
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
ms.openlocfilehash: b860aac01780acb67c53e822eff478b78198996b
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738191"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a><span data-ttu-id="b7e18-102">Procedimiento para determinar qué versiones de .NET Framework están instaladas</span><span class="sxs-lookup"><span data-stu-id="b7e18-102">How to: Determine which .NET Framework versions are installed</span></span>

<span data-ttu-id="b7e18-103">Los usuarios pueden [instalar](../install/index.md) y ejecutar varias versiones de .NET Framework en sus equipos.</span><span class="sxs-lookup"><span data-stu-id="b7e18-103">Users can [install](../install/index.md) and run multiple versions of the .NET Framework on their computers.</span></span> <span data-ttu-id="b7e18-104">Al desarrollar o implementar una aplicación, puede que necesite conocer las versiones de .NET Framework que están instaladas en el equipo del usuario.</span><span class="sxs-lookup"><span data-stu-id="b7e18-104">When you develop or deploy your app, you might need to know which .NET Framework versions are installed on the user’s computer.</span></span>

<span data-ttu-id="b7e18-105">.NET Framework está formado por dos componentes principales con versiones separadas:</span><span class="sxs-lookup"><span data-stu-id="b7e18-105">The .NET Framework consists of two main components, which are versioned separately:</span></span>

- <span data-ttu-id="b7e18-106">Un conjunto de ensamblados, que son colecciones de tipos y recursos que proporcionan funciones a las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b7e18-106">A set of assemblies, which are collections of types and resources that provide the functionality for your apps.</span></span> <span data-ttu-id="b7e18-107">.NET Framework y los ensamblados comparten el mismo número de versión.</span><span class="sxs-lookup"><span data-stu-id="b7e18-107">The .NET Framework and assemblies share the same version number.</span></span>

- <span data-ttu-id="b7e18-108">Common Language Runtime (CLR), que administra y ejecuta el código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b7e18-108">The common language runtime (CLR), which manages and executes your app's code.</span></span> <span data-ttu-id="b7e18-109">El CLR se identifica mediante su propio número de versión (consulte [Versiones y dependencias](versions-and-dependencies.md)).</span><span class="sxs-lookup"><span data-stu-id="b7e18-109">The CLR is identified by its own version number (see [Versions and dependencies](versions-and-dependencies.md)).</span></span>

> [!NOTE]
> <span data-ttu-id="b7e18-110">Cada versión de .NET Framework contiene características de versiones anteriores e incorpora nuevas características.</span><span class="sxs-lookup"><span data-stu-id="b7e18-110">Each new version of the .NET Framework retains features from the previous versions and adds new features.</span></span> <span data-ttu-id="b7e18-111">Puede cargar varias versiones de .NET Framework en un equipo al mismo tiempo, lo que significa que puede instalarlo sin tener que eliminar las versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="b7e18-111">You can load multiple versions of the .NET Framework on a single computer at the same time, which means that you can install the .NET Framework without having to uninstall previous versions.</span></span> <span data-ttu-id="b7e18-112">En general, no debe desinstalar ninguna versión anterior de .NET Framework, ya que una determinada aplicación puede depender de una versión concreta y puede dejar de funcionar si se quita esa versión.</span><span class="sxs-lookup"><span data-stu-id="b7e18-112">In general, you shouldn't uninstall previous versions of the .NET Framework, because an application you use may depend on a specific version and may break if that version is removed.</span></span>
>
> <span data-ttu-id="b7e18-113">Hay una diferencia entre la versión de .NET Framework y la versión de CLR:</span><span class="sxs-lookup"><span data-stu-id="b7e18-113">There is a difference between the .NET Framework version and the CLR version:</span></span>
>
> - <span data-ttu-id="b7e18-114">Las versiones de .NET Framework se basan en el conjunto de ensamblados que conforman la biblioteca de clases .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b7e18-114">The .NET Framework version is based on the set of assemblies that form the .NET Framework class library.</span></span> <span data-ttu-id="b7e18-115">Por ejemplo, las versiones de .NET Framework incluyen 4.5, 4.6.1 y 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="b7e18-115">For example, .NET Framework versions include 4.5, 4.6.1, and 4.7.2.</span></span>
> - <span data-ttu-id="b7e18-116">La versión de CLR se basa en el tiempo de ejecución en el que se ejecutan las aplicaciones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b7e18-116">The CLR version is based on the runtime on which .NET Framework applications execute.</span></span> <span data-ttu-id="b7e18-117">Normalmente, una misma versión de CLR admite varias versiones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b7e18-117">A single CLR version typically supports multiple .NET Framework versions.</span></span> <span data-ttu-id="b7e18-118">Por ejemplo, la versión de CLR 4.0.30319.*xxxxx* admite las versiones de la 4 a la 4.5.2 de .NET Framework; donde *xxxxx* es inferior a 42000, y la versión de CLR 4.0.30319.42000 admite las versiones de .NET Framework a partir de .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="b7e18-118">For example, CLR version 4.0.30319.*xxxxx* supports .NET Framework versions 4 through 4.5.2, where *xxxxx* is less than 42000, and CLR version 4.0.30319.42000 supports .NET Framework versions starting with .NET Framework 4.6.</span></span>
>
> <span data-ttu-id="b7e18-119">Para obtener más información sobre las versiones, vea [Versiones y dependencias de .NET Framework](versions-and-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="b7e18-119">For more information about versions, see [.NET Framework versions and dependencies](versions-and-dependencies.md).</span></span>

<span data-ttu-id="b7e18-120">El registro contiene una lista de las versiones de .NET Framework instaladas en un equipo.</span><span class="sxs-lookup"><span data-stu-id="b7e18-120">The registry contains a list of the .NET Framework versions installed on a computer.</span></span> <span data-ttu-id="b7e18-121">Puede usar el Editor del Registro para ver el Registro o usar código para consultarlo:</span><span class="sxs-lookup"><span data-stu-id="b7e18-121">You can either use the Registry Editor to view the registry or query it with code:</span></span>

- <span data-ttu-id="b7e18-122">Búsqueda de versiones más recientes de .NET Framework (4.5 y versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="b7e18-122">Find newer .NET Framework versions (4.5 and later):</span></span>

  - [<span data-ttu-id="b7e18-123">Uso del Editor del Registro para buscar versiones de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b7e18-123">Use the Registry Editor to find .NET Framework versions</span></span>](#net_b)
  - [<span data-ttu-id="b7e18-124">Uso de código para consultar en el Registro las versiones de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b7e18-124">Use code to query the registry for .NET Framework versions</span></span>](#net_d)
  - [<span data-ttu-id="b7e18-125">Uso de PowerShell para consultar en el Registro las versiones de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b7e18-125">Use PowerShell to query the registry for .NET Framework versions</span></span>](#ps_a)

- <span data-ttu-id="b7e18-126">Búsqueda de versiones más antiguas de .NET Framework (1 a 4):</span><span class="sxs-lookup"><span data-stu-id="b7e18-126">Find older .NET Framework versions (1 through 4):</span></span>

  - [<span data-ttu-id="b7e18-127">Uso del Editor del Registro para buscar versiones de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b7e18-127">Use the Registry Editor to find .NET Framework versions</span></span>](#net_a)
  - [<span data-ttu-id="b7e18-128">Uso de código para consultar en el Registro las versiones de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b7e18-128">Use code to query the registry for .NET Framework versions</span></span>](#net_c)

<span data-ttu-id="b7e18-129">Para obtener una lista de las versiones de CLR instaladas en un equipo, use una herramienta o código:</span><span class="sxs-lookup"><span data-stu-id="b7e18-129">To get a list of the CLR versions installed on a computer, use a tool or code:</span></span>

- [<span data-ttu-id="b7e18-130">Uso de la herramienta Clrver</span><span class="sxs-lookup"><span data-stu-id="b7e18-130">Use the Clrver tool</span></span>](#clr_a)
- [<span data-ttu-id="b7e18-131">Uso de código para consultar la clase Environment</span><span class="sxs-lookup"><span data-stu-id="b7e18-131">Use code to query the Environment class</span></span>](#clr_b)

<span data-ttu-id="b7e18-132">Para obtener información sobre cómo detectar las actualizaciones instaladas de cada versión de .NET Framework, vea [Cómo: Determinar las actualizaciones de .NET Framework que están instaladas](how-to-determine-which-net-framework-updates-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="b7e18-132">For information about detecting the installed updates for each version of the .NET Framework, see [How to: Determine which .NET Framework updates are installed](how-to-determine-which-net-framework-updates-are-installed.md).</span></span>

## <a name="find-newer-net-framework-versions-45-and-later"></a><span data-ttu-id="b7e18-133">Búsqueda de versiones más recientes de .NET Framework (4.5 y versiones posteriores)</span><span class="sxs-lookup"><span data-stu-id="b7e18-133">Find newer .NET Framework versions (4.5 and later)</span></span>

<span data-ttu-id="b7e18-134">Puede usar el Editor del Registro para buscar la información de versión en el registro o puede consultar el registro mediante programación.</span><span class="sxs-lookup"><span data-stu-id="b7e18-134">You can use Registry Editor to find version information in the registry, or you can query the registry programmatically.</span></span>

<a name="net_b"></a>

### <a name="use-registry-editor"></a><span data-ttu-id="b7e18-135">Uso del Editor del Registro</span><span class="sxs-lookup"><span data-stu-id="b7e18-135">Use Registry Editor</span></span>

1. <span data-ttu-id="b7e18-136">En el menú **Inicio**, seleccione **Ejecutar**, escriba *regedit* y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b7e18-136">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>

     <span data-ttu-id="b7e18-137">Debe tener credenciales de administrador para ejecutar regedit.</span><span class="sxs-lookup"><span data-stu-id="b7e18-137">You must have administrative credentials to run regedit.</span></span>

2. <span data-ttu-id="b7e18-138">En el Editor del Registro, abra la subclave siguiente: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span><span class="sxs-lookup"><span data-stu-id="b7e18-138">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span></span> <span data-ttu-id="b7e18-139">Si la subclave **Full** no está presente, significa que .NET Framework 4.5 (o una versión posterior) no está instalado.</span><span class="sxs-lookup"><span data-stu-id="b7e18-139">If the **Full** subkey isn't present, then you don't have the .NET Framework 4.5 or later installed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b7e18-140">La carpeta **NET Framework Setup** del Registro *no* comienza con un punto.</span><span class="sxs-lookup"><span data-stu-id="b7e18-140">The **NET Framework Setup** folder in the registry does *not* begin with a period.</span></span>

3. <span data-ttu-id="b7e18-141">Busque una entrada DWORD denominada **Release**.</span><span class="sxs-lookup"><span data-stu-id="b7e18-141">Check for a DWORD entry named **Release**.</span></span> <span data-ttu-id="b7e18-142">Si existe, significa que tiene instalado .NET Framework 4.5 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="b7e18-142">If it exists, then you have .NET Framework 4.5 or later installed.</span></span> <span data-ttu-id="b7e18-143">Su valor es una clave de versión que corresponde a una versión concreta de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b7e18-143">Its value is a release key that corresponds to a particular version of the .NET Framework.</span></span> <span data-ttu-id="b7e18-144">En la ilustración siguiente, por ejemplo, el valor de la entrada **Release** es 378389, que es la clave de versión de .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="b7e18-144">In the following figure, for example, the value of the **Release** entry is 378389, which is the release key for .NET Framework 4.5.</span></span>

   <span data-ttu-id="b7e18-145">![Entrada del Registro para .NET Framework 4.5](./media/clr-installdir.png "Entrada del Registro para .NET Framework 4.5")</span><span class="sxs-lookup"><span data-stu-id="b7e18-145">![Registry entry for the .NET Framework 4.5](./media/clr-installdir.png "Registry entry for the .NET Framework 4.5")</span></span>

<span data-ttu-id="b7e18-146">En la tabla siguiente se muestra el valor de DWORD **Release** de sistemas operativos individuales para .NET Framework 4.5 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="b7e18-146">The following table lists the value of the **Release** DWORD on individual operating systems for .NET Framework 4.5 and later versions.</span></span>

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

<a name="version_table"></a>

|<span data-ttu-id="b7e18-147">Versión de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b7e18-147">.NET Framework version</span></span>|<span data-ttu-id="b7e18-148">Valor DWORD de la versión</span><span class="sxs-lookup"><span data-stu-id="b7e18-148">Value of the Release DWORD</span></span>|
|--------------------------------|-------------|
|<span data-ttu-id="b7e18-149">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="b7e18-149">.NET Framework 4.5</span></span>|<span data-ttu-id="b7e18-150">Todos los sistemas operativos Windows: 378389</span><span class="sxs-lookup"><span data-stu-id="b7e18-150">All Windows operating systems: 378389</span></span>|
|<span data-ttu-id="b7e18-151">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="b7e18-151">.NET Framework 4.5.1</span></span>|<span data-ttu-id="b7e18-152">En Windows 8.1 y Windows Server 2012 R2: 378675</span><span class="sxs-lookup"><span data-stu-id="b7e18-152">On Windows 8.1 and Windows Server 2012 R2: 378675</span></span><br /><span data-ttu-id="b7e18-153">En todos los demás sistemas operativos Windows: 378758</span><span class="sxs-lookup"><span data-stu-id="b7e18-153">On all other Windows operating systems: 378758</span></span>|
|<span data-ttu-id="b7e18-154">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="b7e18-154">.NET Framework 4.5.2</span></span>|<span data-ttu-id="b7e18-155">Todos los sistemas operativos Windows: 379893</span><span class="sxs-lookup"><span data-stu-id="b7e18-155">All Windows operating systems: 379893</span></span>|
|<span data-ttu-id="b7e18-156">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="b7e18-156">.NET Framework 4.6</span></span>|<span data-ttu-id="b7e18-157">En Windows 10: 393295</span><span class="sxs-lookup"><span data-stu-id="b7e18-157">On Windows 10: 393295</span></span><br /><span data-ttu-id="b7e18-158">En todos los demás sistemas operativos Windows: 393297</span><span class="sxs-lookup"><span data-stu-id="b7e18-158">On all other Windows operating systems: 393297</span></span>|
|<span data-ttu-id="b7e18-159">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="b7e18-159">.NET Framework 4.6.1</span></span>|<span data-ttu-id="b7e18-160">En sistemas con la actualización de noviembre de Windows 10: 394254</span><span class="sxs-lookup"><span data-stu-id="b7e18-160">On Windows 10 November Update systems: 394254</span></span><br /><span data-ttu-id="b7e18-161">En todos los demás sistemas operativos Windows (incluido Windows 10): 394271</span><span class="sxs-lookup"><span data-stu-id="b7e18-161">On all other Windows operating systems (including Windows 10): 394271</span></span>|
|<span data-ttu-id="b7e18-162">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="b7e18-162">.NET Framework 4.6.2</span></span>|<span data-ttu-id="b7e18-163">En la Actualización de aniversario de Windows 10 y Windows Server 2016: 394802</span><span class="sxs-lookup"><span data-stu-id="b7e18-163">On Windows 10 Anniversary Update and Windows Server 2016: 394802</span></span><br /><span data-ttu-id="b7e18-164">En todos los demás sistemas operativos Windows (incluidos otros sistemas operativos Windows 10): 394806</span><span class="sxs-lookup"><span data-stu-id="b7e18-164">On all other Windows operating systems (including other Windows 10 operating systems): 394806</span></span>|
|<span data-ttu-id="b7e18-165">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="b7e18-165">.NET Framework 4.7</span></span>|<span data-ttu-id="b7e18-166">En Windows 10 Creators Update: 460798</span><span class="sxs-lookup"><span data-stu-id="b7e18-166">On Windows 10 Creators Update: 460798</span></span><br /><span data-ttu-id="b7e18-167">En todos los demás sistemas operativos Windows (incluidos otros sistemas operativos Windows 10): 460805</span><span class="sxs-lookup"><span data-stu-id="b7e18-167">On all other Windows operating systems (including other Windows 10 operating systems): 460805</span></span>|
|<span data-ttu-id="b7e18-168">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="b7e18-168">.NET Framework 4.7.1</span></span>|<span data-ttu-id="b7e18-169">En Windows 10 Fall Creators Update y Windows Server, versión 1709: 461308</span><span class="sxs-lookup"><span data-stu-id="b7e18-169">On Windows 10 Fall Creators Update and Windows Server, version 1709: 461308</span></span><br/><span data-ttu-id="b7e18-170">En todos los demás sistemas operativos Windows (incluidos otros sistemas operativos Windows 10): 461310</span><span class="sxs-lookup"><span data-stu-id="b7e18-170">On all other Windows operating systems (including other Windows 10 operating systems): 461310</span></span>|
|<span data-ttu-id="b7e18-171">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="b7e18-171">.NET Framework 4.7.2</span></span>|<span data-ttu-id="b7e18-172">En la actualización de Windows 10 de abril de 2018 y Windows Server, versión 1803: 461808</span><span class="sxs-lookup"><span data-stu-id="b7e18-172">On Windows 10 April 2018 Update and Windows Server, version 1803: 461808</span></span><br/><span data-ttu-id="b7e18-173">En todos los sistemas operativos diferentes de la Actualización de abril de 2018 de Windows 10 y Windows Server, versión 1803: 461814</span><span class="sxs-lookup"><span data-stu-id="b7e18-173">On all Windows operating systems other than Windows 10 April 2018 Update and Windows Server, version 1803: 461814</span></span>|
|<span data-ttu-id="b7e18-174">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="b7e18-174">.NET Framework 4.8</span></span>|<span data-ttu-id="b7e18-175">En la actualización de Windows 10 de mayo de 2019 y en la de noviembre de 2019: 528040</span><span class="sxs-lookup"><span data-stu-id="b7e18-175">On Windows 10 May 2019 Update and Windows 10 November 2019 Update: 528040</span></span><br/><span data-ttu-id="b7e18-176">En todos los demás sistemas operativos Windows (incluidos otros sistemas operativos Windows 10): 528049</span><span class="sxs-lookup"><span data-stu-id="b7e18-176">On all other Windows operating systems (including other Windows 10 operating systems): 528049</span></span>|

#### <a name="specific-version"></a><span data-ttu-id="b7e18-177">Versión específica</span><span class="sxs-lookup"><span data-stu-id="b7e18-177">Specific version</span></span>

<span data-ttu-id="b7e18-178">Para determinar si una versión *específica* de .NET Framework está instalada en una versión concreta del sistema operativo Windows, pruebe si el valor de DWORD **Release** es *igual al* valor que aparece en la tabla.</span><span class="sxs-lookup"><span data-stu-id="b7e18-178">To determine whether a *specific* version of the .NET Framework is installed on a particular version of the Windows operating system, test whether the **Release** DWORD value is *equal to* the value listed in the table.</span></span> <span data-ttu-id="b7e18-179">Por ejemplo, para determinar si .NET Framework 4.6 está presente en un sistema Windows 10, pruebe un valor de **Release** que sea *igual a* 393295.</span><span class="sxs-lookup"><span data-stu-id="b7e18-179">For example, to determine whether .NET Framework 4.6 is present on a Windows 10 system, test for the a **Release** value that is *equal to* 393295.</span></span>

#### <a name="minimum-version"></a><span data-ttu-id="b7e18-180">Versión mínima</span><span class="sxs-lookup"><span data-stu-id="b7e18-180">Minimum version</span></span>

<span data-ttu-id="b7e18-181">Para determinar si existe una versión *mínima* de .NET Framework, utilice el valor más bajo de DWORD **RELEASE** para esa versión de la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="b7e18-181">To determine whether a *minimum* version of the .NET Framework is present, use the smallest **RELEASE** DWORD value for that version from the previous table.</span></span> <span data-ttu-id="b7e18-182">(Para mayor comodidad, los valores mínimos también se muestran en la tabla siguiente).</span><span class="sxs-lookup"><span data-stu-id="b7e18-182">(For convenience, the minimum values are also listed in the table that follows.)</span></span>

<span data-ttu-id="b7e18-183">Por ejemplo, si la aplicación se ejecuta en .NET Framework 4.8 o una versión posterior, pruebe un valor de DWORD **RELEASE** que sea *mayor o igual que* 528040.</span><span class="sxs-lookup"><span data-stu-id="b7e18-183">For example, if your application runs under .NET Framework 4.8 or a later version, test for a **RELEASE** DWORD value that is *greater than or equal to* 528040.</span></span>

|<span data-ttu-id="b7e18-184">Versión de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b7e18-184">.NET Framework version</span></span>|<span data-ttu-id="b7e18-185">Valor mínimo de DWORD de la versión</span><span class="sxs-lookup"><span data-stu-id="b7e18-185">Minimum value of the Release DWORD</span></span>|
|--------------------------------|-------------|
|<span data-ttu-id="b7e18-186">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="b7e18-186">.NET Framework 4.5</span></span>|<span data-ttu-id="b7e18-187">378389</span><span class="sxs-lookup"><span data-stu-id="b7e18-187">378389</span></span>|
|<span data-ttu-id="b7e18-188">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="b7e18-188">.NET Framework 4.5.1</span></span>|<span data-ttu-id="b7e18-189">378675</span><span class="sxs-lookup"><span data-stu-id="b7e18-189">378675</span></span>|
|<span data-ttu-id="b7e18-190">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="b7e18-190">.NET Framework 4.5.2</span></span>|<span data-ttu-id="b7e18-191">379893</span><span class="sxs-lookup"><span data-stu-id="b7e18-191">379893</span></span>|
|<span data-ttu-id="b7e18-192">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="b7e18-192">.NET Framework 4.6</span></span>|<span data-ttu-id="b7e18-193">393295</span><span class="sxs-lookup"><span data-stu-id="b7e18-193">393295</span></span>|
|<span data-ttu-id="b7e18-194">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="b7e18-194">.NET Framework 4.6.1</span></span>|<span data-ttu-id="b7e18-195">394254</span><span class="sxs-lookup"><span data-stu-id="b7e18-195">394254</span></span>|
|<span data-ttu-id="b7e18-196">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="b7e18-196">.NET Framework 4.6.2</span></span>|<span data-ttu-id="b7e18-197">394802</span><span class="sxs-lookup"><span data-stu-id="b7e18-197">394802</span></span>|
|<span data-ttu-id="b7e18-198">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="b7e18-198">.NET Framework 4.7</span></span>|<span data-ttu-id="b7e18-199">460798</span><span class="sxs-lookup"><span data-stu-id="b7e18-199">460798</span></span>|
|<span data-ttu-id="b7e18-200">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="b7e18-200">.NET Framework 4.7.1</span></span>|<span data-ttu-id="b7e18-201">461308</span><span class="sxs-lookup"><span data-stu-id="b7e18-201">461308</span></span>|
|<span data-ttu-id="b7e18-202">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="b7e18-202">.NET Framework 4.7.2</span></span>|<span data-ttu-id="b7e18-203">461808</span><span class="sxs-lookup"><span data-stu-id="b7e18-203">461808</span></span>|
|<span data-ttu-id="b7e18-204">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="b7e18-204">.NET Framework 4.8</span></span>|<span data-ttu-id="b7e18-205">528040</span><span class="sxs-lookup"><span data-stu-id="b7e18-205">528040</span></span>|

#### <a name="multiple-versions"></a><span data-ttu-id="b7e18-206">Varias versiones</span><span class="sxs-lookup"><span data-stu-id="b7e18-206">Multiple versions</span></span>

<span data-ttu-id="b7e18-207">Para probar varias versiones, empiece por probar un valor que sea *mayor o igual que* el valor más bajo de DWORD para la última versión de .NET Framework y, después, compare el valor con el valor más bajo de DWORD para cada versión anterior sucesiva.</span><span class="sxs-lookup"><span data-stu-id="b7e18-207">To test for multiple versions, begin by testing for a value that is *greater than or equal to* the smaller DWORD value for the latest .NET Framework version, and then compare the value with the smaller DWORD value for each successive earlier version.</span></span> <span data-ttu-id="b7e18-208">Por ejemplo, si la aplicación requiere .NET Framework 4.7 o versiones posteriores y quiere determinar cuál es la versión específica de .NET Framework existente, empiece por probar un valor de DWORD **RELEASE** que sea *mayor o igual que* 461808 (el valor de DWORD más pequeño para .NET Framework 4.7.2).</span><span class="sxs-lookup"><span data-stu-id="b7e18-208">For example, if your application requires .NET Framework 4.7 or later and you want to determine the specific version of .NET Framework present, start by testing for a **RELEASE** DWORD value that is *great than or equal to* to 461808 (the smaller DWORD value for .NET Framework 4.7.2).</span></span> <span data-ttu-id="b7e18-209">Después, compare el valor de DWORD **RELEASE** con el valor más bajo de cada versión posterior de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b7e18-209">Then compare the **RELEASE** DWORD value with the smaller value for each later .NET Framework version.</span></span>

<a name="net_d"></a>

### <a name="query-the-registry-using-code"></a><span data-ttu-id="b7e18-210">Consulta del registro mediante código</span><span class="sxs-lookup"><span data-stu-id="b7e18-210">Query the registry using code</span></span>

1. <span data-ttu-id="b7e18-211">Use los métodos <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> y <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> para obtener acceso a la subclave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** en el Registro de Windows.</span><span class="sxs-lookup"><span data-stu-id="b7e18-211">Use the <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> and <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> methods to access the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey in the Windows registry.</span></span>

   <span data-ttu-id="b7e18-212">La existencia de la entrada DWORD **Release** en la subclave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** indica que .NET Framework 4.5 (o una versión posterior) está instalado en un equipo.</span><span class="sxs-lookup"><span data-stu-id="b7e18-212">The existence of the **Release** DWORD entry in the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey indicates that the .NET Framework 4.5 or a later version is installed on a computer.</span></span>

2. <span data-ttu-id="b7e18-213">Compruebe el valor de la entrada **Release** para determinar la versión instalada.</span><span class="sxs-lookup"><span data-stu-id="b7e18-213">Check the value of the **Release** entry to determine the installed version.</span></span> <span data-ttu-id="b7e18-214">Para que sea compatible con versiones posteriores, puede buscar un valor mayor o igual que el valor que se muestra en la [tabla de versiones de .NET Framework](#version_table).</span><span class="sxs-lookup"><span data-stu-id="b7e18-214">To be forward-compatible, check for a value greater than or equal to the value listed in the [.NET Framework version table](#version_table).</span></span>

<span data-ttu-id="b7e18-215">En el ejemplo siguiente se comprueba el valor de la entrada **Release** del Registro para buscar .NET Framework 4.5 y las versiones posteriores que están instaladas:</span><span class="sxs-lookup"><span data-stu-id="b7e18-215">The following example checks the value of the **Release** entry in the registry to find the .NET Framework 4.5 and later versions that are installed:</span></span>

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

<span data-ttu-id="b7e18-216">Este ejemplo sigue la práctica recomendada para la comprobación de versión:</span><span class="sxs-lookup"><span data-stu-id="b7e18-216">This example follows the recommended practice for version checking:</span></span>

- <span data-ttu-id="b7e18-217">Comprueba si el valor de la entrada **Release** es *mayor o igual* que el valor de las claves de versión conocidas.</span><span class="sxs-lookup"><span data-stu-id="b7e18-217">It checks whether the value of the **Release** entry is *greater than or equal to* the value of the known release keys.</span></span>

- <span data-ttu-id="b7e18-218">Realiza la comprobación en orden, desde la versión más reciente hasta la más antigua.</span><span class="sxs-lookup"><span data-stu-id="b7e18-218">It checks in order from most recent version to earliest version.</span></span>

<a name="ps_a"></a>

### <a name="use-powershell-to-check-for-a-minimum-required-version"></a><span data-ttu-id="b7e18-219">Uso de PowerShell para comprobar si hay una versión mínima requerida</span><span class="sxs-lookup"><span data-stu-id="b7e18-219">Use PowerShell to check for a minimum-required version</span></span>

<span data-ttu-id="b7e18-220">Use comandos de PowerShell para comprobar el valor de la entrada **Release** de la subclave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span><span class="sxs-lookup"><span data-stu-id="b7e18-220">Use PowerShell commands to check the value of the **Release** entry of the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey.</span></span>

<span data-ttu-id="b7e18-221">En los ejemplos siguientes se comprueba el valor de la entrada **Release** para determinar si está instalado .NET Framework 4.6.2 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="b7e18-221">The following examples check the value of the **Release** entry to determine whether the .NET Framework 4.6.2 or later is installed.</span></span> <span data-ttu-id="b7e18-222">Este código devuelve `True` si está instalado y `False` en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="b7e18-222">This code returns `True` if it's installed and `False` otherwise.</span></span>

```PowerShell
(Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -ge 394802
```

<span data-ttu-id="b7e18-223">Para comprobar si hay una versión mínima requerida de .NET Framework diferente, reemplace `394802` en el ejemplo por un valor de la [tabla de versiones de .NET Framework](#version_table).</span><span class="sxs-lookup"><span data-stu-id="b7e18-223">To check for a different minimum-required .NET Framework version, replace `394802` in the example with a value from the [.NET Framework version table](#version_table).</span></span> <span data-ttu-id="b7e18-224">Use el valor más pequeño que aparezca para esa versión.</span><span class="sxs-lookup"><span data-stu-id="b7e18-224">Use the smallest value shown for that version.</span></span>

## <a name="find-older-net-framework-versions-1-through-4"></a><span data-ttu-id="b7e18-225">Búsqueda de versiones más antiguas de .NET Framework (1 a 4)</span><span class="sxs-lookup"><span data-stu-id="b7e18-225">Find older .NET Framework versions (1 through 4)</span></span>

<a name="net_a"></a>

### <a name="use-registry-editor-older-framework-versions"></a><span data-ttu-id="b7e18-226">Uso del Editor del Registro (versiones anteriores de la plataforma)</span><span class="sxs-lookup"><span data-stu-id="b7e18-226">Use Registry Editor (older framework versions)</span></span>

1. <span data-ttu-id="b7e18-227">En el menú **Inicio**, seleccione **Ejecutar**, escriba *regedit* y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b7e18-227">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>

    <span data-ttu-id="b7e18-228">Debe tener credenciales de administrador para ejecutar regedit.</span><span class="sxs-lookup"><span data-stu-id="b7e18-228">You must have administrative credentials to run regedit.</span></span>

2. <span data-ttu-id="b7e18-229">En el Editor del Registro, abra la subclave siguiente: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:</span><span class="sxs-lookup"><span data-stu-id="b7e18-229">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:</span></span>

    - <span data-ttu-id="b7e18-230">Para las versiones de .NET Framework de 1.1 a 3.5, cada versión instalada aparece como una subclave bajo la subclave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**.</span><span class="sxs-lookup"><span data-stu-id="b7e18-230">For .NET Framework versions 1.1 through 3.5, each installed version is listed as a subkey under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP** subkey.</span></span> <span data-ttu-id="b7e18-231">Por ejemplo, **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**.</span><span class="sxs-lookup"><span data-stu-id="b7e18-231">For example, **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**.</span></span> <span data-ttu-id="b7e18-232">El número de versión se almacena como un valor en la entrada **Version** de la subclave de versión.</span><span class="sxs-lookup"><span data-stu-id="b7e18-232">The version number is stored as a value in the version subkey's **Version** entry.</span></span>

    - <span data-ttu-id="b7e18-233">Para .NET Framework 4, la entrada **Version** se halla bajo la subclave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client**, bajo la subclave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** o bajo ambas subclaves.</span><span class="sxs-lookup"><span data-stu-id="b7e18-233">For .NET Framework 4, the **Version** entry is under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client** subkey, the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** subkey, or under both subkeys.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b7e18-234">La carpeta **NET Framework Setup** del Registro no comienza con un punto.</span><span class="sxs-lookup"><span data-stu-id="b7e18-234">The **NET Framework Setup** folder in the registry does not begin with a period.</span></span>

    <span data-ttu-id="b7e18-235">En la siguiente ilustración se muestra la subclave y su entrada **Version** para .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="b7e18-235">The following figure shows the subkey and its **Version** entry for the .NET Framework 3.5.</span></span>

    <span data-ttu-id="b7e18-236">![Entrada del registro para .NET Framework 3.5.](./media/net-4-and-earlier.png ".NET Framework 3.5 y versiones anteriores")</span><span class="sxs-lookup"><span data-stu-id="b7e18-236">![The registry entry for the .NET Framework 3.5.](./media/net-4-and-earlier.png ".NET Framework 3.5 and earlier versions")</span></span>

<a name="net_c"></a>

### <a name="query-the-registry-using-code-older-framework-versions"></a><span data-ttu-id="b7e18-237">Consultar el registro mediante código (versiones anteriores de la plataforma)</span><span class="sxs-lookup"><span data-stu-id="b7e18-237">Query the registry using code (older framework versions)</span></span>

<span data-ttu-id="b7e18-238">Use la clase <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> para tener acceso a la subclave **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** en el Registro de Windows.</span><span class="sxs-lookup"><span data-stu-id="b7e18-238">Use the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** subkey in the Windows registry.</span></span>

<span data-ttu-id="b7e18-239">En el ejemplo siguiente se buscan las versiones 1 a 4 de .NET Framework que están instaladas:</span><span class="sxs-lookup"><span data-stu-id="b7e18-239">The following example finds the .NET Framework 1 through 4 versions that are installed:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

## <a name="find-clr-versions"></a><span data-ttu-id="b7e18-240">Búsqueda de versiones de CLR</span><span class="sxs-lookup"><span data-stu-id="b7e18-240">Find CLR versions</span></span>

<a name="clr_a"></a>

### <a name="use-clrverexe"></a><span data-ttu-id="b7e18-241">Uso de Clrver.exe</span><span class="sxs-lookup"><span data-stu-id="b7e18-241">Use Clrver.exe</span></span>

<span data-ttu-id="b7e18-242">Use la [herramienta de versión de CLR (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) para determinar qué versiones de CLR están instaladas en un equipo:</span><span class="sxs-lookup"><span data-stu-id="b7e18-242">Use the [CLR Version tool (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) to determine which versions of the CLR are installed on a computer:</span></span>

- <span data-ttu-id="b7e18-243">En un [Símbolo del sistema para desarrolladores de Visual Studio](../tools/developer-command-prompt-for-vs.md), escriba `clrver`.</span><span class="sxs-lookup"><span data-stu-id="b7e18-243">From a [Developer Command Prompt for Visual Studio](../tools/developer-command-prompt-for-vs.md), enter `clrver`.</span></span>

    <span data-ttu-id="b7e18-244">Resultados del ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b7e18-244">Sample output:</span></span>

    ```console
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

<a name="clr_b"></a>

### <a name="use-the-environment-class"></a><span data-ttu-id="b7e18-245">Uso de la clase Environment</span><span class="sxs-lookup"><span data-stu-id="b7e18-245">Use the Environment class</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b7e18-246">Para .NET Framework 4.5 y versiones posteriores, no use la propiedad <xref:System.Environment.Version%2A?displayProperty=nameWithType> para detectar la versión de CLR.</span><span class="sxs-lookup"><span data-stu-id="b7e18-246">For the .NET Framework 4.5 and later versions, don't use the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to detect the version of the CLR.</span></span> <span data-ttu-id="b7e18-247">En su lugar, consultar el Registro como se describe en [Búsqueda de versiones de .NET Framework 4.5 y versiones posteriores con código](#net_d).</span><span class="sxs-lookup"><span data-stu-id="b7e18-247">Instead, query the registry as described in [Find .NET Framework versions 4.5 and later with code](#net_d).</span></span>

1. <span data-ttu-id="b7e18-248">Consulte la propiedad <xref:System.Environment.Version?displayProperty=nameWithType> para recuperar un objeto <xref:System.Version>.</span><span class="sxs-lookup"><span data-stu-id="b7e18-248">Query the <xref:System.Environment.Version?displayProperty=nameWithType> property to retrieve a <xref:System.Version> object.</span></span>

    <span data-ttu-id="b7e18-249">El objeto `System.Version` devuelto identifica la versión de tiempo de ejecución que está ejecutando el código.</span><span class="sxs-lookup"><span data-stu-id="b7e18-249">The returned `System.Version` object identifies the version of the runtime that's currently executing the code.</span></span> <span data-ttu-id="b7e18-250">No devuelve versiones de ensamblado ni otras versiones del runtime que se hayan instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="b7e18-250">It doesn't return assembly versions or other versions of the runtime that may have been installed on the computer.</span></span>

    <span data-ttu-id="b7e18-251">Para las versiones 4, 4.5, 4.5.1 y 4.5.2 de .NET Framework, la representación de cadena del objeto <xref:System.Version> devuelto tiene la forma 4.0.30319.*xxxxx*, donde *xxxxx* es inferior a 42000.</span><span class="sxs-lookup"><span data-stu-id="b7e18-251">For the .NET Framework versions 4, 4.5, 4.5.1, and 4.5.2, the string representation of the returned <xref:System.Version> object has the form 4.0.30319.*xxxxx*, where *xxxxx* is less than 42000.</span></span> <span data-ttu-id="b7e18-252">Para .NET Framework 4.6 y versiones posteriores, tiene la forma 4.0.30319.42000.</span><span class="sxs-lookup"><span data-stu-id="b7e18-252">For the .NET Framework 4.6 and later versions, it has the form 4.0.30319.42000.</span></span>

2. <span data-ttu-id="b7e18-253">Una vez que tenga el objeto `Version`, consúltelo de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="b7e18-253">After you have the `Version` object, query it as follows:</span></span>

   - <span data-ttu-id="b7e18-254">Para el identificador de versión principal (por ejemplo, *4* en la versión 4.0), use la propiedad <xref:System.Version.Major%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b7e18-254">For the major release identifier (for example, *4* for version 4.0), use the <xref:System.Version.Major%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="b7e18-255">Para el identificador de versión secundaria (por ejemplo, *0* en la versión 4.0), use la propiedad <xref:System.Version.Minor%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b7e18-255">For the minor release identifier (for example, *0* for version 4.0), use the <xref:System.Version.Minor%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="b7e18-256">Para la cadena de versión completa (por ejemplo, *4.0.30319.18010*), use el método <xref:System.Version.ToString%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b7e18-256">For the entire version string (for example, *4.0.30319.18010*), use the <xref:System.Version.ToString%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="b7e18-257">Este método devuelve un valor único que refleja la versión del runtime que está ejecutando el código.</span><span class="sxs-lookup"><span data-stu-id="b7e18-257">This method returns a single value that reflects the version of the runtime that's executing the code.</span></span> <span data-ttu-id="b7e18-258">No devuelve versiones de ensamblado ni otras versiones del runtime que se hayan instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="b7e18-258">It doesn't return assembly versions or other runtime versions that may be installed on the computer.</span></span>

<span data-ttu-id="b7e18-259">En el ejemplo siguiente se usa la propiedad <xref:System.Environment.Version%2A?displayProperty=nameWithType> para recuperar la información de la versión de CLR:</span><span class="sxs-lookup"><span data-stu-id="b7e18-259">The following example uses the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to retrieve CLR version information:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a><span data-ttu-id="b7e18-260">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7e18-260">See also</span></span>

- [<span data-ttu-id="b7e18-261">Cómo: Determinar las actualizaciones de .NET Framework que están instaladas</span><span class="sxs-lookup"><span data-stu-id="b7e18-261">How to: Determine which .NET Framework updates are installed</span></span>](how-to-determine-which-net-framework-updates-are-installed.md)
- [<span data-ttu-id="b7e18-262">Instalación de .NET Framework para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="b7e18-262">Install the .NET Framework for developers</span></span>](../install/guide-for-developers.md)
- [<span data-ttu-id="b7e18-263">Versiones y dependencias de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b7e18-263">.NET Framework versions and dependencies</span></span>](versions-and-dependencies.md)

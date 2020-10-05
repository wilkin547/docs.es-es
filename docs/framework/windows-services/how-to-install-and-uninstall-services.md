---
title: Procedimiento Instalar y desinstalar servicios de Windows
description: Vea cómo instalar y desinstalar servicios de Windows. Si va a desarrollar un servicio de Windows con .NET, puede usar InstallUtil.exe o PowerShell.
ms.date: 02/05/2019
helpviewer_keywords:
- Windows Service applications, deploying
- services, uninstalling
- services, installing
- installing Windows Services
- uninstalling applications, apps, Windows services
- installation, Windows services
- uninstalling Windows services
- installutil.exe tool
ms.assetid: c89c5169-f567-4305-9d62-db31a1de5481
ms.openlocfilehash: 6b7cfd8b241df4fe01c9c2a08888c88a1c749d13
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609686"
---
# <a name="how-to-install-and-uninstall-windows-services"></a><span data-ttu-id="776db-104">Procedimiento Instalar y desinstalar servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="776db-104">How to: Install and uninstall Windows services</span></span>

<span data-ttu-id="776db-105">Si desarrolla un servicio de Windows con .NET Framework, puede instalar rápidamente la aplicación de servicio mediante la utilidad de línea de comandos [*InstallUtil.exe*](../tools/installutil-exe-installer-tool.md) o [PowerShell](/powershell/scripting/overview).</span><span class="sxs-lookup"><span data-stu-id="776db-105">If you’re developing a Windows service with the .NET Framework, you can quickly install your service app by using the [*InstallUtil.exe*](../tools/installutil-exe-installer-tool.md) command-line utility or [PowerShell](/powershell/scripting/overview).</span></span> <span data-ttu-id="776db-106">Los desarrolladores que quieran publicar un servicio de Windows que los usuarios puedan instalar y desinstalar pueden utilizar el [conjunto de herramientas WiX](https://wixtoolset.org/) gratuito u otras herramientas comerciales como [Advanced Installer](https://www.advancedinstaller.com/), [InstallShield](https://www.revenera.com/install/products/installshield.html), etc.</span><span class="sxs-lookup"><span data-stu-id="776db-106">Developers who want to release a Windows service that users can install and uninstall can use the free [WiX Toolset](https://wixtoolset.org/) or commercial tools like [Advanced Installer](https://www.advancedinstaller.com/), [InstallShield](https://www.revenera.com/install/products/installshield.html), or others.</span></span> <span data-ttu-id="776db-107">Para más información, consulte [Creación de un paquete de instalador (escritorio de Windows)](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).</span><span class="sxs-lookup"><span data-stu-id="776db-107">For more information, see [Create an installer package (Windows desktop)](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).</span></span>

> [!WARNING]
> <span data-ttu-id="776db-108">Si desea desinstalar un servicio del equipo, no siga los pasos descritos en este artículo.</span><span class="sxs-lookup"><span data-stu-id="776db-108">If you want to uninstall a service from your computer, don’t follow the steps in this article.</span></span> <span data-ttu-id="776db-109">En su lugar, averigüe qué paquete de software o programa ha instalado el servicio y, después, haga clic en **Aplicaciones** en Configuración para desinstalar ese programa.</span><span class="sxs-lookup"><span data-stu-id="776db-109">Instead, find out which program or software package installed the service, and then choose **Apps** in Settings to uninstall that program.</span></span> <span data-ttu-id="776db-110">Tenga en cuenta que muchos servicios forman parte de Windows; si los quita, podría causar inestabilidad en el sistema.</span><span class="sxs-lookup"><span data-stu-id="776db-110">Note that many services are integral parts of Windows; if you remove them, you might cause system instability.</span></span>

<span data-ttu-id="776db-111">Para seguir los pasos de este artículo, primero debe agregar un instalador del servicio al servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="776db-111">To use the steps in this article, you first need to add a service installer to your Windows service.</span></span> <span data-ttu-id="776db-112">Para obtener más información, vea [Tutorial: Creación de una aplicación de un servicio de Windows](walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span><span class="sxs-lookup"><span data-stu-id="776db-112">For more information, see [Walkthrough: Creating a Windows service app](walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>

<span data-ttu-id="776db-113">Los proyectos de servicio de Windows no se pueden ejecutar directamente desde el entorno de desarrollo de Visual Studio presionando F5.</span><span class="sxs-lookup"><span data-stu-id="776db-113">You can't run Windows service projects directly from the Visual Studio development environment by pressing F5.</span></span> <span data-ttu-id="776db-114">Antes de poder ejecutar el proyecto, tendrá que instalar el servicio en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="776db-114">Before you can run the project, you must install the service in the project.</span></span>

> [!TIP]
> <span data-ttu-id="776db-115">Puede usar el **Explorador de servidores** para comprobar que el servicio se ha instalado o desinstalado.</span><span class="sxs-lookup"><span data-stu-id="776db-115">You can use **Server Explorer** to verify that you've installed or uninstalled your service.</span></span> <span data-ttu-id="776db-116">Para más información, vea [CÓMO: Utilizar el Explorador de servidores de Visual Studio .NET](https://support.microsoft.com/help/316649/how-to-use-the-server-explorer-in-visual-studio-net-and-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="776db-116">For more information, see [How to use Server Explorer in Visual Studio](https://support.microsoft.com/help/316649/how-to-use-the-server-explorer-in-visual-studio-net-and-visual-studio).</span></span>

### <a name="install-your-service-manually-using-installutilexe-utility"></a><span data-ttu-id="776db-117">Instalación manual del servicio con la utilidad InstallUtil. exe</span><span class="sxs-lookup"><span data-stu-id="776db-117">Install your service manually using InstallUtil.exe utility</span></span>

1. <span data-ttu-id="776db-118">Desde el menú **Inicio**, seleccione el directorio **Visual Studio \<*version*>** y luego **Símbolo del sistema para desarrolladores de VS\<*version*>** .</span><span class="sxs-lookup"><span data-stu-id="776db-118">From the **Start** menu, select the **Visual Studio \<*version*>** directory, then select **Developer Command Prompt for VS \<*version*>**.</span></span>

     <span data-ttu-id="776db-119">Aparecerá el símbolo del sistema para desarrolladores de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="776db-119">The Developer Command Prompt for Visual Studio appears.</span></span>

2. <span data-ttu-id="776db-120">Obtenga acceso al directorio donde se encuentra el archivo ejecutable compilado del proyecto.</span><span class="sxs-lookup"><span data-stu-id="776db-120">Access the directory where your project's compiled executable file is located.</span></span>

3. <span data-ttu-id="776db-121">Ejecute *InstallUtil.exe* desde la línea de comandos con el archivo ejecutable del proyecto como parámetro:</span><span class="sxs-lookup"><span data-stu-id="776db-121">Run *InstallUtil.exe* from the command prompt with your project's executable as a parameter:</span></span>

    ```console
    installutil <yourproject>.exe
    ```

     <span data-ttu-id="776db-122">Si usa el símbolo del sistema para desarrolladores de Visual Studio, *InstallUtil.exe* debe estar en la ruta de acceso del sistema.</span><span class="sxs-lookup"><span data-stu-id="776db-122">If you’re using the Developer Command Prompt for Visual Studio, *InstallUtil.exe* should be on the system path.</span></span> <span data-ttu-id="776db-123">En caso contrario, puede agregarlo a la ruta de acceso o usar la ruta de acceso completa para invocarlo.</span><span class="sxs-lookup"><span data-stu-id="776db-123">Otherwise, you can add it to the path, or use the fully qualified path to invoke it.</span></span> <span data-ttu-id="776db-124">Esta herramienta se instala con .NET Framework en *%WINDIR%\Microsoft.NET\Framework[64]\\<versión_de_la_plataforma>\>* .</span><span class="sxs-lookup"><span data-stu-id="776db-124">This tool is installed with the .NET Framework in *%WINDIR%\Microsoft.NET\Framework[64]\\<framework_version\>*.</span></span>

     <span data-ttu-id="776db-125">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="776db-125">For example:</span></span>
     - <span data-ttu-id="776db-126">Para la versión de 32 bits de .NET Framework 4 o 4.5 y versiones posteriores, si el directorio de instalación de Windows es *C:\Windows*, la ruta predeterminada es *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.</span><span class="sxs-lookup"><span data-stu-id="776db-126">For the 32-bit version of the .NET Framework 4 or 4.5 and later, if your Windows installation directory is *C:\Windows*, the default path is *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.</span></span>
     - <span data-ttu-id="776db-127">Para la versión de 64 bits de .NET Framework 4 o 4.5 y versiones posteriores, la ruta de acceso predeterminada es *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span><span class="sxs-lookup"><span data-stu-id="776db-127">For the 64-bit version of the .NET Framework 4 or 4.5 and later, the default path is *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span></span>

### <a name="uninstall-your-service-manually-using-installutilexe-utility"></a><span data-ttu-id="776db-128">Desinstalación manual del servicio con la utilidad InstallUtil.exe</span><span class="sxs-lookup"><span data-stu-id="776db-128">Uninstall your service manually using InstallUtil.exe utility</span></span>

1. <span data-ttu-id="776db-129">Desde el menú **Inicio**, seleccione el directorio **Visual Studio \<*version*>** y luego **Símbolo del sistema para desarrolladores para VS\<*version*>** .</span><span class="sxs-lookup"><span data-stu-id="776db-129">From the **Start** menu, select the **Visual Studio \<*version*>** directory, then select **Developer Command Prompt for VS \<*version*>**.</span></span>

     <span data-ttu-id="776db-130">Aparecerá el símbolo del sistema para desarrolladores de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="776db-130">The Developer Command Prompt for Visual Studio appears.</span></span>

2. <span data-ttu-id="776db-131">Ejecute *InstallUtil.exe* desde la línea de comandos con la salida del proyecto como parámetro:</span><span class="sxs-lookup"><span data-stu-id="776db-131">Run *InstallUtil.exe* from the command prompt with your project's output as a parameter:</span></span>

    ```console
    installutil /u <yourproject>.exe
    ```

3. <span data-ttu-id="776db-132">Después de eliminar el archivo ejecutable de un servicio, es posible que el servicio permanezca en el Registro.</span><span class="sxs-lookup"><span data-stu-id="776db-132">After the executable for a service is deleted, the service might still be present in the registry.</span></span> <span data-ttu-id="776db-133">En ese caso, use el comando [sc delete](/windows-server/administration/windows-commands/sc-delete) para quitar la entrada del servicio del Registro.</span><span class="sxs-lookup"><span data-stu-id="776db-133">If that's the case, use the command [sc delete](/windows-server/administration/windows-commands/sc-delete) to remove the entry for the service from the registry.</span></span>

### <a name="install-your-service-manually-using-powershell"></a><span data-ttu-id="776db-134">Instalación manual del servicio con PowerShell</span><span class="sxs-lookup"><span data-stu-id="776db-134">Install your service manually using PowerShell</span></span>

1. <span data-ttu-id="776db-135">En el menú **Inicio**, seleccione el directorio **Windows PowerShell** y elija **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="776db-135">From the **Start** menu, select the **Windows PowerShell** directory, then select **Windows PowerShell**.</span></span>

2. <span data-ttu-id="776db-136">Obtenga acceso al directorio donde se encuentra el archivo ejecutable compilado del proyecto.</span><span class="sxs-lookup"><span data-stu-id="776db-136">Access the directory where your project's compiled executable file is located.</span></span>

3. <span data-ttu-id="776db-137">Ejecute el cmdlet [**New-Service**](/powershell/module/microsoft.powershell.management/new-service) con la salida del proyecto y un nombre de servicio como parámetros:</span><span class="sxs-lookup"><span data-stu-id="776db-137">Run the [**New-Service**](/powershell/module/microsoft.powershell.management/new-service) cmdlet with the with your project's output and a service name as parameters:</span></span>

    ```powershell
    New-Service -Name "YourServiceName" -BinaryPathName <yourproject>.exe
    ```

### <a name="uninstall-your-service-manually-using-powershell"></a><span data-ttu-id="776db-138">Desinstalación manual del servicio con PowerShell</span><span class="sxs-lookup"><span data-stu-id="776db-138">Uninstall your service manually using PowerShell</span></span>

1. <span data-ttu-id="776db-139">En el menú **Inicio**, seleccione el directorio **Windows PowerShell** y elija **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="776db-139">From the **Start** menu, select the **Windows PowerShell** directory, then select **Windows PowerShell**.</span></span>

2. <span data-ttu-id="776db-140">Ejecute el cmdlet [**Remove-Service**](/powershell/module/microsoft.powershell.management/remove-service) con el nombre del servicio como parámetro:</span><span class="sxs-lookup"><span data-stu-id="776db-140">Run the [**Remove-Service**](/powershell/module/microsoft.powershell.management/remove-service) cmdlet with the name of your service as parameter:</span></span>

    ```powershell
    Remove-Service -Name "YourServiceName"
    ```

3. <span data-ttu-id="776db-141">Después de eliminar el archivo ejecutable de un servicio, es posible que el servicio permanezca en el Registro.</span><span class="sxs-lookup"><span data-stu-id="776db-141">After the executable for a service is deleted, the service might still be present in the registry.</span></span> <span data-ttu-id="776db-142">En ese caso, use el comando [sc delete](/windows-server/administration/windows-commands/sc-delete) para quitar la entrada del servicio del Registro.</span><span class="sxs-lookup"><span data-stu-id="776db-142">If that's the case, use the command [sc delete](/windows-server/administration/windows-commands/sc-delete) to remove the entry for the service from the registry.</span></span>

    ```powershell
    sc.exe delete "YourServiceName"
    ```

## <a name="see-also"></a><span data-ttu-id="776db-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="776db-143">See also</span></span>

- [<span data-ttu-id="776db-144">Introducción a las aplicaciones de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="776db-144">Introduction to Windows service applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="776db-145">Cómo: Crear servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="776db-145">How to: Create Windows services</span></span>](how-to-create-windows-services.md)
- [<span data-ttu-id="776db-146">Cómo: Agregar instaladores a una aplicación de servicio</span><span class="sxs-lookup"><span data-stu-id="776db-146">How to: Add installers to your service application</span></span>](how-to-add-installers-to-your-service-application.md)
- [<span data-ttu-id="776db-147">Installutil.exe (Herramienta Installer)</span><span class="sxs-lookup"><span data-stu-id="776db-147">Installutil.exe (Installer tool)</span></span>](../tools/installutil-exe-installer-tool.md)

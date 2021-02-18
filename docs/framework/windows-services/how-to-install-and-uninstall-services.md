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
ms.openlocfilehash: 0803d9908a9b92df0d17537ee4db2d798a2a07cc
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100433426"
---
# <a name="how-to-install-and-uninstall-windows-services"></a><span data-ttu-id="41b8a-104">Procedimiento Instalar y desinstalar servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="41b8a-104">How to: Install and uninstall Windows services</span></span>

<span data-ttu-id="41b8a-105">Si va a desarrollar un servicio de Windows con .NET Framework, puede instalar rápidamente la aplicación de servicio mediante la utilidad de línea de comandos [*InstallUtil.exe*](../tools/installutil-exe-installer-tool.md) o [PowerShell](/powershell/scripting/overview).</span><span class="sxs-lookup"><span data-stu-id="41b8a-105">If you're developing a Windows service with the .NET Framework, you can quickly install your service app by using the [*InstallUtil.exe*](../tools/installutil-exe-installer-tool.md) command-line utility or [PowerShell](/powershell/scripting/overview).</span></span> <span data-ttu-id="41b8a-106">Los desarrolladores que quieran publicar un servicio de Windows que los usuarios puedan instalar y desinstalar pueden utilizar el [conjunto de herramientas WiX](https://wixtoolset.org/) gratuito u otras herramientas comerciales como [Advanced Installer](https://www.advancedinstaller.com/), [InstallShield](https://www.revenera.com/install/products/installshield.html), etc.</span><span class="sxs-lookup"><span data-stu-id="41b8a-106">Developers who want to release a Windows service that users can install and uninstall can use the free [WiX Toolset](https://wixtoolset.org/) or commercial tools like [Advanced Installer](https://www.advancedinstaller.com/), [InstallShield](https://www.revenera.com/install/products/installshield.html), or others.</span></span> <span data-ttu-id="41b8a-107">Para más información, consulte [Creación de un paquete de instalador (escritorio de Windows)](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).</span><span class="sxs-lookup"><span data-stu-id="41b8a-107">For more information, see [Create an installer package (Windows desktop)](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).</span></span>

> [!WARNING]
> <span data-ttu-id="41b8a-108">Si quiere desinstalar un servicio del equipo, no siga los pasos descritos en este artículo.</span><span class="sxs-lookup"><span data-stu-id="41b8a-108">If you want to uninstall a service from your computer, don't follow the steps in this article.</span></span> <span data-ttu-id="41b8a-109">En su lugar, averigüe qué paquete de software o programa ha instalado el servicio y, después, haga clic en **Aplicaciones** en Configuración para desinstalar ese programa.</span><span class="sxs-lookup"><span data-stu-id="41b8a-109">Instead, find out which program or software package installed the service, and then choose **Apps** in Settings to uninstall that program.</span></span> <span data-ttu-id="41b8a-110">Tenga en cuenta que muchos servicios forman parte de Windows; si los quita, podría causar inestabilidad en el sistema.</span><span class="sxs-lookup"><span data-stu-id="41b8a-110">Note that many services are integral parts of Windows; if you remove them, you might cause system instability.</span></span>

<span data-ttu-id="41b8a-111">Para seguir los pasos de este artículo, primero debe agregar un instalador del servicio al servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="41b8a-111">To use the steps in this article, you first need to add a service installer to your Windows service.</span></span> <span data-ttu-id="41b8a-112">Para obtener más información, vea [Tutorial: Creación de una aplicación de un servicio de Windows](walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span><span class="sxs-lookup"><span data-stu-id="41b8a-112">For more information, see [Walkthrough: Creating a Windows service app](walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>

<span data-ttu-id="41b8a-113">Los proyectos de servicio de Windows no se pueden ejecutar directamente desde el entorno de desarrollo de Visual Studio presionando F5.</span><span class="sxs-lookup"><span data-stu-id="41b8a-113">You can't run Windows service projects directly from the Visual Studio development environment by pressing F5.</span></span> <span data-ttu-id="41b8a-114">Antes de poder ejecutar el proyecto, tendrá que instalar el servicio en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="41b8a-114">Before you can run the project, you must install the service in the project.</span></span>

> [!TIP]
> <span data-ttu-id="41b8a-115">Puede usar el **Explorador de servidores** para comprobar que el servicio se ha instalado o desinstalado.</span><span class="sxs-lookup"><span data-stu-id="41b8a-115">You can use **Server Explorer** to verify that you've installed or uninstalled your service.</span></span>

## <a name="install-using-installutilexe-utility"></a><span data-ttu-id="41b8a-116">Instalación mediante la utilidad InstallUtil.exe</span><span class="sxs-lookup"><span data-stu-id="41b8a-116">Install using InstallUtil.exe utility</span></span>

1. <span data-ttu-id="41b8a-117">Desde el menú **Inicio**, seleccione el directorio **Visual Studio \<*version*>** y luego **Símbolo del sistema para desarrolladores para VS\<*version*>** .</span><span class="sxs-lookup"><span data-stu-id="41b8a-117">From the **Start** menu, select the **Visual Studio \<*version*>** directory, then select **Developer Command Prompt for VS \<*version*>**.</span></span>

     <span data-ttu-id="41b8a-118">Aparecerá el símbolo del sistema para desarrolladores de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="41b8a-118">The Developer Command Prompt for Visual Studio appears.</span></span>

2. <span data-ttu-id="41b8a-119">Obtenga acceso al directorio donde se encuentra el archivo ejecutable compilado del proyecto.</span><span class="sxs-lookup"><span data-stu-id="41b8a-119">Access the directory where your project's compiled executable file is located.</span></span>

3. <span data-ttu-id="41b8a-120">Ejecute *InstallUtil.exe* desde la línea de comandos con el archivo ejecutable del proyecto como parámetro:</span><span class="sxs-lookup"><span data-stu-id="41b8a-120">Run *InstallUtil.exe* from the command prompt with your project's executable as a parameter:</span></span>

    ```console
    installutil <yourproject>.exe
    ```

     <span data-ttu-id="41b8a-121">Si usa el símbolo del sistema para desarrolladores de Visual Studio, *InstallUtil.exe* debe estar en la ruta de acceso del sistema.</span><span class="sxs-lookup"><span data-stu-id="41b8a-121">If you’re using the Developer Command Prompt for Visual Studio, *InstallUtil.exe* should be on the system path.</span></span> <span data-ttu-id="41b8a-122">En caso contrario, puede agregarlo a la ruta de acceso o usar la ruta de acceso completa para invocarlo.</span><span class="sxs-lookup"><span data-stu-id="41b8a-122">Otherwise, you can add it to the path, or use the fully qualified path to invoke it.</span></span> <span data-ttu-id="41b8a-123">Esta herramienta se instala con .NET Framework en *%WINDIR%\Microsoft.NET\Framework[64]\\<versión_de_la_plataforma>\>* .</span><span class="sxs-lookup"><span data-stu-id="41b8a-123">This tool is installed with the .NET Framework in *%WINDIR%\Microsoft.NET\Framework[64]\\<framework_version\>*.</span></span>

     <span data-ttu-id="41b8a-124">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="41b8a-124">For example:</span></span>
     - <span data-ttu-id="41b8a-125">Para la versión de 32 bits de .NET Framework 4 o 4.5 y versiones posteriores, si el directorio de instalación de Windows es *C:\Windows*, la ruta predeterminada es *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.</span><span class="sxs-lookup"><span data-stu-id="41b8a-125">For the 32-bit version of the .NET Framework 4 or 4.5 and later, if your Windows installation directory is *C:\Windows*, the default path is *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.</span></span>
     - <span data-ttu-id="41b8a-126">Para la versión de 64 bits de .NET Framework 4 o 4.5 y versiones posteriores, la ruta de acceso predeterminada es *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span><span class="sxs-lookup"><span data-stu-id="41b8a-126">For the 64-bit version of the .NET Framework 4 or 4.5 and later, the default path is *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span></span>

## <a name="uninstall-using-installutilexe-utility"></a><span data-ttu-id="41b8a-127">Desinstalación mediante la utilidad InstallUtil.exe</span><span class="sxs-lookup"><span data-stu-id="41b8a-127">Uninstall using InstallUtil.exe utility</span></span>

1. <span data-ttu-id="41b8a-128">Desde el menú **Inicio**, seleccione el directorio **Visual Studio \<*version*>** y luego **Símbolo del sistema para desarrolladores para VS\<*version*>** .</span><span class="sxs-lookup"><span data-stu-id="41b8a-128">From the **Start** menu, select the **Visual Studio \<*version*>** directory, then select **Developer Command Prompt for VS \<*version*>**.</span></span>

     <span data-ttu-id="41b8a-129">Aparecerá el símbolo del sistema para desarrolladores de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="41b8a-129">The Developer Command Prompt for Visual Studio appears.</span></span>

2. <span data-ttu-id="41b8a-130">Ejecute *InstallUtil.exe* desde la línea de comandos con la salida del proyecto como parámetro:</span><span class="sxs-lookup"><span data-stu-id="41b8a-130">Run *InstallUtil.exe* from the command prompt with your project's output as a parameter:</span></span>

    ```console
    installutil /u <yourproject>.exe
    ```

3. <span data-ttu-id="41b8a-131">Después de eliminar el archivo ejecutable de un servicio, es posible que el servicio permanezca en el Registro.</span><span class="sxs-lookup"><span data-stu-id="41b8a-131">After the executable for a service is deleted, the service might still be present in the registry.</span></span> <span data-ttu-id="41b8a-132">En ese caso, use el comando [sc delete](/windows-server/administration/windows-commands/sc-delete) para quitar la entrada del servicio del Registro.</span><span class="sxs-lookup"><span data-stu-id="41b8a-132">If that's the case, use the command [sc delete](/windows-server/administration/windows-commands/sc-delete) to remove the entry for the service from the registry.</span></span>

## <a name="install-using-powershell"></a><span data-ttu-id="41b8a-133">Instalación mediante PowerShell</span><span class="sxs-lookup"><span data-stu-id="41b8a-133">Install using PowerShell</span></span>

1. <span data-ttu-id="41b8a-134">En el menú **Inicio**, seleccione el directorio **Windows PowerShell** y elija **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="41b8a-134">From the **Start** menu, select the **Windows PowerShell** directory, then select **Windows PowerShell**.</span></span>

2. <span data-ttu-id="41b8a-135">Obtenga acceso al directorio donde se encuentra el archivo ejecutable compilado del proyecto.</span><span class="sxs-lookup"><span data-stu-id="41b8a-135">Access the directory where your project's compiled executable file is located.</span></span>

3. <span data-ttu-id="41b8a-136">Ejecute el cmdlet [**New-Service**](/powershell/module/microsoft.powershell.management/new-service) con la salida del proyecto y un nombre de servicio como parámetros:</span><span class="sxs-lookup"><span data-stu-id="41b8a-136">Run the [**New-Service**](/powershell/module/microsoft.powershell.management/new-service) cmdlet with the with your project's output and a service name as parameters:</span></span>

    ```powershell
    New-Service -Name "YourServiceName" -BinaryPathName <yourproject>.exe
    ```

## <a name="uninstall-using-powershell"></a><span data-ttu-id="41b8a-137">Desinstalación mediante PowerShell</span><span class="sxs-lookup"><span data-stu-id="41b8a-137">Uninstall using PowerShell</span></span>

1. <span data-ttu-id="41b8a-138">En el menú **Inicio**, seleccione el directorio **Windows PowerShell** y elija **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="41b8a-138">From the **Start** menu, select the **Windows PowerShell** directory, then select **Windows PowerShell**.</span></span>

2. <span data-ttu-id="41b8a-139">Ejecute el cmdlet [**Remove-Service**](/powershell/module/microsoft.powershell.management/remove-service) con el nombre del servicio como parámetro:</span><span class="sxs-lookup"><span data-stu-id="41b8a-139">Run the [**Remove-Service**](/powershell/module/microsoft.powershell.management/remove-service) cmdlet with the name of your service as parameter:</span></span>

    ```powershell
    Remove-Service -Name "YourServiceName"
    ```

3. <span data-ttu-id="41b8a-140">Después de eliminar el archivo ejecutable de un servicio, es posible que el servicio permanezca en el Registro.</span><span class="sxs-lookup"><span data-stu-id="41b8a-140">After the executable for a service is deleted, the service might still be present in the registry.</span></span> <span data-ttu-id="41b8a-141">En ese caso, use el comando [sc delete](/windows-server/administration/windows-commands/sc-delete) para quitar la entrada del servicio del Registro.</span><span class="sxs-lookup"><span data-stu-id="41b8a-141">If that's the case, use the command [sc delete](/windows-server/administration/windows-commands/sc-delete) to remove the entry for the service from the registry.</span></span>

    ```powershell
    sc.exe delete "YourServiceName"
    ```

## <a name="see-also"></a><span data-ttu-id="41b8a-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="41b8a-142">See also</span></span>

- [<span data-ttu-id="41b8a-143">Introducción a las aplicaciones de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="41b8a-143">Introduction to Windows service applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="41b8a-144">Cómo: Crear servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="41b8a-144">How to: Create Windows services</span></span>](how-to-create-windows-services.md)
- [<span data-ttu-id="41b8a-145">Cómo: Agregar instaladores a una aplicación de servicio</span><span class="sxs-lookup"><span data-stu-id="41b8a-145">How to: Add installers to your service application</span></span>](how-to-add-installers-to-your-service-application.md)
- [<span data-ttu-id="41b8a-146">Installutil.exe (Herramienta Installer)</span><span class="sxs-lookup"><span data-stu-id="41b8a-146">Installutil.exe (Installer tool)</span></span>](../tools/installutil-exe-installer-tool.md)

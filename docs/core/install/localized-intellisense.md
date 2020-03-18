---
title: Instalación de archivos de IntelliSense localizados
description: Obtenga información sobre cómo configurar su máquina de desarrollo con el fin de usar archivos de IntelliSense localizados para los proyectos de .NET Core en Visual Studio.
ms.date: 01/23/2020
ms.openlocfilehash: e45e225e58865ca2b529000ada0984fbeca850f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "78157718"
---
# <a name="how-to-install-localized-intellisense-files-for-net-core"></a><span data-ttu-id="d56d2-103">Procedimiento para instalar archivos de IntelliSense localizados para .NET Core</span><span class="sxs-lookup"><span data-stu-id="d56d2-103">How to install localized IntelliSense files for .NET Core</span></span>

<span data-ttu-id="d56d2-104">[IntelliSense](/visualstudio/ide/using-intellisense) es una característica que ayuda a completar código y que está disponible en diferentes entornos de desarrollo integrado (IDE), como Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d56d2-104">[IntelliSense](/visualstudio/ide/using-intellisense) is a code-completion aid that is available in different integrated development environments (IDEs), such as Visual Studio.</span></span> <span data-ttu-id="d56d2-105">De manera predeterminada, al desarrollar proyectos de .NET Core, el SDK solo incluye la versión en inglés de los archivos de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="d56d2-105">By default, when you're developing .NET Core projects, the SDK only includes the English version of the IntelliSense files.</span></span> <span data-ttu-id="d56d2-106">En este artículo, se explica lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d56d2-106">This article explains:</span></span>

- <span data-ttu-id="d56d2-107">Procedimiento para instalar la versión localizada de estos archivos.</span><span class="sxs-lookup"><span data-stu-id="d56d2-107">How to install the localized version of those files.</span></span>
- <span data-ttu-id="d56d2-108">Procedimiento para modificar la instalación de Visual Studio para usar otro idioma.</span><span class="sxs-lookup"><span data-stu-id="d56d2-108">How to modify the Visual Studio installation to use a different language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d56d2-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d56d2-109">Prerequisites</span></span>

- <span data-ttu-id="d56d2-110">[SDK de .NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core) o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="d56d2-110">[.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) or a later version.</span></span>
- <span data-ttu-id="d56d2-111">[Versión 16.3 de Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) u otra posterior.</span><span class="sxs-lookup"><span data-stu-id="d56d2-111">[Visual Studio 2019 version 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or a later version.</span></span>

## <a name="download-and-install-the-localized-intellisense-files"></a><span data-ttu-id="d56d2-112">Descarga e instalación de los archivos de IntelliSense localizados</span><span class="sxs-lookup"><span data-stu-id="d56d2-112">Download and install the localized IntelliSense files</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d56d2-113">Para poder realizar este procedimiento, necesita tener permiso de administrador para copiar los archivos de IntelliSense en la carpeta de instalación de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d56d2-113">This procedure requires that you have administrator permission to copy the IntelliSense files to the .NET Core installation folder.</span></span>

1. <span data-ttu-id="d56d2-114">Vaya a la página [Descarga de archivos de IntelliSense](https://dotnet.microsoft.com/download/dotnet-core/intellisense).</span><span class="sxs-lookup"><span data-stu-id="d56d2-114">Go to the [Download IntelliSense files](https://dotnet.microsoft.com/download/dotnet-core/intellisense) page.</span></span>

1. <span data-ttu-id="d56d2-115">Descargue el archivo de IntelliSense en el idioma y la versión que prefiera.</span><span class="sxs-lookup"><span data-stu-id="d56d2-115">Download the IntelliSense file for the language and version you'd like to use.</span></span>

1. <span data-ttu-id="d56d2-116">Extraiga el contenido del archivo ZIP.</span><span class="sxs-lookup"><span data-stu-id="d56d2-116">Extract the contents of the zip file.</span></span>

1. <span data-ttu-id="d56d2-117">Vaya a la carpeta Intellisense de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d56d2-117">Navigate to the .NET Core Intellisense folder.</span></span>

   1. <span data-ttu-id="d56d2-118">Vaya a la carpeta de instalación de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d56d2-118">Navigate to the .NET Core installation folder.</span></span> <span data-ttu-id="d56d2-119">De manera predeterminada, se encuentra en *%Archivos de programa%\dotnet\packs*.</span><span class="sxs-lookup"><span data-stu-id="d56d2-119">By default, it's under *%ProgramFiles%\dotnet\packs*.</span></span>
   1. <span data-ttu-id="d56d2-120">Elija para qué SDK quiere instalar el archivo de IntelliSense y vaya a la ruta de acceso correspondiente.</span><span class="sxs-lookup"><span data-stu-id="d56d2-120">Choose which SDK you want to install the IntelliSense for, and navigate to the associated path.</span></span> <span data-ttu-id="d56d2-121">Dispone de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d56d2-121">You have the following options:</span></span>

      | <span data-ttu-id="d56d2-122">Tipo de SDK</span><span class="sxs-lookup"><span data-stu-id="d56d2-122">SDK type</span></span>        | <span data-ttu-id="d56d2-123">Path</span><span class="sxs-lookup"><span data-stu-id="d56d2-123">Path</span></span>                               |
      | --------------- | ---------------------------------- |
      | <span data-ttu-id="d56d2-124">.NET Core</span><span class="sxs-lookup"><span data-stu-id="d56d2-124">.NET Core</span></span>       | <span data-ttu-id="d56d2-125">*Microsoft.NETCore.App.Ref*</span><span class="sxs-lookup"><span data-stu-id="d56d2-125">*Microsoft.NETCore.App.Ref*</span></span>        |
      | <span data-ttu-id="d56d2-126">Escritorio de Windows</span><span class="sxs-lookup"><span data-stu-id="d56d2-126">Windows Desktop</span></span> | <span data-ttu-id="d56d2-127">*Microsoft.WindowsDesktop.App.Ref*</span><span class="sxs-lookup"><span data-stu-id="d56d2-127">*Microsoft.WindowsDesktop.App.Ref*</span></span> |
      | <span data-ttu-id="d56d2-128">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="d56d2-128">.NET Standard</span></span>   | <span data-ttu-id="d56d2-129">*NETStandard.Library.Ref*</span><span class="sxs-lookup"><span data-stu-id="d56d2-129">*NETStandard.Library.Ref*</span></span>          |

   1. <span data-ttu-id="d56d2-130">Vaya a la versión para la que quiera instalar el archivo de IntelliSense localizado.</span><span class="sxs-lookup"><span data-stu-id="d56d2-130">Navigate to the version you want to install the localized IntelliSense for.</span></span> <span data-ttu-id="d56d2-131">Por ejemplo, la *3.1.0*.</span><span class="sxs-lookup"><span data-stu-id="d56d2-131">For example, *3.1.0*.</span></span>
   1. <span data-ttu-id="d56d2-132">Abra la carpeta *ref*.</span><span class="sxs-lookup"><span data-stu-id="d56d2-132">Open the *ref* folder.</span></span>
   1. <span data-ttu-id="d56d2-133">Abra la carpeta del moniker.</span><span class="sxs-lookup"><span data-stu-id="d56d2-133">Open the moniker folder.</span></span> <span data-ttu-id="d56d2-134">Por ejemplo, *netcoreapp3.1*.</span><span class="sxs-lookup"><span data-stu-id="d56d2-134">For example, *netcoreapp3.1*.</span></span>

   <span data-ttu-id="d56d2-135">Así pues, la ruta de acceso completa tendrá un aspecto similar al siguiente: *C:\Archivos de programa\dotnet\packs\Microsoft.NETCore.App.Ref\3.1.0\ref\netcoreapp3.1*.</span><span class="sxs-lookup"><span data-stu-id="d56d2-135">So, the full path that you'd navigate to would look similar to *C:\Program Files\dotnet\packs\Microsoft.NETCore.App.Ref\3.1.0\ref\netcoreapp3.1*.</span></span>

1. <span data-ttu-id="d56d2-136">Cree una subcarpeta en la carpeta del moniker que acaba de abrir.</span><span class="sxs-lookup"><span data-stu-id="d56d2-136">Create a subfolder inside the moniker folder you just opened.</span></span> <span data-ttu-id="d56d2-137">El nombre de la carpeta indicará el idioma que quiere usar.</span><span class="sxs-lookup"><span data-stu-id="d56d2-137">The name of the folder indicates which language you want to use.</span></span> <span data-ttu-id="d56d2-138">En la siguiente tabla, se especifican las diferentes opciones:</span><span class="sxs-lookup"><span data-stu-id="d56d2-138">The following table specifies the different options:</span></span>

   | <span data-ttu-id="d56d2-139">Lenguaje</span><span class="sxs-lookup"><span data-stu-id="d56d2-139">Language</span></span>              | <span data-ttu-id="d56d2-140">Nombre de carpeta</span><span class="sxs-lookup"><span data-stu-id="d56d2-140">Folder name</span></span> |
   | --------------------- | ----------- |
   | <span data-ttu-id="d56d2-141">Portugués (Brasil)</span><span class="sxs-lookup"><span data-stu-id="d56d2-141">Brazilian Portuguese</span></span>  | <span data-ttu-id="d56d2-142">*pt-br*</span><span class="sxs-lookup"><span data-stu-id="d56d2-142">*pt-br*</span></span>     |
   | <span data-ttu-id="d56d2-143">Chino simplificado</span><span class="sxs-lookup"><span data-stu-id="d56d2-143">Chinese (simplified)</span></span>  | <span data-ttu-id="d56d2-144">*zh-hans*</span><span class="sxs-lookup"><span data-stu-id="d56d2-144">*zh-hans*</span></span>   |
   | <span data-ttu-id="d56d2-145">Chino tradicional</span><span class="sxs-lookup"><span data-stu-id="d56d2-145">Chinese (traditional)</span></span> | <span data-ttu-id="d56d2-146">*zh-hant*</span><span class="sxs-lookup"><span data-stu-id="d56d2-146">*zh-hant*</span></span>   |
   | <span data-ttu-id="d56d2-147">Francés</span><span class="sxs-lookup"><span data-stu-id="d56d2-147">French</span></span>                | <span data-ttu-id="d56d2-148">*fr*</span><span class="sxs-lookup"><span data-stu-id="d56d2-148">*fr*</span></span>        |
   | <span data-ttu-id="d56d2-149">Alemán</span><span class="sxs-lookup"><span data-stu-id="d56d2-149">German</span></span>                | <span data-ttu-id="d56d2-150">*de*</span><span class="sxs-lookup"><span data-stu-id="d56d2-150">*de*</span></span>        |
   | <span data-ttu-id="d56d2-151">Italiano</span><span class="sxs-lookup"><span data-stu-id="d56d2-151">Italian</span></span>               | <span data-ttu-id="d56d2-152">*it*</span><span class="sxs-lookup"><span data-stu-id="d56d2-152">*it*</span></span>        |
   | <span data-ttu-id="d56d2-153">Japonés</span><span class="sxs-lookup"><span data-stu-id="d56d2-153">Japanese</span></span>              | <span data-ttu-id="d56d2-154">*ja*</span><span class="sxs-lookup"><span data-stu-id="d56d2-154">*ja*</span></span>        |
   | <span data-ttu-id="d56d2-155">Coreano</span><span class="sxs-lookup"><span data-stu-id="d56d2-155">Korean</span></span>                | <span data-ttu-id="d56d2-156">*ko*</span><span class="sxs-lookup"><span data-stu-id="d56d2-156">*ko*</span></span>        |
   | <span data-ttu-id="d56d2-157">Ruso</span><span class="sxs-lookup"><span data-stu-id="d56d2-157">Russian</span></span>               | <span data-ttu-id="d56d2-158">*ru*</span><span class="sxs-lookup"><span data-stu-id="d56d2-158">*ru*</span></span>        |
   | <span data-ttu-id="d56d2-159">Español</span><span class="sxs-lookup"><span data-stu-id="d56d2-159">Spanish</span></span>               | <span data-ttu-id="d56d2-160">*es*</span><span class="sxs-lookup"><span data-stu-id="d56d2-160">*es*</span></span>        |

1. <span data-ttu-id="d56d2-161">Copie en esta nueva carpeta los archivos *.xml* que ha extraído en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="d56d2-161">Copy the *.xml* files you extracted on step 3 to this new folder.</span></span> <span data-ttu-id="d56d2-162">Los archivos *.xml* se mostrarán agrupados según las diferentes carpetas de SDK, de modo que debe copiarlos en la del SDK que haya elegido en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="d56d2-162">The *.xml* files are broken down by SDK folders, so copy them to the matching SDK you chose on step 4.</span></span>

## <a name="modify-visual-studio-language"></a><span data-ttu-id="d56d2-163">Modificación del idioma de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d56d2-163">Modify Visual Studio language</span></span>

<span data-ttu-id="d56d2-164">Para que Visual Studio use otro idioma para IntelliSense, instale el paquete de idioma correspondiente.</span><span class="sxs-lookup"><span data-stu-id="d56d2-164">For Visual Studio to use a different language for IntelliSense, install the appropriate language pack.</span></span> <span data-ttu-id="d56d2-165">Esto se puede realizar [durante la instalación](/visualstudio/install/install-visual-studio#step-6---install-language-packs-optional) o después modificando la instalación de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d56d2-165">This can be done [during installation](/visualstudio/install/install-visual-studio#step-6---install-language-packs-optional) or at a later time by modifying the Visual Studio installation.</span></span> <span data-ttu-id="d56d2-166">Si ya tiene Visual Studio configurado en el idioma que quiere, su instalación de IntelliSense está lista.</span><span class="sxs-lookup"><span data-stu-id="d56d2-166">If you already have Visual Studio configured to the language of your choice, your IntelliSense installation is ready.</span></span>

### <a name="install-the-language-pack"></a><span data-ttu-id="d56d2-167">Instalación del paquete de idioma</span><span class="sxs-lookup"><span data-stu-id="d56d2-167">Install the language pack</span></span>

<span data-ttu-id="d56d2-168">Si no ha instalado el paquete de idioma deseado durante la configuración, actualice Visual Studio como se indica a continuación para instalar el paquete de idioma:</span><span class="sxs-lookup"><span data-stu-id="d56d2-168">If you didn't install the desired language pack during setup, update Visual Studio as follows to install the language pack:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d56d2-169">Para instalar, actualizar o modificar Visual Studio, debe iniciar sesión con una cuenta que tenga permisos de administrador.</span><span class="sxs-lookup"><span data-stu-id="d56d2-169">To install, update, or modify Visual Studio, you must log on with an account that has administrator permission.</span></span> <span data-ttu-id="d56d2-170">Para obtener más información, consulte [Permisos de usuario y Visual Studio](/visualstudio/ide/user-permissions-and-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="d56d2-170">For more information, see [User permissions and Visual Studio](/visualstudio/ide/user-permissions-and-visual-studio).</span></span>

1. <span data-ttu-id="d56d2-171">Busque el instalador de Visual Studio en su equipo.</span><span class="sxs-lookup"><span data-stu-id="d56d2-171">Find the Visual Studio Installer on your computer.</span></span>

   <span data-ttu-id="d56d2-172">Por ejemplo, en un equipo que ejecuta Windows 10, seleccione **Iniciar** y, después, desplácese hasta la letra **I** donde lo verá como **Instalador de Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="d56d2-172">For example, on a computer running Windows 10, select **Start**, and then scroll to the letter **V**, where it's listed as **Visual Studio Installer**.</span></span>

   ![Apertura del Instalador de Visual Studio desde Windows](./media/localized-intellisense/vs-installer-windows-start.png)

   > [!NOTE]
   > <span data-ttu-id="d56d2-174">También pude encontrar el instalador de Visual Studio en la siguiente ubicación:</span><span class="sxs-lookup"><span data-stu-id="d56d2-174">You can also find the Visual Studio Installer in the following location:</span></span>
   >
   > `C:\Program Files (x86)\Microsoft Visual Studio\Installer\vs_installer.exe`

   <span data-ttu-id="d56d2-175">Es posible que tenga que actualizar el instalador antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="d56d2-175">You might have to update the installer before continuing.</span></span> <span data-ttu-id="d56d2-176">De ser así, siga las indicaciones.</span><span class="sxs-lookup"><span data-stu-id="d56d2-176">If so, follow the prompts.</span></span>

1. <span data-ttu-id="d56d2-177">En el instalador, busque la edición de Visual Studio a la que quiera agregar el paquete de idioma y, luego, elija **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="d56d2-177">In the installer, look for the edition of Visual Studio that you want to add the language pack to, and then choose **Modify**.</span></span>

   ![Actualización o modificación de Visual Studio](./media/localized-intellisense/vs-installer-modify.png)

   > [!IMPORTANT]
   > <span data-ttu-id="d56d2-179">Si no ve el botón **Modificar**, pero sí el botón **Actualizar**, significa que necesita actualizar su versión de Visual Studio para poder modificar su instalación.</span><span class="sxs-lookup"><span data-stu-id="d56d2-179">If you don't see a **Modify** button but you see an **Update** one instead, you need to update your Visual Studio before you can modify your installation.</span></span>
   > <span data-ttu-id="d56d2-180">Cuando haya finalizado la actualización, aparecerá el botón **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="d56d2-180">After the update is finished, the **Modify** button should appear.</span></span>

1. <span data-ttu-id="d56d2-181">En la pestaña **Paquetes de idioma**, seleccione o anule la selección de los idiomas que quiera instalar o desinstalar.</span><span class="sxs-lookup"><span data-stu-id="d56d2-181">In the **Language packs** tab, select or deselect the languages you want to install or uninstall.</span></span>

   ![Pestaña Paquetes de idioma de Visual Studio](./media/localized-intellisense/vs-modify-language-packs.png)

1. <span data-ttu-id="d56d2-183">Elija **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="d56d2-183">Choose **Modify**.</span></span> <span data-ttu-id="d56d2-184">Se inicia la actualización.</span><span class="sxs-lookup"><span data-stu-id="d56d2-184">The update starts.</span></span>

### <a name="modify-language-settings-in-visual-studio"></a><span data-ttu-id="d56d2-185">Modificación de la configuración de idioma en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d56d2-185">Modify language settings in Visual Studio</span></span>

<span data-ttu-id="d56d2-186">Una vez que haya instalado los paquete de idioma deseados, modifique la configuración de Visual Studio para usar otro idioma:</span><span class="sxs-lookup"><span data-stu-id="d56d2-186">Once you've installed the desired language packs, modify your Visual Studio settings to use a different language:</span></span>

1. <span data-ttu-id="d56d2-187">Abra Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d56d2-187">Open Visual Studio.</span></span>

1. <span data-ttu-id="d56d2-188">En la ventana de inicio, elija **Continuar sin código**.</span><span class="sxs-lookup"><span data-stu-id="d56d2-188">On the start window, choose **Continue without code**.</span></span>

1. <span data-ttu-id="d56d2-189">En la barra de menús, seleccione **Herramientas** > **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="d56d2-189">On the menu bar, select **Tools** > **Options**.</span></span> <span data-ttu-id="d56d2-190">Se abrirá el cuadro de diálogo Opciones.</span><span class="sxs-lookup"><span data-stu-id="d56d2-190">The Options dialog opens.</span></span>

1. <span data-ttu-id="d56d2-191">En el nodo **Entorno**, seleccione **Configuración internacional**.</span><span class="sxs-lookup"><span data-stu-id="d56d2-191">Under the **Environment** node, choose **International Settings**.</span></span>

1. <span data-ttu-id="d56d2-192">En la lista desplegable **Idioma**, seleccione el que quiera usar.</span><span class="sxs-lookup"><span data-stu-id="d56d2-192">On the **Language** drop-down, select the desired language.</span></span> <span data-ttu-id="d56d2-193">Elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d56d2-193">Choose **OK**.</span></span>

1. <span data-ttu-id="d56d2-194">Aparecerá un cuadro de diálogo en el que se le informará de que debe reiniciar Visual Studio para que se apliquen los cambios.</span><span class="sxs-lookup"><span data-stu-id="d56d2-194">A dialog informs you that you have to restart Visual Studio for the changes to take effect.</span></span> <span data-ttu-id="d56d2-195">Elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d56d2-195">Choose **OK**.</span></span>

1. <span data-ttu-id="d56d2-196">Reinicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d56d2-196">Restart Visual Studio.</span></span>

<span data-ttu-id="d56d2-197">Después de esto, IntelliSense deberá funcionar según lo esperado al abrir un proyecto de .NET Core que tenga como destino la versión de los archivos de IntelliSense que acaba de instalar.</span><span class="sxs-lookup"><span data-stu-id="d56d2-197">After this, your IntelliSense should work as expected when you open a .NET Core project that targets the version of the IntelliSense files you just installed.</span></span>

## <a name="see-also"></a><span data-ttu-id="d56d2-198">Vea también</span><span class="sxs-lookup"><span data-stu-id="d56d2-198">See also</span></span>

- [<span data-ttu-id="d56d2-199">IntelliSense en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d56d2-199">IntelliSense in Visual Studio</span></span>](/visualstudio/ide/using-intellisense)

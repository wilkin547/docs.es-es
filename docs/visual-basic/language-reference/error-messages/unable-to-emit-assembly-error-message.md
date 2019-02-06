---
title: 'No se puede emitir el ensamblado: <error message>'
ms.date: 08/14/2018
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
ms.openlocfilehash: d564f4f4462a691504297d65575956c5f06691ca
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2019
ms.locfileid: "55759228"
---
# <a name="unable-to-emit-assembly-error-message"></a><span data-ttu-id="f8ea1-102">No se puede emitir el ensamblado: \<mensaje de error ></span><span class="sxs-lookup"><span data-stu-id="f8ea1-102">Unable to emit assembly: \<error message></span></span>

<span data-ttu-id="f8ea1-103">El compilador de Visual Basic llama a Assembly Linker (*Al.exe*, también conocido como Alink) generar un ensamblado con un manifiesto y el vinculador informa de un error en la fase de emisión de creación del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f8ea1-103">The Visual Basic compiler calls the Assembly Linker (*Al.exe*, also known as Alink) to generate an assembly with a manifest, and the linker reports an error in the emission stage of creating the assembly.</span></span>

<span data-ttu-id="f8ea1-104">**Identificador de error:** BC30145</span><span class="sxs-lookup"><span data-stu-id="f8ea1-104">**Error ID:** BC30145</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="f8ea1-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="f8ea1-105">To correct this error</span></span>

1. <span data-ttu-id="f8ea1-106">Examine el mensaje de error citado y consulte el tema [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) para obtener más información y consejos.</span><span class="sxs-lookup"><span data-stu-id="f8ea1-106">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) for further explanation and advice.</span></span>

2. <span data-ttu-id="f8ea1-107">Intente firmar el ensamblado manualmente, mediante la [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) o [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md).</span><span class="sxs-lookup"><span data-stu-id="f8ea1-107">Try signing the assembly manually, using either the [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) or the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md).</span></span>

3. <span data-ttu-id="f8ea1-108">Si el error persiste, reúna información sobre las circunstancias y notifíquelo a los Servicios de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f8ea1-108">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>

### <a name="to-sign-the-assembly-manually"></a><span data-ttu-id="f8ea1-109">Para firmar el ensamblado manualmente</span><span class="sxs-lookup"><span data-stu-id="f8ea1-109">To sign the assembly manually</span></span>

1. <span data-ttu-id="f8ea1-110">Utilice la [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)) para crear un archivo de par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="f8ea1-110">Use the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)) to create a public/private key pair file.</span></span>

   <span data-ttu-id="f8ea1-111">Este archivo tiene un *.snk* extensión.</span><span class="sxs-lookup"><span data-stu-id="f8ea1-111">This file has an *.snk* extension.</span></span>

2. <span data-ttu-id="f8ea1-112">Elimine la referencia COM que está provocando el error en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="f8ea1-112">Delete the COM reference that is generating the error from your project.</span></span>

3. <span data-ttu-id="f8ea1-113">Abra el [símbolo del sistema para desarrolladores de Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="f8ea1-113">Open the [Developer Command Prompt for Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).</span></span>

   <span data-ttu-id="f8ea1-114">En Windows 10, escriba **símbolo** en el cuadro de búsqueda en la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="f8ea1-114">In Windows 10, enter **Developer command prompt** into the search box on the task bar.</span></span> <span data-ttu-id="f8ea1-115">A continuación, seleccione **símbolo del sistema para desarrolladores para VS 2017** desde la lista de resultados.</span><span class="sxs-lookup"><span data-stu-id="f8ea1-115">Then, select **Developer Command Prompt for VS 2017** from the results list.</span></span>

4. <span data-ttu-id="f8ea1-116">Cambie el directorio al directorio donde desea colocar el contenedor de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f8ea1-116">Change the directory to the directory where you want to place your assembly wrapper.</span></span>

5. <span data-ttu-id="f8ea1-117">Escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="f8ea1-117">Enter the following command:</span></span>

    ```cmd
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>
    ```

   <span data-ttu-id="f8ea1-118">Es un ejemplo del comando real que podría escribir:</span><span class="sxs-lookup"><span data-stu-id="f8ea1-118">An example of the actual command you might enter is:</span></span>

    ```cmd
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"
    ```

   > [!TIP]
   > <span data-ttu-id="f8ea1-119">Si un archivo o ruta de acceso contiene espacios, utilice comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="f8ea1-119">Use double quotation marks if a path or file contains spaces.</span></span>

6. <span data-ttu-id="f8ea1-120">En Visual Studio, agregue una referencia de ensamblado .NET al archivo que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="f8ea1-120">In Visual Studio, add a .NET Assembly reference to the file you just created.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8ea1-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8ea1-121">See also</span></span>

- [<span data-ttu-id="f8ea1-122">Al.exe</span><span class="sxs-lookup"><span data-stu-id="f8ea1-122">Al.exe</span></span>](../../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="f8ea1-123">Sn.exe (Herramienta de nombre seguro)</span><span class="sxs-lookup"><span data-stu-id="f8ea1-123">Sn.exe (Strong Name Tool)</span></span>](../../../framework/tools/sn-exe-strong-name-tool.md)
- [<span data-ttu-id="f8ea1-124">Cómo: Creación de un par de claves privada y pública</span><span class="sxs-lookup"><span data-stu-id="f8ea1-124">How to: Create a Public-Private Key Pair</span></span>](../../../framework/app-domains/how-to-create-a-public-private-key-pair.md)
- [<span data-ttu-id="f8ea1-125">Hable con nosotros</span><span class="sxs-lookup"><span data-stu-id="f8ea1-125">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
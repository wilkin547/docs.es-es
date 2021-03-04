---
description: 'Más información acerca de: BC30145: no se puede emitir el ensamblado: <error message>'
title: 'No se puede emitir el ensamblado: <error message>'
ms.date: 08/14/2018
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
ms.openlocfilehash: 393571f5b1fab518f379bbd6f4e6f1cb62a74b26
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102104788"
---
# <a name="bc30145-unable-to-emit-assembly-error-message"></a><span data-ttu-id="71138-103">BC30145: no se puede emitir el ensamblado: \<error message></span><span class="sxs-lookup"><span data-stu-id="71138-103">BC30145: Unable to emit assembly: \<error message></span></span>

<span data-ttu-id="71138-104">El compilador Visual Basic llama a Assembly Linker (*Al.exe*, también conocido como ALink) para generar un ensamblado con un manifiesto, y el vinculador informa de un error en la fase de emisión de la creación del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="71138-104">The Visual Basic compiler calls the Assembly Linker (*Al.exe*, also known as Alink) to generate an assembly with a manifest, and the linker reports an error in the emission stage of creating the assembly.</span></span>

<span data-ttu-id="71138-105">**Identificador de error:** BC30145</span><span class="sxs-lookup"><span data-stu-id="71138-105">**Error ID:** BC30145</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="71138-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="71138-106">To correct this error</span></span>

1. <span data-ttu-id="71138-107">Examine el mensaje de error citado y consulte el tema [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) para obtener una explicación más detallada y consejos.</span><span class="sxs-lookup"><span data-stu-id="71138-107">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) for further explanation and advice.</span></span>

2. <span data-ttu-id="71138-108">Intente firmar el ensamblado manualmente, mediante el [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) o el [Sn.exe (herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md).</span><span class="sxs-lookup"><span data-stu-id="71138-108">Try signing the assembly manually, using either the [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) or the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md).</span></span>

3. <span data-ttu-id="71138-109">Si el error persiste, reúna información sobre las circunstancias y notifíquelo a los Servicios de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="71138-109">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>

### <a name="to-sign-the-assembly-manually"></a><span data-ttu-id="71138-110">Para firmar el ensamblado manualmente</span><span class="sxs-lookup"><span data-stu-id="71138-110">To sign the assembly manually</span></span>

1. <span data-ttu-id="71138-111">Use el [Sn.exe (herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md)) para crear un archivo de par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="71138-111">Use the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)) to create a public/private key pair file.</span></span>

   <span data-ttu-id="71138-112">Este archivo tiene la extensión *. snk* .</span><span class="sxs-lookup"><span data-stu-id="71138-112">This file has an *.snk* extension.</span></span>

2. <span data-ttu-id="71138-113">Elimine la referencia COM que está provocando el error en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="71138-113">Delete the COM reference that is generating the error from your project.</span></span>

3. <span data-ttu-id="71138-114">Abra el [símbolo del sistema para desarrolladores para Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="71138-114">Open the [Developer Command Prompt for Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).</span></span>

4. <span data-ttu-id="71138-115">Cambie el directorio al directorio en el que desea colocar el contenedor de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="71138-115">Change the directory to the directory where you want to place your assembly wrapper.</span></span>

5. <span data-ttu-id="71138-116">Escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="71138-116">Enter the following command:</span></span>

    ```cmd
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>
    ```

   <span data-ttu-id="71138-117">Un ejemplo del comando real que puede escribir es:</span><span class="sxs-lookup"><span data-stu-id="71138-117">An example of the actual command you might enter is:</span></span>

    ```cmd
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"
    ```

   > [!TIP]
   > <span data-ttu-id="71138-118">Utilice comillas dobles si una ruta de acceso o archivo contiene espacios.</span><span class="sxs-lookup"><span data-stu-id="71138-118">Use double quotation marks if a path or file contains spaces.</span></span>

6. <span data-ttu-id="71138-119">En Visual Studio, agregue una referencia de ensamblado .NET al archivo que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="71138-119">In Visual Studio, add a .NET Assembly reference to the file you just created.</span></span>

## <a name="see-also"></a><span data-ttu-id="71138-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="71138-120">See also</span></span>

- [<span data-ttu-id="71138-121">Al.exe</span><span class="sxs-lookup"><span data-stu-id="71138-121">Al.exe</span></span>](../../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="71138-122">Sn.exe (Herramienta de nombre seguro)</span><span class="sxs-lookup"><span data-stu-id="71138-122">Sn.exe (Strong Name Tool)</span></span>](../../../framework/tools/sn-exe-strong-name-tool.md)
- [<span data-ttu-id="71138-123">Cómo: Creación de un par de claves privada y pública</span><span class="sxs-lookup"><span data-stu-id="71138-123">How to: Create a Public-Private Key Pair</span></span>](../../../standard/assembly/create-public-private-key-pair.md)
- [<span data-ttu-id="71138-124">Opciones de comentarios de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="71138-124">Visual Studio feedback options</span></span>](/visualstudio/ide/feedback-options)

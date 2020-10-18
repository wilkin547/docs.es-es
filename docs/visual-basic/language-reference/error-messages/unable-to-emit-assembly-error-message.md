---
title: 'No se puede emitir el ensamblado: <error message>'
ms.date: 08/14/2018
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
ms.openlocfilehash: c088f273c100b1a7eefcf74047865093f378e970
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161665"
---
# <a name="bc30145-unable-to-emit-assembly-error-message"></a><span data-ttu-id="2b28f-102">BC30145: no se puede emitir el ensamblado: \<error message></span><span class="sxs-lookup"><span data-stu-id="2b28f-102">BC30145: Unable to emit assembly: \<error message></span></span>

<span data-ttu-id="2b28f-103">El compilador Visual Basic llama a Assembly Linker (*Al.exe*, también conocido como ALink) para generar un ensamblado con un manifiesto, y el vinculador informa de un error en la fase de emisión de la creación del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2b28f-103">The Visual Basic compiler calls the Assembly Linker (*Al.exe*, also known as Alink) to generate an assembly with a manifest, and the linker reports an error in the emission stage of creating the assembly.</span></span>

<span data-ttu-id="2b28f-104">**Identificador de error:** BC30145</span><span class="sxs-lookup"><span data-stu-id="2b28f-104">**Error ID:** BC30145</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="2b28f-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="2b28f-105">To correct this error</span></span>

1. <span data-ttu-id="2b28f-106">Examine el mensaje de error citado y consulte el tema [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) para obtener una explicación más detallada y consejos.</span><span class="sxs-lookup"><span data-stu-id="2b28f-106">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) for further explanation and advice.</span></span>

2. <span data-ttu-id="2b28f-107">Intente firmar el ensamblado manualmente, mediante el [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) o el [Sn.exe (herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md).</span><span class="sxs-lookup"><span data-stu-id="2b28f-107">Try signing the assembly manually, using either the [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) or the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md).</span></span>

3. <span data-ttu-id="2b28f-108">Si el error persiste, reúna información sobre las circunstancias y notifíquelo a los Servicios de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2b28f-108">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>

### <a name="to-sign-the-assembly-manually"></a><span data-ttu-id="2b28f-109">Para firmar el ensamblado manualmente</span><span class="sxs-lookup"><span data-stu-id="2b28f-109">To sign the assembly manually</span></span>

1. <span data-ttu-id="2b28f-110">Use el [Sn.exe (herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md)) para crear un archivo de par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="2b28f-110">Use the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)) to create a public/private key pair file.</span></span>

   <span data-ttu-id="2b28f-111">Este archivo tiene la extensión *. snk* .</span><span class="sxs-lookup"><span data-stu-id="2b28f-111">This file has an *.snk* extension.</span></span>

2. <span data-ttu-id="2b28f-112">Elimine la referencia COM que está provocando el error en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="2b28f-112">Delete the COM reference that is generating the error from your project.</span></span>

3. <span data-ttu-id="2b28f-113">Abra el [símbolo del sistema para desarrolladores para Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="2b28f-113">Open the [Developer Command Prompt for Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).</span></span>

   <span data-ttu-id="2b28f-114">En Windows 10, escriba **símbolo del sistema para desarrolladores** en el cuadro de búsqueda de la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="2b28f-114">In Windows 10, enter **Developer command prompt** into the search box on the task bar.</span></span> <span data-ttu-id="2b28f-115">A continuación, seleccione **símbolo del sistema para desarrolladores para VS 2017** en la lista de resultados.</span><span class="sxs-lookup"><span data-stu-id="2b28f-115">Then, select **Developer Command Prompt for VS 2017** from the results list.</span></span>

4. <span data-ttu-id="2b28f-116">Cambie el directorio al directorio en el que desea colocar el contenedor de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2b28f-116">Change the directory to the directory where you want to place your assembly wrapper.</span></span>

5. <span data-ttu-id="2b28f-117">Escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="2b28f-117">Enter the following command:</span></span>

    ```cmd
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>
    ```

   <span data-ttu-id="2b28f-118">Un ejemplo del comando real que puede escribir es:</span><span class="sxs-lookup"><span data-stu-id="2b28f-118">An example of the actual command you might enter is:</span></span>

    ```cmd
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"
    ```

   > [!TIP]
   > <span data-ttu-id="2b28f-119">Utilice comillas dobles si una ruta de acceso o archivo contiene espacios.</span><span class="sxs-lookup"><span data-stu-id="2b28f-119">Use double quotation marks if a path or file contains spaces.</span></span>

6. <span data-ttu-id="2b28f-120">En Visual Studio, agregue una referencia de ensamblado .NET al archivo que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="2b28f-120">In Visual Studio, add a .NET Assembly reference to the file you just created.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b28f-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b28f-121">See also</span></span>

- [<span data-ttu-id="2b28f-122">Al.exe</span><span class="sxs-lookup"><span data-stu-id="2b28f-122">Al.exe</span></span>](../../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="2b28f-123">Sn.exe (Herramienta de nombre seguro)</span><span class="sxs-lookup"><span data-stu-id="2b28f-123">Sn.exe (Strong Name Tool)</span></span>](../../../framework/tools/sn-exe-strong-name-tool.md)
- [<span data-ttu-id="2b28f-124">Cómo: Creación de un par de claves privada y pública</span><span class="sxs-lookup"><span data-stu-id="2b28f-124">How to: Create a Public-Private Key Pair</span></span>](../../../standard/assembly/create-public-private-key-pair.md)
- [<span data-ttu-id="2b28f-125">Hable con nosotros</span><span class="sxs-lookup"><span data-stu-id="2b28f-125">Talk to Us</span></span>](/visualstudio/ide/feedback-options)

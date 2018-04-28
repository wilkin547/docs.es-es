---
title: 'No se puede emitir el ensamblado: &lt;mensaje de error&gt;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 59288ba7b4cec34cd2266d66aa931e92598e819a
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="unable-to-emit-assembly-lterror-messagegt"></a><span data-ttu-id="2a80f-102">No se puede emitir el ensamblado: &lt;mensaje de error&gt;</span><span class="sxs-lookup"><span data-stu-id="2a80f-102">Unable to emit assembly: &lt;error message&gt;</span></span>
<span data-ttu-id="2a80f-103">El compilador de Visual Basic llama a Assembly Linker (Al.exe, también denominado Alink) para generar un ensamblado con un manifiesto y el vinculador informa de un error en la fase de emisión de creación del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2a80f-103">The Visual Basic compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest, with the linker reporting an error in the emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="2a80f-104">**Id. de error:** BC30145</span><span class="sxs-lookup"><span data-stu-id="2a80f-104">**Error ID:** BC30145</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2a80f-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="2a80f-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="2a80f-106">Examine el mensaje de error citado y consulte el tema [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="2a80f-106">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span></span> <span data-ttu-id="2a80f-107">Para obtener una explicación y consejos.</span><span class="sxs-lookup"><span data-stu-id="2a80f-107">for further explanation and advice.</span></span>  
  
2.  <span data-ttu-id="2a80f-108">Intente firmar el ensamblado manualmente, mediante la [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) o [Sn.exe (herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md).</span><span class="sxs-lookup"><span data-stu-id="2a80f-108">Try signing the assembly manually, using either the [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) or the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md).</span></span>  
  
3.  <span data-ttu-id="2a80f-109">Si el error persiste, reúna información sobre las circunstancias y notifíquelo a los Servicios de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2a80f-109">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
### <a name="to-sign-the-assembly-manually"></a><span data-ttu-id="2a80f-110">Para firmar el ensamblado manualmente</span><span class="sxs-lookup"><span data-stu-id="2a80f-110">To sign the assembly manually</span></span>  
  
1.  <span data-ttu-id="2a80f-111">Use el [Sn.exe (herramienta de nombre seguro)][Sn.exe (herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md)) para crear un archivo de par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="2a80f-111">Use the [Sn.exe (Strong Name Tool)][Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)) to create a public/private key pair file.</span></span>  
  
     <span data-ttu-id="2a80f-112">Este archivo tiene la extensión .snk.</span><span class="sxs-lookup"><span data-stu-id="2a80f-112">This file has a .snk extension.</span></span>  
  
2.  <span data-ttu-id="2a80f-113">Elimine la referencia COM que está provocando el error en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="2a80f-113">Delete the COM reference that is generating the error from your project.</span></span>  
  
3.  <span data-ttu-id="2a80f-114">Desde las ventanas **iniciar** menú, elija **programas**, seleccione **Microsoft Visual Studio 2008**, seleccione **Visual Studio Tools**, y a continuación, haga clic en **símbolo del sistema de Visual Studio 2008**.</span><span class="sxs-lookup"><span data-stu-id="2a80f-114">From the Windows **Start** menu, point to **Programs**, point to **Microsoft Visual Studio 2008**, point to **Visual Studio Tools**, and then click **Visual Studio 2008 Command Prompt**.</span></span>  
  
4.  <span data-ttu-id="2a80f-115">Vaya al directorio en el que quiera colocar el contenedor de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2a80f-115">Move to the directory where you want to place your assembly wrapper.</span></span>  
  
5.  <span data-ttu-id="2a80f-116">Escriba el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="2a80f-116">Type the following code.</span></span>  
  
    ```  
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>  
    ```  
  
     <span data-ttu-id="2a80f-117">A continuación mostramos un ejemplo del código que se podría especificar.</span><span class="sxs-lookup"><span data-stu-id="2a80f-117">An example of the code you might enter would be the following.</span></span>  
  
    ```  
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"  
    ```  
  
     <span data-ttu-id="2a80f-118">Incluya comillas dobles (") si especifica una ruta de acceso o archivo que contiene espacios.</span><span class="sxs-lookup"><span data-stu-id="2a80f-118">Use double quotation marks (") if a path or file contains spaces.</span></span>  
  
6.  <span data-ttu-id="2a80f-119">En Visual Studio, agregue una referencia de ensamblado .NET al archivo que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="2a80f-119">In Visual Studio, add a .NET Assembly reference to the file you just created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a80f-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a80f-120">See Also</span></span>  
 
 <span data-ttu-id="2a80f-121">[Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="2a80f-121">[Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span></span>  
 <span data-ttu-id="2a80f-122">[Sn.exe (herramienta de nombre seguro)] [Sn.exe (herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md))</span><span class="sxs-lookup"><span data-stu-id="2a80f-122">[Sn.exe (Strong Name Tool)][Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>  
 [<span data-ttu-id="2a80f-123">Cómo: Crear un par de claves pública y privada</span><span class="sxs-lookup"><span data-stu-id="2a80f-123">How to: Create a Public-Private Key Pair</span></span>](../../../framework/app-domains/how-to-create-a-public-private-key-pair.md)  
 [<span data-ttu-id="2a80f-124">Hable con nosotros</span><span class="sxs-lookup"><span data-stu-id="2a80f-124">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)

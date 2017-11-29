---
title: 'No se puede emitir el ensamblado: &lt;mensaje de error&gt;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords: BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9dcf3d4bec379faa5783ca17847b91f9739df598
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="unable-to-emit-assembly-lterror-messagegt"></a><span data-ttu-id="1b58c-102">No se puede emitir el ensamblado: &lt;mensaje de error&gt;</span><span class="sxs-lookup"><span data-stu-id="1b58c-102">Unable to emit assembly: &lt;error message&gt;</span></span>
<span data-ttu-id="1b58c-103">El compilador de [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] llama a Assembly Linker (Al.exe, también denominado Alink) para generar un ensamblado con un manifiesto; el vinculador informa de un error en la fase de emisión de la creación del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1b58c-103">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest, with the linker reporting an error in the emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="1b58c-104">**Id. de error:** BC30145</span><span class="sxs-lookup"><span data-stu-id="1b58c-104">**Error ID:** BC30145</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1b58c-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="1b58c-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="1b58c-106">Examine el mensaje de error citado y consulte el tema [Errores y advertencias de la herramienta Al.exe](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) para obtener una explicación más detallada y consejos.</span><span class="sxs-lookup"><span data-stu-id="1b58c-106">Examine the quoted error message and consult the topic [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) for further explanation and advice.</span></span>  
  
2.  <span data-ttu-id="1b58c-107">Intente firmar el ensamblado manualmente, mediante la [Al.exe (Assembly Linker)](https://msdn.microsoft.com/library/c405shex) o [Sn.exe (herramienta de nombre seguro)](https://msdn.microsoft.com/library/k5b5tt23).</span><span class="sxs-lookup"><span data-stu-id="1b58c-107">Try signing the assembly manually, using either the [Al.exe (Assembly Linker)](https://msdn.microsoft.com/library/c405shex) or the [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span></span>  
  
3.  <span data-ttu-id="1b58c-108">Si el error persiste, reúna información sobre las circunstancias y notifíquelo a los Servicios de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1b58c-108">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
### <a name="to-sign-the-assembly-manually"></a><span data-ttu-id="1b58c-109">Para firmar el ensamblado manualmente</span><span class="sxs-lookup"><span data-stu-id="1b58c-109">To sign the assembly manually</span></span>  
  
1.  <span data-ttu-id="1b58c-110">Use la [Sn.exe (herramienta de nombre seguro)](https://msdn.microsoft.com/library/k5b5tt23) para crear un archivo de par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="1b58c-110">Use the [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23) to create a public/private key pair file.</span></span>  
  
     <span data-ttu-id="1b58c-111">Este archivo tiene la extensión .snk.</span><span class="sxs-lookup"><span data-stu-id="1b58c-111">This file has a .snk extension.</span></span>  
  
2.  <span data-ttu-id="1b58c-112">Elimine la referencia COM que está provocando el error en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="1b58c-112">Delete the COM reference that is generating the error from your project.</span></span>  
  
3.  <span data-ttu-id="1b58c-113">Desde las ventanas **iniciar** menú, elija **programas**, seleccione **Microsoft Visual Studio 2008**, seleccione **Visual Studio Tools**, y a continuación, haga clic en **símbolo del sistema de Visual Studio 2008**.</span><span class="sxs-lookup"><span data-stu-id="1b58c-113">From the Windows **Start** menu, point to **Programs**, point to **Microsoft Visual Studio 2008**, point to **Visual Studio Tools**, and then click **Visual Studio 2008 Command Prompt**.</span></span>  
  
4.  <span data-ttu-id="1b58c-114">Vaya al directorio en el que quiera colocar el contenedor de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1b58c-114">Move to the directory where you want to place your assembly wrapper.</span></span>  
  
5.  <span data-ttu-id="1b58c-115">Escriba el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="1b58c-115">Type the following code.</span></span>  
  
    ```  
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>  
    ```  
  
     <span data-ttu-id="1b58c-116">A continuación mostramos un ejemplo del código que se podría especificar.</span><span class="sxs-lookup"><span data-stu-id="1b58c-116">An example of the code you might enter would be the following.</span></span>  
  
    ```  
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"  
    ```  
  
     <span data-ttu-id="1b58c-117">Incluya comillas dobles (") si especifica una ruta de acceso o archivo que contiene espacios.</span><span class="sxs-lookup"><span data-stu-id="1b58c-117">Use double quotation marks (") if a path or file contains spaces.</span></span>  
  
6.  <span data-ttu-id="1b58c-118">En [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], agregue una referencia de ensamblado de .NET al archivo que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="1b58c-118">In [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], add a .NET Assembly reference to the file you just created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b58c-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b58c-119">See Also</span></span>  
 [<span data-ttu-id="1b58c-120">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="1b58c-120">Al.exe (Assembly Linker)</span></span>](https://msdn.microsoft.com/library/c405shex)  
 [<span data-ttu-id="1b58c-121">Las advertencias y errores de la herramienta Al.exe</span><span class="sxs-lookup"><span data-stu-id="1b58c-121">Al.exe Tool Errors and Warnings</span></span>](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)  
 [<span data-ttu-id="1b58c-122">Sn.exe (Herramienta de nombre seguro)</span><span class="sxs-lookup"><span data-stu-id="1b58c-122">Sn.exe (Strong Name Tool)</span></span>](https://msdn.microsoft.com/library/k5b5tt23)  
 <span data-ttu-id="1b58c-123">[How to: Create a Public-Private Key Pair](http://msdn.microsoft.com/library/05026813-f3bd-4d7c-9e0b-fc588eb3d114) (Cómo: Crear un par de claves pública y privada)</span><span class="sxs-lookup"><span data-stu-id="1b58c-123">[How to: Create a Public-Private Key Pair](http://msdn.microsoft.com/library/05026813-f3bd-4d7c-9e0b-fc588eb3d114)</span></span>  
 [<span data-ttu-id="1b58c-124">Hable con nosotros</span><span class="sxs-lookup"><span data-stu-id="1b58c-124">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)

---
title: 'Error al crear el manifiesto del ensamblado: &lt;mensaje de error&gt;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords: BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5e88d28ef787eb57b71d94f4ee51c09e9751dbff
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="error-creating-assembly-manifest-lterror-messagegt"></a><span data-ttu-id="83ff5-102">Error al crear el manifiesto del ensamblado: &lt;mensaje de error&gt;</span><span class="sxs-lookup"><span data-stu-id="83ff5-102">Error creating assembly manifest: &lt;error message&gt;</span></span>
<span data-ttu-id="83ff5-103">El compilador de [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] llama a Assembly Linker (Al.exe, también denominado Alink) para generar un ensamblado con un manifiesto.</span><span class="sxs-lookup"><span data-stu-id="83ff5-103">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest.</span></span> <span data-ttu-id="83ff5-104">El vinculador ha informado de un error en una fase previa a la emisión de la creación del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="83ff5-104">The linker has reported an error in the pre-emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="83ff5-105">Esto puede suceder si existen problemas con el archivo de clave o el contenedor de claves especificado.</span><span class="sxs-lookup"><span data-stu-id="83ff5-105">This can occur if there are problems with the key file or the key container specified.</span></span> <span data-ttu-id="83ff5-106">Para firmar completamente un ensamblado, debe proporcionar un archivo de clave válido que contenga información sobre las claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="83ff5-106">To fully sign an assembly, you must provide a valid key file that contains information about the public and private keys.</span></span> <span data-ttu-id="83ff5-107">Para retrasar la firma de un ensamblado, debe activar la casilla **Retrasar solo firma** y proporcionar un archivo de clave válido que contenga información sobre la clave pública.</span><span class="sxs-lookup"><span data-stu-id="83ff5-107">To delay sign an assembly, you must select the **Delay sign only** check box and provide a valid key file that contains information about the public key information.</span></span> <span data-ttu-id="83ff5-108">La clave privada no es necesaria cuando un ensamblado tiene la firma retrasada.</span><span class="sxs-lookup"><span data-stu-id="83ff5-108">The private key is not necessary when an assembly is delay-signed.</span></span> <span data-ttu-id="83ff5-109">Para obtener más información, vea [Cómo: Firmar un ensamblado con un nombre seguro](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="83ff5-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
 <span data-ttu-id="83ff5-110">**Id. de error:** BC30140</span><span class="sxs-lookup"><span data-stu-id="83ff5-110">**Error ID:** BC30140</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="83ff5-111">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="83ff5-111">To correct this error</span></span>  
  
1.  <span data-ttu-id="83ff5-112">Examine el mensaje de error citado y consulte el tema [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="83ff5-112">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span></span> <span data-ttu-id="83ff5-113">Para obtener consejos y obtener más información de error AL1019.</span><span class="sxs-lookup"><span data-stu-id="83ff5-113">for error AL1019 further explanation and advice</span></span>  
  
2.  <span data-ttu-id="83ff5-114">Si el error persiste, reúna información sobre las circunstancias y notifíquelo a los Servicios de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="83ff5-114">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83ff5-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="83ff5-115">See Also</span></span>  
 [<span data-ttu-id="83ff5-116">Cómo: Firmar un ensamblado con un nombre seguro</span><span class="sxs-lookup"><span data-stu-id="83ff5-116">How to: Sign an Assembly with a Strong Name</span></span>](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)  
 [<span data-ttu-id="83ff5-117">Página Firma, Diseñador de proyectos</span><span class="sxs-lookup"><span data-stu-id="83ff5-117">Signing Page, Project Designer</span></span>](/visualstudio/ide/reference/signing-page-project-designer)  
 <span data-ttu-id="83ff5-118">[Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="83ff5-118">[Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span></span>  
 [<span data-ttu-id="83ff5-119">Hable con nosotros</span><span class="sxs-lookup"><span data-stu-id="83ff5-119">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)

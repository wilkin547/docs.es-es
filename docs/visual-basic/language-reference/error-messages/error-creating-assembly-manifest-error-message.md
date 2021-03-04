---
description: 'Más información acerca de: BC30140: error al crear el manifiesto del ensamblado: <error message>'
title: 'Error al crear manifiesto del ensamblado: <error message>'
ms.date: 07/20/2015
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords:
- BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
ms.openlocfilehash: e2c690ab198e11a70a2fc3bba925ccc4ccb31c79
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102103418"
---
# <a name="bc30140-error-creating-assembly-manifest-error-message"></a><span data-ttu-id="14f43-103">BC30140: error al crear el manifiesto del ensamblado: \<error message></span><span class="sxs-lookup"><span data-stu-id="14f43-103">BC30140: Error creating assembly manifest: \<error message></span></span>

<span data-ttu-id="14f43-104">El compilador Visual Basic llama a Assembly Linker (Al.exe, también conocido como ALink) para generar un ensamblado con un manifiesto.</span><span class="sxs-lookup"><span data-stu-id="14f43-104">The Visual Basic compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest.</span></span> <span data-ttu-id="14f43-105">El vinculador ha informado de un error en una fase previa a la emisión de la creación del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="14f43-105">The linker has reported an error in the pre-emission stage of creating the assembly.</span></span>

 <span data-ttu-id="14f43-106">Esto puede suceder si existen problemas con el archivo de clave o el contenedor de claves especificado.</span><span class="sxs-lookup"><span data-stu-id="14f43-106">This can occur if there are problems with the key file or the key container specified.</span></span> <span data-ttu-id="14f43-107">Para firmar completamente un ensamblado, debe proporcionar un archivo de clave válido que contenga información sobre las claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="14f43-107">To fully sign an assembly, you must provide a valid key file that contains information about the public and private keys.</span></span> <span data-ttu-id="14f43-108">Para retrasar la firma de un ensamblado, debe activar la casilla **Retrasar solo firma** y proporcionar un archivo de clave válido que contenga información sobre la clave pública.</span><span class="sxs-lookup"><span data-stu-id="14f43-108">To delay sign an assembly, you must select the **Delay sign only** check box and provide a valid key file that contains information about the public key information.</span></span> <span data-ttu-id="14f43-109">La clave privada no es necesaria cuando un ensamblado tiene la firma retrasada.</span><span class="sxs-lookup"><span data-stu-id="14f43-109">The private key is not necessary when an assembly is delay-signed.</span></span> <span data-ttu-id="14f43-110">Para más información, vea: [Cómo: Firmar un ensamblado con un nombre seguro](../../../standard/assembly/sign-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="14f43-110">For more information, see [How to: Sign an Assembly with a Strong Name](../../../standard/assembly/sign-strong-name.md).</span></span>

 <span data-ttu-id="14f43-111">**Identificador de error:** BC30140</span><span class="sxs-lookup"><span data-stu-id="14f43-111">**Error ID:** BC30140</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="14f43-112">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="14f43-112">To correct this error</span></span>

1. <span data-ttu-id="14f43-113">Examine el mensaje de error citado y consulte el tema [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="14f43-113">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span></span> <span data-ttu-id="14f43-114">en el caso de error, explicación más detallada y consejos</span><span class="sxs-lookup"><span data-stu-id="14f43-114">for error AL1019 further explanation and advice</span></span>

2. <span data-ttu-id="14f43-115">Si el error persiste, reúna información sobre las circunstancias y notifíquelo a los Servicios de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="14f43-115">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="14f43-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="14f43-116">See also</span></span>

- [<span data-ttu-id="14f43-117">Cómo: Firma de un ensamblado con un nombre seguro</span><span class="sxs-lookup"><span data-stu-id="14f43-117">How to: Sign an Assembly with a Strong Name</span></span>](../../../standard/assembly/sign-strong-name.md)
- [<span data-ttu-id="14f43-118">Página Firma, Diseñador de proyectos</span><span class="sxs-lookup"><span data-stu-id="14f43-118">Signing Page, Project Designer</span></span>](/visualstudio/ide/reference/signing-page-project-designer)
- [<span data-ttu-id="14f43-119">Al.exe</span><span class="sxs-lookup"><span data-stu-id="14f43-119">Al.exe</span></span>](../../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="14f43-120">Opciones de comentarios de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="14f43-120">Visual Studio feedback options</span></span>](/visualstudio/ide/feedback-options)

---
description: "Más información acerca de: BC30971: <message> este error también podría deberse a la combinación de una referencia de archivo con una referencia de proyecto al ensamblado ' <assemblyname> '"
title: <message> Este error también puede ser debido a la combinación de una referencia de archivo con una referencia de proyecto al ensamblado "<assemblyname>"
ms.date: 07/20/2015
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
ms.openlocfilehash: 73b0e3623bdb5fd7b8ab2110d85436b3f415b4f9
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100470946"
---
# <a name="bc30971-message-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-assemblyname"></a><span data-ttu-id="c27ad-103">BC30971: \<message> este error también podría deberse a la combinación de una referencia de archivo con una referencia de proyecto al ensamblado ' \<assemblyname> '</span><span class="sxs-lookup"><span data-stu-id="c27ad-103">BC30971: \<message> This error could also be due to mixing a file reference with a project reference to assembly '\<assemblyname>'</span></span>

<span data-ttu-id="c27ad-104">\<message> Este error también podría deberse a la combinación de una referencia de archivo con una referencia de proyecto al ensamblado ' \<assemblyname> .</span><span class="sxs-lookup"><span data-stu-id="c27ad-104">\<message> This error could also be due to mixing a file reference with a project reference to assembly '\<assemblyname>.</span></span> <span data-ttu-id="c27ad-105">En este caso, intente reemplazar la referencia de archivo a ' \<assemblyfilename> ' en el proyecto ' \<projectname1> ' con una referencia de proyecto a ' \<projectname2> '.</span><span class="sxs-lookup"><span data-stu-id="c27ad-105">In this case, try replacing the file reference to '\<assemblyfilename>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>

 <span data-ttu-id="c27ad-106">El código del proyecto accede a un miembro de otro proyecto, pero la configuración de la solución no permite que el compilador de Visual Basic resuelva la referencia.</span><span class="sxs-lookup"><span data-stu-id="c27ad-106">Code in your project accesses a member of another project, but the configuration of your solution does not allow the Visual Basic compiler to resolve the reference.</span></span>

 <span data-ttu-id="c27ad-107">Para tener acceso a un tipo definido en otro ensamblado, el compilador Visual Basic debe tener una referencia a ese ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c27ad-107">To access a type defined in another assembly, the Visual Basic compiler must have a reference to that assembly.</span></span> <span data-ttu-id="c27ad-108">Debe ser una referencia única y no ambigua, que no produzca referencias circulares entre proyectos.</span><span class="sxs-lookup"><span data-stu-id="c27ad-108">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>

 <span data-ttu-id="c27ad-109">**Identificador de error:** BC30971</span><span class="sxs-lookup"><span data-stu-id="c27ad-109">**Error ID:** BC30971</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="c27ad-110">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="c27ad-110">To correct this error</span></span>

1. <span data-ttu-id="c27ad-111">Determine qué proyecto produce el mejor ensamblado para que el proyecto haga referencia a este.</span><span class="sxs-lookup"><span data-stu-id="c27ad-111">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="c27ad-112">Para tomar esta decisión, puede usar criterios como la facilidad de acceso a archivos y la frecuencia de las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="c27ad-112">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>

2. <span data-ttu-id="c27ad-113">En las propiedades del proyecto, agregue una referencia al proyecto que contiene el ensamblado que define el tipo que está usando.</span><span class="sxs-lookup"><span data-stu-id="c27ad-113">In your project properties, add a reference to the project that contains the assembly that defines the type you are using.</span></span>

## <a name="see-also"></a><span data-ttu-id="c27ad-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c27ad-114">See also</span></span>

- [<span data-ttu-id="c27ad-115">Administrar referencias en un proyecto</span><span class="sxs-lookup"><span data-stu-id="c27ad-115">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="c27ad-116">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="c27ad-116">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [<span data-ttu-id="c27ad-117">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="c27ad-117">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="c27ad-118">Solucionar problemas de referencias rotas</span><span class="sxs-lookup"><span data-stu-id="c27ad-118">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)

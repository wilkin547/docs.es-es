---
description: "Obtenga más información sobre: BC30969: referencia necesaria para el ensamblado ' <assemblyidentity> ' que contiene el tipo ' <typename> ', pero no se pudo encontrar una referencia adecuada debido a la ambigüedad entre los proyectos ' <projectname1> ' y '<projectname2>"
title: Es necesaria una referencia al ensamblado '<assemblyidentity>' que contenga el tipo '<typename>', pero no se encontró una referencia adecuada debido a la ambigüedad entre los proyectos '<projectname1>' y '<projectname2>'
ms.date: 07/20/2015
f1_keywords:
- bc30969
- vbc30969
helpviewer_keywords:
- BC30969
ms.assetid: 1b29dbc5-8268-45fe-bfc2-b2070a5c845c
ms.openlocfilehash: 945a6558ff9eea20a28bc27da27e495d0eddfb15
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792042"
---
# <a name="bc30969-reference-required-to-assembly-assemblyidentity-containing-type-typename-but-a-suitable-reference-could-not-be-found-due-to-ambiguity-between-projects-projectname1-and-projectname2"></a><span data-ttu-id="66d2a-103">BC30969: referencia necesaria para el ensamblado ' \<assemblyidentity> ' que contiene el tipo ' \<typename> ', pero no se pudo encontrar una referencia adecuada debido a la ambigüedad entre los proyectos ' \<projectname1> ' y ' \<projectname2> '</span><span class="sxs-lookup"><span data-stu-id="66d2a-103">BC30969: Reference required to assembly '\<assemblyidentity>' containing type '\<typename>', but a suitable reference could not be found due to ambiguity between projects '\<projectname1>' and '\<projectname2>'</span></span>

<span data-ttu-id="66d2a-104">Una expresión usa un tipo como, por ejemplo, una clase, estructura, interfaz, enumeración o delegado, que se define fuera del proyecto.</span><span class="sxs-lookup"><span data-stu-id="66d2a-104">An expression uses a type, such as a class, structure, interface, enumeration, or delegate, that is defined outside your project.</span></span> <span data-ttu-id="66d2a-105">Sin embargo, hay referencias de proyectos a más de un ensamblado que definen ese tipo.</span><span class="sxs-lookup"><span data-stu-id="66d2a-105">However, you have project references to more than one assembly defining that type.</span></span>

 <span data-ttu-id="66d2a-106">Los proyectos citados generan ensamblados con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="66d2a-106">The cited projects produce assemblies with the same name.</span></span> <span data-ttu-id="66d2a-107">Por lo tanto, el compilador no puede determinar qué ensamblado debe usar para el tipo al que se está accediendo.</span><span class="sxs-lookup"><span data-stu-id="66d2a-107">Therefore, the compiler cannot determine which assembly to use for the type you are accessing.</span></span>

 <span data-ttu-id="66d2a-108">Para tener acceso a un tipo definido en otro ensamblado, el compilador Visual Basic debe tener una referencia a ese ensamblado.</span><span class="sxs-lookup"><span data-stu-id="66d2a-108">To access a type defined in another assembly, the Visual Basic compiler must have a reference to that assembly.</span></span> <span data-ttu-id="66d2a-109">Debe ser una referencia única y no ambigua, que no produzca referencias circulares entre proyectos.</span><span class="sxs-lookup"><span data-stu-id="66d2a-109">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>

 <span data-ttu-id="66d2a-110">**Identificador de error:** BC30969</span><span class="sxs-lookup"><span data-stu-id="66d2a-110">**Error ID:** BC30969</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="66d2a-111">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="66d2a-111">To correct this error</span></span>

1. <span data-ttu-id="66d2a-112">Determine qué proyecto produce el mejor ensamblado para que el proyecto haga referencia a este.</span><span class="sxs-lookup"><span data-stu-id="66d2a-112">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="66d2a-113">Para tomar esta decisión, puede usar criterios como la facilidad de acceso a archivos y la frecuencia de las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="66d2a-113">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>

2. <span data-ttu-id="66d2a-114">En las propiedades del proyecto, agregue una referencia al archivo que contiene el ensamblado que define el tipo que está utilizando.</span><span class="sxs-lookup"><span data-stu-id="66d2a-114">In your project properties, add a reference to the file that contains the assembly that defines the type you are using.</span></span>

## <a name="see-also"></a><span data-ttu-id="66d2a-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="66d2a-115">See also</span></span>

- [<span data-ttu-id="66d2a-116">Administrar referencias en un proyecto</span><span class="sxs-lookup"><span data-stu-id="66d2a-116">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="66d2a-117">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="66d2a-117">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [<span data-ttu-id="66d2a-118">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="66d2a-118">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="66d2a-119">Solucionar problemas de referencias rotas</span><span class="sxs-lookup"><span data-stu-id="66d2a-119">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)

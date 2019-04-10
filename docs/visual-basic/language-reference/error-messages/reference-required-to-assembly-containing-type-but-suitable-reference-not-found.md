---
title: Es necesaria una referencia al ensamblado '<assemblyidentity>' que contenga el tipo '<typename>', pero no se encontró una referencia adecuada debido a la ambigüedad entre los proyectos '<projectname1>' y '<projectname2>'
ms.date: 07/20/2015
f1_keywords:
- bc30969
- vbc30969
helpviewer_keywords:
- BC30969
ms.assetid: 1b29dbc5-8268-45fe-bfc2-b2070a5c845c
ms.openlocfilehash: 9868598b32ae17ef5bfb5dd738f8a7541515f5ec
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59310676"
---
# <a name="reference-required-to-assembly-assemblyidentity-containing-type-typename-but-a-suitable-reference-could-not-be-found-due-to-ambiguity-between-projects-projectname1-and-projectname2"></a><span data-ttu-id="96498-102">Necesaria una referencia al ensamblado '\<assemblyidentity >' que contiene el tipo '\<typename >', pero no se encontró una referencia adecuada debido a la ambigüedad entre los proyectos\<projectname1 >' y '\< projectname2 >'</span><span class="sxs-lookup"><span data-stu-id="96498-102">Reference required to assembly '\<assemblyidentity>' containing type '\<typename>', but a suitable reference could not be found due to ambiguity between projects '\<projectname1>' and '\<projectname2>'</span></span>
<span data-ttu-id="96498-103">Una expresión usa un tipo como, por ejemplo, una clase, estructura, interfaz, enumeración o delegado, que se define fuera del proyecto.</span><span class="sxs-lookup"><span data-stu-id="96498-103">An expression uses a type, such as a class, structure, interface, enumeration, or delegate, that is defined outside your project.</span></span> <span data-ttu-id="96498-104">Sin embargo, hay referencias de proyectos a más de un ensamblado que definen ese tipo.</span><span class="sxs-lookup"><span data-stu-id="96498-104">However, you have project references to more than one assembly defining that type.</span></span>  
  
 <span data-ttu-id="96498-105">Los proyectos citados generan ensamblados con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="96498-105">The cited projects produce assemblies with the same name.</span></span> <span data-ttu-id="96498-106">Por lo tanto, el compilador no puede determinar qué ensamblado debe usar para el tipo al que se está accediendo.</span><span class="sxs-lookup"><span data-stu-id="96498-106">Therefore, the compiler cannot determine which assembly to use for the type you are accessing.</span></span>  
  
 <span data-ttu-id="96498-107">Para obtener acceso a un tipo definido en otro ensamblado, el compilador de Visual Basic debe tener una referencia a ese ensamblado.</span><span class="sxs-lookup"><span data-stu-id="96498-107">To access a type defined in another assembly, the Visual Basic compiler must have a reference to that assembly.</span></span> <span data-ttu-id="96498-108">Debe ser una referencia única y no ambigua, que no produzca referencias circulares entre proyectos.</span><span class="sxs-lookup"><span data-stu-id="96498-108">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="96498-109">**Identificador de error:** BC30969</span><span class="sxs-lookup"><span data-stu-id="96498-109">**Error ID:** BC30969</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="96498-110">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="96498-110">To correct this error</span></span>  
  
1. <span data-ttu-id="96498-111">Determine qué proyecto produce el mejor ensamblado para que el proyecto haga referencia a este.</span><span class="sxs-lookup"><span data-stu-id="96498-111">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="96498-112">Para tomar esta decisión, puede usar criterios como la facilidad de acceso a archivos y la frecuencia de las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="96498-112">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2. <span data-ttu-id="96498-113">En las propiedades del proyecto, agregue una referencia al archivo que contiene el ensamblado que define el tipo que está usando.</span><span class="sxs-lookup"><span data-stu-id="96498-113">In your project properties, add a reference to the file that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96498-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="96498-114">See also</span></span>

- [<span data-ttu-id="96498-115">Administrar referencias en un proyecto</span><span class="sxs-lookup"><span data-stu-id="96498-115">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="96498-116">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="96498-116">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [<span data-ttu-id="96498-117">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="96498-117">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="96498-118">Troubleshooting Broken References</span><span class="sxs-lookup"><span data-stu-id="96498-118">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)

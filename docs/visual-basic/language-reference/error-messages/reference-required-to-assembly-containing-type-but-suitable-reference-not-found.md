---
title: "Necesaria una referencia al ensamblado &#39; &lt;identidadensamblado&gt;&#39; contenedor tipo &#39;&lt; TypeName&gt;&#39; pero no se pudo encontrar una referencia adecuada debido a la ambigüedad entre proyectos &#39;&lt; projectname1&gt;&#39; y &#39;&lt; projectname2&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30969
- vbc30969
helpviewer_keywords: BC30969
ms.assetid: 1b29dbc5-8268-45fe-bfc2-b2070a5c845c
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 04a1b16a10d2a3945d1efbe3a2bd0850f1da39fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="reference-required-to-assembly-39ltassemblyidentitygt39-containing-type-39lttypenamegt39-but-a-suitable-reference-could-not-be-found-due-to-ambiguity-between-projects-39ltprojectname1gt39-and-39ltprojectname2gt39"></a><span data-ttu-id="1c450-102">Necesaria una referencia al ensamblado &#39; &lt;identidadensamblado&gt;&#39; contenedor tipo &#39;&lt; TypeName&gt;&#39; pero no se pudo encontrar una referencia adecuada debido a la ambigüedad entre proyectos &#39;&lt; projectname1&gt;&#39; y &#39;&lt; projectname2&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="1c450-102">Reference required to assembly &#39;&lt;assemblyidentity&gt;&#39; containing type &#39;&lt;typename&gt;&#39;, but a suitable reference could not be found due to ambiguity between projects &#39;&lt;projectname1&gt;&#39; and &#39;&lt;projectname2&gt;&#39;</span></span>
<span data-ttu-id="1c450-103">Una expresión usa un tipo como, por ejemplo, una clase, estructura, interfaz, enumeración o delegado, que se define fuera del proyecto.</span><span class="sxs-lookup"><span data-stu-id="1c450-103">An expression uses a type, such as a class, structure, interface, enumeration, or delegate, that is defined outside your project.</span></span> <span data-ttu-id="1c450-104">Sin embargo, hay referencias de proyectos a más de un ensamblado que definen ese tipo.</span><span class="sxs-lookup"><span data-stu-id="1c450-104">However, you have project references to more than one assembly defining that type.</span></span>  
  
 <span data-ttu-id="1c450-105">Los proyectos citados generan ensamblados con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="1c450-105">The cited projects produce assemblies with the same name.</span></span> <span data-ttu-id="1c450-106">Por lo tanto, el compilador no puede determinar qué ensamblado debe usar para el tipo al que se está accediendo.</span><span class="sxs-lookup"><span data-stu-id="1c450-106">Therefore, the compiler cannot determine which assembly to use for the type you are accessing.</span></span>  
  
 <span data-ttu-id="1c450-107">Para acceder a un tipo definido en otro ensamblado, el compilador de [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] debe tener una referencia a dicho ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1c450-107">To access a type defined in another assembly, the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler must have a reference to that assembly.</span></span> <span data-ttu-id="1c450-108">Debe ser una referencia única y no ambigua, que no produzca referencias circulares entre proyectos.</span><span class="sxs-lookup"><span data-stu-id="1c450-108">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="1c450-109">**Identificador de error:** BC30969</span><span class="sxs-lookup"><span data-stu-id="1c450-109">**Error ID:** BC30969</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1c450-110">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="1c450-110">To correct this error</span></span>  
  
1.  <span data-ttu-id="1c450-111">Determine qué proyecto produce el mejor ensamblado para que el proyecto haga referencia a este.</span><span class="sxs-lookup"><span data-stu-id="1c450-111">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="1c450-112">Para tomar esta decisión, puede usar criterios como la facilidad de acceso a archivos y la frecuencia de las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="1c450-112">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2.  <span data-ttu-id="1c450-113">En las propiedades del proyecto, agregue una referencia al archivo que contiene el ensamblado que define el tipo que está usando.</span><span class="sxs-lookup"><span data-stu-id="1c450-113">In your project properties, add a reference to the file that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c450-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c450-114">See Also</span></span>  
 [<span data-ttu-id="1c450-115">Administrar referencias en un proyecto</span><span class="sxs-lookup"><span data-stu-id="1c450-115">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)  
 [<span data-ttu-id="1c450-116">Referencias a elementos declarados</span><span class="sxs-lookup"><span data-stu-id="1c450-116">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="1c450-117">NO ESTÁ EN LA COMPILACIÓN: Cómo: agregar o quitar referencias mediante el cuadro de diálogo Agregar referencia</span><span class="sxs-lookup"><span data-stu-id="1c450-117">NIB How to: Add or Remove References By Using the Add Reference Dialog Box</span></span>](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)  
 [<span data-ttu-id="1c450-118">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="1c450-118">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 [<span data-ttu-id="1c450-119">Solucionar problemas de referencias rotas</span><span class="sxs-lookup"><span data-stu-id="1c450-119">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)

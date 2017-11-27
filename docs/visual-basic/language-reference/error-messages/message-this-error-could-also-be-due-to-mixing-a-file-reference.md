---
title: "&lt;mensaje&gt; este error también podría ser debido a la combinación de una referencia de archivo con una referencia de proyecto al ensamblado &#39;&lt; AssemblyName&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords: BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a30e5d5aca09e7b74e16dd05cdc0c5c361c1657d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltmessagegt-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-39ltassemblynamegt39"></a><span data-ttu-id="70364-102">&lt;mensaje&gt; este error también podría ser debido a la combinación de una referencia de archivo con una referencia de proyecto al ensamblado &#39;&lt; AssemblyName&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="70364-102">&lt;message&gt; This error could also be due to mixing a file reference with a project reference to assembly &#39;&lt;assemblyname&gt;&#39;</span></span>
<span data-ttu-id="70364-103">\<mensaje > Este error también podría ser debido a la combinación de una referencia de archivo con una referencia de proyecto al ensamblado '\<assemblyname >.</span><span class="sxs-lookup"><span data-stu-id="70364-103">\<message> This error could also be due to mixing a file reference with a project reference to assembly '\<assemblyname>.</span></span> <span data-ttu-id="70364-104">En este caso, intente reemplazar la referencia de archivo a '\<nombredearchivodeensamblado >' en el proyecto '\<projectname1 >' con una referencia de proyecto a '\<projectname2 >'.</span><span class="sxs-lookup"><span data-stu-id="70364-104">In this case, try replacing the file reference to '\<assemblyfilename>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="70364-105">El código del proyecto accede a un miembro de otro proyecto, pero la configuración de la solución no permite que el compilador de [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] resuelva la referencia.</span><span class="sxs-lookup"><span data-stu-id="70364-105">Code in your project accesses a member of another project, but the configuration of your solution does not allow the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler to resolve the reference.</span></span>  
  
 <span data-ttu-id="70364-106">Para acceder a un tipo definido en otro ensamblado, el compilador de [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] debe tener una referencia a dicho ensamblado.</span><span class="sxs-lookup"><span data-stu-id="70364-106">To access a type defined in another assembly, the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler must have a reference to that assembly.</span></span> <span data-ttu-id="70364-107">Debe ser una referencia única y no ambigua, que no produzca referencias circulares entre proyectos.</span><span class="sxs-lookup"><span data-stu-id="70364-107">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="70364-108">**Identificador de error:** BC30971</span><span class="sxs-lookup"><span data-stu-id="70364-108">**Error ID:** BC30971</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="70364-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="70364-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="70364-110">Determine qué proyecto produce el mejor ensamblado para que el proyecto haga referencia a este.</span><span class="sxs-lookup"><span data-stu-id="70364-110">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="70364-111">Para tomar esta decisión, puede usar criterios como la facilidad de acceso a archivos y la frecuencia de las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="70364-111">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2.  <span data-ttu-id="70364-112">En las propiedades del proyecto, agregue una referencia al proyecto que contiene el ensamblado que define el tipo que está usando.</span><span class="sxs-lookup"><span data-stu-id="70364-112">In your project properties, add a reference to the project that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70364-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="70364-113">See Also</span></span>  
 [<span data-ttu-id="70364-114">Administrar referencias en un proyecto</span><span class="sxs-lookup"><span data-stu-id="70364-114">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)  
 [<span data-ttu-id="70364-115">Referencias a elementos declarados</span><span class="sxs-lookup"><span data-stu-id="70364-115">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="70364-116">NO ESTÁ EN LA COMPILACIÓN: Cómo: agregar o quitar referencias mediante el cuadro de diálogo Agregar referencia</span><span class="sxs-lookup"><span data-stu-id="70364-116">NIB How to: Add or Remove References By Using the Add Reference Dialog Box</span></span>](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)  
 [<span data-ttu-id="70364-117">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="70364-117">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 [<span data-ttu-id="70364-118">Solucionar problemas de referencias rotas</span><span class="sxs-lookup"><span data-stu-id="70364-118">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)

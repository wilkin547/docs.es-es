---
title: '&lt;mensaje&gt; este error también podría ser debido a la combinación de una referencia de archivo con una referencia de proyecto al ensamblado &#39; &lt;assemblyname&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
ms.openlocfilehash: d4fb2a8985a21ecea5056b83d2766e8dc468180d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528997"
---
# <a name="ltmessagegt-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-39ltassemblynamegt39"></a><span data-ttu-id="fb459-102">&lt;mensaje&gt; este error también podría ser debido a la combinación de una referencia de archivo con una referencia de proyecto al ensamblado &#39; &lt;assemblyname&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="fb459-102">&lt;message&gt; This error could also be due to mixing a file reference with a project reference to assembly &#39;&lt;assemblyname&gt;&#39;</span></span>
<span data-ttu-id="fb459-103">\<mensaje > Este error también podría ser debido a la combinación de una referencia de archivo con una referencia de proyecto al ensamblado '\<assemblyname >.</span><span class="sxs-lookup"><span data-stu-id="fb459-103">\<message> This error could also be due to mixing a file reference with a project reference to assembly '\<assemblyname>.</span></span> <span data-ttu-id="fb459-104">En este caso, intente reemplazar la referencia de archivo a '\<nombredearchivodeensamblado >' en el proyecto '\<projectname1 >' con una referencia de proyecto a '\<projectname2 >'.</span><span class="sxs-lookup"><span data-stu-id="fb459-104">In this case, try replacing the file reference to '\<assemblyfilename>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="fb459-105">Código del proyecto accede a un miembro de otro proyecto, pero la configuración de la solución no admite el compilador de Visual Basic resolver la referencia.</span><span class="sxs-lookup"><span data-stu-id="fb459-105">Code in your project accesses a member of another project, but the configuration of your solution does not allow the Visual Basic compiler to resolve the reference.</span></span>  
  
 <span data-ttu-id="fb459-106">Para obtener acceso a un tipo definido en otro ensamblado, el compilador de Visual Basic debe tener una referencia a ese ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fb459-106">To access a type defined in another assembly, the Visual Basic compiler must have a reference to that assembly.</span></span> <span data-ttu-id="fb459-107">Debe ser una referencia única y no ambigua, que no produzca referencias circulares entre proyectos.</span><span class="sxs-lookup"><span data-stu-id="fb459-107">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="fb459-108">**Identificador de error:** BC30971</span><span class="sxs-lookup"><span data-stu-id="fb459-108">**Error ID:** BC30971</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fb459-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="fb459-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="fb459-110">Determine qué proyecto produce el mejor ensamblado para que el proyecto haga referencia a este.</span><span class="sxs-lookup"><span data-stu-id="fb459-110">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="fb459-111">Para tomar esta decisión, puede usar criterios como la facilidad de acceso a archivos y la frecuencia de las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="fb459-111">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2.  <span data-ttu-id="fb459-112">En las propiedades del proyecto, agregue una referencia al proyecto que contiene el ensamblado que define el tipo que está usando.</span><span class="sxs-lookup"><span data-stu-id="fb459-112">In your project properties, add a reference to the project that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb459-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb459-113">See also</span></span>
- [<span data-ttu-id="fb459-114">Administrar referencias en un proyecto</span><span class="sxs-lookup"><span data-stu-id="fb459-114">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="fb459-115">Referencias a elementos declarados</span><span class="sxs-lookup"><span data-stu-id="fb459-115">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [<span data-ttu-id="fb459-116">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="fb459-116">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="fb459-117">Solucionar problemas de referencias rotas</span><span class="sxs-lookup"><span data-stu-id="fb459-117">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)

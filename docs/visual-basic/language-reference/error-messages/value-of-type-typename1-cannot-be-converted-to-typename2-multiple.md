---
title: Valor de tipo &#39; &lt;typename1&gt; &#39; no se puede convertir a &#39; &lt;nombredetipo2&gt; &#39; (varias referencias de archivo)
ms.date: 07/20/2015
f1_keywords:
- vbc30961
- bc30961
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
ms.openlocfilehash: 41c18160be9b546f8b525376fa06bc0eca6c117a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603696"
---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39-multiple-file-references"></a><span data-ttu-id="94b56-102">Valor de tipo &#39; &lt;typename1&gt; &#39; no se puede convertir a &#39; &lt;nombredetipo2&gt; &#39; (varias referencias de archivo)</span><span class="sxs-lookup"><span data-stu-id="94b56-102">Value of type &#39;&lt;typename1&gt;&#39; cannot be converted to &#39;&lt;typename2&gt;&#39; (Multiple file references)</span></span>
<span data-ttu-id="94b56-103">Valor de tipo '\<NombreTipo1 >' no se puede convertir a '\<nombredetipo2 >'.</span><span class="sxs-lookup"><span data-stu-id="94b56-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="94b56-104">Discordancia de tipos puede deberse a la combinación de una referencia de archivo a '\<rutaaccesoarchivo1 >' en el proyecto '\<projectname1 >' con una referencia de archivo a '\<rutaaccesoarchivo2 >' en el proyecto '\<projectname2 >'.</span><span class="sxs-lookup"><span data-stu-id="94b56-104">Type mismatch could be due to mixing a file reference to '\<filepath1>' in project '\<projectname1>' with a file reference to '\<filepath2>' in project '\<projectname2>'.</span></span> <span data-ttu-id="94b56-105">Si ambos ensamblados son idénticos, intente reemplazar estas referencias para que ambas procedan de la misma ubicación.</span><span class="sxs-lookup"><span data-stu-id="94b56-105">If both assemblies are identical, try replacing these references so both references are from the same location.</span></span>  
  
 <span data-ttu-id="94b56-106">En una situación donde un proyecto hace más de una referencia de archivo a un ensamblado, el compilador no puede garantizar que se puede convertir un tipo a otro.</span><span class="sxs-lookup"><span data-stu-id="94b56-106">In a situation where a project makes more than one file reference to an assembly, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="94b56-107">Cada referencia de archivo especifica una ruta de acceso y nombre del archivo de salida de un proyecto (normalmente un archivo DLL).</span><span class="sxs-lookup"><span data-stu-id="94b56-107">Each file reference specifies a file path and name for the output file of a project (typically a DLL file).</span></span> <span data-ttu-id="94b56-108">El compilador no puede garantizar que los archivos de salida procedan del mismo origen, ni que representen la misma versión del mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="94b56-108">The compiler cannot guarantee that the output files come from the same source, or that they represent the same version of the same assembly.</span></span> <span data-ttu-id="94b56-109">Por lo tanto, no puede garantizar que los tipos de las distintas referencias son del mismo tipo, o incluso que uno puede convertirse a otro.</span><span class="sxs-lookup"><span data-stu-id="94b56-109">Therefore, it cannot guarantee that the types in the different references are the same type, or even that one can be converted to the other.</span></span>  
  
 <span data-ttu-id="94b56-110">Puede usar una referencia de archivo si sabe que los ensamblados de referencia tienen la misma identidad de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="94b56-110">You can use a single file reference if you know that the referenced assemblies have the same assembly identity.</span></span> <span data-ttu-id="94b56-111">La *identidad del ensamblado* incluye el nombre, la versión, la clave pública, si existe, y la referencia cultural del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="94b56-111">The *assembly identity* includes the assembly's name, version, public key if any, and culture.</span></span> <span data-ttu-id="94b56-112">Esta información identifica de forma exclusiva el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="94b56-112">This information uniquely identifies the assembly.</span></span>  
  
 <span data-ttu-id="94b56-113">**Id. de error:** BC30961</span><span class="sxs-lookup"><span data-stu-id="94b56-113">**Error ID:** BC30961</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="94b56-114">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="94b56-114">To correct this error</span></span>  
  
-   <span data-ttu-id="94b56-115">Si los ensamblados de referencia tienen la misma identidad de ensamblado, quite o reemplace una de las referencias de archivo para que hay solo una única referencia de archivo.</span><span class="sxs-lookup"><span data-stu-id="94b56-115">If the referenced assemblies have the same assembly identity, then remove or replace one of the file references so that there is only a single file reference.</span></span>  
  
-   <span data-ttu-id="94b56-116">Si los ensamblados de referencia no tienen la misma identidad de ensamblado, a continuación, cambie el código para que no intente convertir el tipo de uno a un tipo en otro.</span><span class="sxs-lookup"><span data-stu-id="94b56-116">If the referenced assemblies do not have the same assembly identity, then change your code so that it does not attempt to convert a type in one to a type in the other.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94b56-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="94b56-117">See Also</span></span>  
 [<span data-ttu-id="94b56-118">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="94b56-118">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="94b56-119">Administrar referencias en un proyecto</span><span class="sxs-lookup"><span data-stu-id="94b56-119">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)  
 

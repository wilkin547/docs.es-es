---
title: Un valor de tipo '<typename1>' no se puede convertir a '<typename2>' (varias referencias de archivo)
ms.date: 07/20/2015
f1_keywords:
- vbc30961
- bc30961
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
ms.openlocfilehash: 25008f05979638e050b74fc659fdc0a6d13b3c31
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406591"
---
# <a name="value-of-type-typename1-cannot-be-converted-to-typename2-multiple-file-references"></a><span data-ttu-id="bd68b-102">Un valor de tipo '\<typename1>' no se puede convertir a '\<typename2>' (varias referencias de archivo)</span><span class="sxs-lookup"><span data-stu-id="bd68b-102">Value of type '\<typename1>' cannot be converted to '\<typename2>' (Multiple file references)</span></span>
<span data-ttu-id="bd68b-103">El valor de tipo ' \<typename1> ' no se puede convertir en ' \<typename2> '.</span><span class="sxs-lookup"><span data-stu-id="bd68b-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="bd68b-104">La falta de coincidencia de tipos podría ser debido a la combinación de una referencia de archivo a ' \<filepath1> ' en el proyecto ' \<projectname1> ' con una referencia de archivo a ' \<filepath2> ' en el proyecto ' ' \<projectname2> .</span><span class="sxs-lookup"><span data-stu-id="bd68b-104">Type mismatch could be due to mixing a file reference to '\<filepath1>' in project '\<projectname1>' with a file reference to '\<filepath2>' in project '\<projectname2>'.</span></span> <span data-ttu-id="bd68b-105">Si ambos ensamblados son idénticos, intente reemplazar estas referencias para que ambas procedan de la misma ubicación.</span><span class="sxs-lookup"><span data-stu-id="bd68b-105">If both assemblies are identical, try replacing these references so both references are from the same location.</span></span>  
  
 <span data-ttu-id="bd68b-106">En una situación en la que un proyecto realiza más de una referencia de archivo a un ensamblado, el compilador no puede garantizar que un tipo se pueda convertir en otro.</span><span class="sxs-lookup"><span data-stu-id="bd68b-106">In a situation where a project makes more than one file reference to an assembly, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="bd68b-107">Cada referencia de archivo especifica una ruta de acceso y un nombre de archivo para el archivo de salida de un proyecto (normalmente un archivo DLL).</span><span class="sxs-lookup"><span data-stu-id="bd68b-107">Each file reference specifies a file path and name for the output file of a project (typically a DLL file).</span></span> <span data-ttu-id="bd68b-108">El compilador no puede garantizar que los archivos de salida proceden del mismo origen o que representan la misma versión del mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bd68b-108">The compiler cannot guarantee that the output files come from the same source, or that they represent the same version of the same assembly.</span></span> <span data-ttu-id="bd68b-109">Por lo tanto, no puede garantizar que los tipos de las distintas referencias son del mismo tipo, o incluso que se puede convertir en el otro.</span><span class="sxs-lookup"><span data-stu-id="bd68b-109">Therefore, it cannot guarantee that the types in the different references are the same type, or even that one can be converted to the other.</span></span>  
  
 <span data-ttu-id="bd68b-110">Puede usar una sola referencia de archivo si sabe que los ensamblados a los que se hace referencia tienen la misma identidad de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bd68b-110">You can use a single file reference if you know that the referenced assemblies have the same assembly identity.</span></span> <span data-ttu-id="bd68b-111">La *identidad del ensamblado* incluye el nombre, la versión, la clave pública, si existe, y la referencia cultural del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bd68b-111">The *assembly identity* includes the assembly's name, version, public key if any, and culture.</span></span> <span data-ttu-id="bd68b-112">Esta información identifica de forma exclusiva el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bd68b-112">This information uniquely identifies the assembly.</span></span>  
  
 <span data-ttu-id="bd68b-113">**Identificador de error:** BC30961</span><span class="sxs-lookup"><span data-stu-id="bd68b-113">**Error ID:** BC30961</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bd68b-114">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="bd68b-114">To correct this error</span></span>  
  
- <span data-ttu-id="bd68b-115">Si los ensamblados a los que se hace referencia tienen la misma identidad de ensamblado, quite o reemplace una de las referencias de archivo para que solo haya una referencia de archivo única.</span><span class="sxs-lookup"><span data-stu-id="bd68b-115">If the referenced assemblies have the same assembly identity, then remove or replace one of the file references so that there is only a single file reference.</span></span>  
  
- <span data-ttu-id="bd68b-116">Si los ensamblados a los que se hace referencia no tienen la misma identidad de ensamblado, cambie el código para que no intente convertir un tipo de uno en un tipo en el otro.</span><span class="sxs-lookup"><span data-stu-id="bd68b-116">If the referenced assemblies do not have the same assembly identity, then change your code so that it does not attempt to convert a type in one to a type in the other.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd68b-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bd68b-117">See also</span></span>

- [<span data-ttu-id="bd68b-118">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bd68b-118">Type Conversions in Visual Basic</span></span>](../../programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="bd68b-119">Administrar referencias en un proyecto</span><span class="sxs-lookup"><span data-stu-id="bd68b-119">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)

---
title: Un valor de tipo '<typename1>' no se puede convertir a '<typename2>' (varias referencias de archivo)
ms.date: 07/20/2015
f1_keywords:
- vbc30961
- bc30961
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
ms.openlocfilehash: 58b334eb5e6db443bcfaba72729d59cb1d798e70
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766823"
---
# <a name="value-of-type-typename1-cannot-be-converted-to-typename2-multiple-file-references"></a><span data-ttu-id="6b3d9-102">Valor de tipo '\<typename1 >' no se puede convertir a '\<nombredetipo2 >' (varias referencias de archivo)</span><span class="sxs-lookup"><span data-stu-id="6b3d9-102">Value of type '\<typename1>' cannot be converted to '\<typename2>' (Multiple file references)</span></span>
<span data-ttu-id="6b3d9-103">Valor de tipo '\<typename1 >' no se puede convertir a '\<nombredetipo2 >'.</span><span class="sxs-lookup"><span data-stu-id="6b3d9-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="6b3d9-104">Discordancia de tipos podría ser debido a la combinación de una referencia a '\<rutadeaccesodearchivo1 >' en el proyecto '\<projectname1 >' con una referencia a '\<rutadeaccesodearchivo2 >' en el proyecto '\<projectname2 >'.</span><span class="sxs-lookup"><span data-stu-id="6b3d9-104">Type mismatch could be due to mixing a file reference to '\<filepath1>' in project '\<projectname1>' with a file reference to '\<filepath2>' in project '\<projectname2>'.</span></span> <span data-ttu-id="6b3d9-105">Si ambos ensamblados son idénticos, intente reemplazar estas referencias para que ambas procedan de la misma ubicación.</span><span class="sxs-lookup"><span data-stu-id="6b3d9-105">If both assemblies are identical, try replacing these references so both references are from the same location.</span></span>  
  
 <span data-ttu-id="6b3d9-106">En una situación donde un proyecto realiza más de una referencia de archivo a un ensamblado, el compilador no puede garantizar que se puede convertir un tipo a otro.</span><span class="sxs-lookup"><span data-stu-id="6b3d9-106">In a situation where a project makes more than one file reference to an assembly, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="6b3d9-107">Cada referencia de archivo especifica una ruta de acceso y nombre del archivo de salida de un proyecto (normalmente un archivo DLL).</span><span class="sxs-lookup"><span data-stu-id="6b3d9-107">Each file reference specifies a file path and name for the output file of a project (typically a DLL file).</span></span> <span data-ttu-id="6b3d9-108">El compilador no puede garantizar que los archivos de salida procedan del mismo origen, o que representan la misma versión del mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6b3d9-108">The compiler cannot guarantee that the output files come from the same source, or that they represent the same version of the same assembly.</span></span> <span data-ttu-id="6b3d9-109">Por lo tanto, no puede garantizar que los tipos en las distintas referencias son del mismo tipo, o incluso que uno puede convertirse a otro.</span><span class="sxs-lookup"><span data-stu-id="6b3d9-109">Therefore, it cannot guarantee that the types in the different references are the same type, or even that one can be converted to the other.</span></span>  
  
 <span data-ttu-id="6b3d9-110">Puede usar una referencia de archivo si sabe que los ensamblados de referencia tienen la misma identidad de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6b3d9-110">You can use a single file reference if you know that the referenced assemblies have the same assembly identity.</span></span> <span data-ttu-id="6b3d9-111">La *identidad del ensamblado* incluye el nombre, la versión, la clave pública, si existe, y la referencia cultural del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6b3d9-111">The *assembly identity* includes the assembly's name, version, public key if any, and culture.</span></span> <span data-ttu-id="6b3d9-112">Esta información identifica de forma exclusiva el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6b3d9-112">This information uniquely identifies the assembly.</span></span>  
  
 <span data-ttu-id="6b3d9-113">**Identificador de error:** BC30961</span><span class="sxs-lookup"><span data-stu-id="6b3d9-113">**Error ID:** BC30961</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6b3d9-114">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="6b3d9-114">To correct this error</span></span>  
  
- <span data-ttu-id="6b3d9-115">Si los ensamblados de referencia tienen la misma identidad de ensamblado, quitar o reemplazar una de las referencias de archivo, por lo que hay solo una referencia de archivo.</span><span class="sxs-lookup"><span data-stu-id="6b3d9-115">If the referenced assemblies have the same assembly identity, then remove or replace one of the file references so that there is only a single file reference.</span></span>  
  
- <span data-ttu-id="6b3d9-116">Si los ensamblados de referencia no tienen la misma identidad de ensamblado, a continuación, cambie el código para que no intenta convertir a un tipo de una a un tipo en el otro.</span><span class="sxs-lookup"><span data-stu-id="6b3d9-116">If the referenced assemblies do not have the same assembly identity, then change your code so that it does not attempt to convert a type in one to a type in the other.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b3d9-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b3d9-117">See also</span></span>

- [<span data-ttu-id="6b3d9-118">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6b3d9-118">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="6b3d9-119">Administrar referencias en un proyecto</span><span class="sxs-lookup"><span data-stu-id="6b3d9-119">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)

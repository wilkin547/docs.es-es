---
title: Un valor de tipo '<typename1>' no se puede convertir a '<typename2>'
ms.date: 07/20/2015
f1_keywords:
- vbc30955
- bc30955
helpviewer_keywords:
- BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
ms.openlocfilehash: 67cb8ac602437474f35c89c9aecf66fbf40c91c9
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875040"
---
# <a name="value-of-type-typename1-cannot-be-converted-to-typename2"></a><span data-ttu-id="34982-102">Un valor de tipo '\<typename1>' no se puede convertir a '\<typename2>'</span><span class="sxs-lookup"><span data-stu-id="34982-102">Value of type '\<typename1>' cannot be converted to '\<typename2>'</span></span>

<span data-ttu-id="34982-103">El valor de tipo ' \<typename1> ' no se puede convertir en ' \<typename2> '.</span><span class="sxs-lookup"><span data-stu-id="34982-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="34982-104">La falta de coincidencia de tipos podría deberse a la combinación de una referencia de archivo con una referencia de proyecto al ensamblado ' \<assemblyname> '.</span><span class="sxs-lookup"><span data-stu-id="34982-104">Type mismatch could be due to the mixing of a file reference with a project reference to assembly '\<assemblyname>'.</span></span> <span data-ttu-id="34982-105">Intente reemplazar la referencia de archivo a ' \<filepath> ' en el proyecto ' \<projectname1> ' con una referencia de proyecto a ' \<projectname2> '.</span><span class="sxs-lookup"><span data-stu-id="34982-105">Try replacing the file reference to '\<filepath>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="34982-106">En una situación en la que un proyecto realiza una referencia de proyecto y una referencia de archivo, el compilador no puede garantizar que un tipo se pueda convertir en otro.</span><span class="sxs-lookup"><span data-stu-id="34982-106">In a situation where a project makes both a project reference and a file reference, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="34982-107">En el siguiente pseudocódigo se muestra una situación que puede generar este error.</span><span class="sxs-lookup"><span data-stu-id="34982-107">The following pseudo-code illustrates a situation that can generate this error.</span></span>  
  
 `' ================ Visual Basic project P1 ================`  
  
 `'        P1 makes a PROJECT REFERENCE to project P2`  
  
 `'        and a FILE REFERENCE to project P3.`  
  
 `Public commonObject As P3.commonClass`  
  
 `commonObject = P2.getCommonClass()`  
  
 `' ================ Visual Basic project P2 ================`  
  
 `'        P2 makes a PROJECT REFERENCE to project P3`  
  
 `Public Function getCommonClass() As P3.commonClass`  
  
 `Return New P3.commonClass`  
  
 `End Function`  
  
 `' ================ Visual Basic project P3 ================`  
  
 `Public Class commonClass`  
  
 `End Class`  
  
 <span data-ttu-id="34982-108">Project `P1` realiza una referencia de proyecto indirecta a través de Project `P2` a Project `P3` y también una referencia de archivo directo a `P3` .</span><span class="sxs-lookup"><span data-stu-id="34982-108">Project `P1` makes an indirect project reference through project `P2` to project `P3`, and also a direct file reference to `P3`.</span></span> <span data-ttu-id="34982-109">La declaración de `commonObject` utiliza la referencia de archivo a `P3` , mientras que la llamada a `P2.getCommonClass` usa la referencia de proyecto a `P3` .</span><span class="sxs-lookup"><span data-stu-id="34982-109">The declaration of `commonObject` uses the file reference to `P3`, while the call to `P2.getCommonClass` uses the project reference to `P3`.</span></span>  
  
 <span data-ttu-id="34982-110">El problema en esta situación es que la referencia de archivo especifica una ruta de acceso y un nombre de archivo para el archivo de salida de `P3` (normalmente p3.dll), mientras que las referencias del proyecto identifican el proyecto de origen ( `P3` ) por nombre de proyecto.</span><span class="sxs-lookup"><span data-stu-id="34982-110">The problem in this situation is that the file reference specifies a file path and name for the output file of `P3` (typically p3.dll), while the project references identify the source project (`P3`) by project name.</span></span> <span data-ttu-id="34982-111">Por este motivo, el compilador no puede garantizar que el tipo `P3.commonClass` proceda del mismo código fuente a través de las dos referencias diferentes.</span><span class="sxs-lookup"><span data-stu-id="34982-111">Because of this, the compiler cannot guarantee that the type `P3.commonClass` comes from the same source code through the two different references.</span></span>  
  
 <span data-ttu-id="34982-112">Esta situación suele producirse cuando se mezclan las referencias de proyecto y las referencias de archivo.</span><span class="sxs-lookup"><span data-stu-id="34982-112">This situation typically occurs when project references and file references are mixed.</span></span> <span data-ttu-id="34982-113">En la ilustración anterior, el problema no se produce si se `P1` realiza una referencia de proyecto directa a en `P3` lugar de una referencia de archivo.</span><span class="sxs-lookup"><span data-stu-id="34982-113">In the preceding illustration, the problem would not occur if `P1` made a direct project reference to `P3` instead of a file reference.</span></span>  
  
 <span data-ttu-id="34982-114">**Identificador de error:** BC30955</span><span class="sxs-lookup"><span data-stu-id="34982-114">**Error ID:** BC30955</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="34982-115">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="34982-115">To correct this error</span></span>  
  
- <span data-ttu-id="34982-116">Cambie la referencia de archivo a una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="34982-116">Change the file reference to a project reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34982-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="34982-117">See also</span></span>

- [<span data-ttu-id="34982-118">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="34982-118">Type Conversions in Visual Basic</span></span>](../../programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="34982-119">Administrar referencias en un proyecto</span><span class="sxs-lookup"><span data-stu-id="34982-119">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)

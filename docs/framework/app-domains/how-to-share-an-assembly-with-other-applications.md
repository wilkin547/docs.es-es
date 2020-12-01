---
title: Procedimiento para compartir un ensamblado con otras aplicaciones
description: Vea cómo compartir un ensamblado con otras aplicaciones en .NET. Los ensamblados pueden ser privados (el valor predeterminado) o compartidos. Para compartir un ensamblado, colóquelo en la GAC.
ms.date: 08/19/2019
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
ms.openlocfilehash: 1056f8b555713d5d67488537e6c06cc457c4d312
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242544"
---
# <a name="how-to-share-an-assembly-with-other-applications"></a><span data-ttu-id="7983c-105">Procedimiento para compartir un ensamblado con otras aplicaciones</span><span class="sxs-lookup"><span data-stu-id="7983c-105">How to: Share an assembly with other applications</span></span>

<span data-ttu-id="7983c-106">Los ensamblados pueden ser privados o compartidos: de forma predeterminada, la mayoría de los programas sencillos constan de un ensamblado privado porque no se diseñaron para ser usados por otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="7983c-106">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  

<span data-ttu-id="7983c-107">Para compartir un ensamblado con otras aplicaciones, debe colocarse en la [caché global de ensamblados](gac.md).</span><span class="sxs-lookup"><span data-stu-id="7983c-107">In order to share an assembly with other applications, it must be placed in the [global assembly cache (GAC)](gac.md).</span></span>  
  
<span data-ttu-id="7983c-108">Para compartir un ensamblado:</span><span class="sxs-lookup"><span data-stu-id="7983c-108">To share an assembly:</span></span>
  
1. <span data-ttu-id="7983c-109">Cree el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7983c-109">Create your assembly.</span></span> <span data-ttu-id="7983c-110">Para obtener más información, vea [Creación de ensamblados](../../standard/assembly/create.md).</span><span class="sxs-lookup"><span data-stu-id="7983c-110">For more information, see [Create assemblies](../../standard/assembly/create.md).</span></span>  
  
2. <span data-ttu-id="7983c-111">Asigne un nombre seguro al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7983c-111">Assign a strong name to your assembly.</span></span> <span data-ttu-id="7983c-112">Para obtener más información, vea [Cómo: Firmar un ensamblado con un nombre seguro](../../standard/assembly/sign-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="7983c-112">For more information, see [How to: Sign an assembly with a strong name](../../standard/assembly/sign-strong-name.md).</span></span>  
  
3. <span data-ttu-id="7983c-113">Asigne la información de versión al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7983c-113">Assign version information to your assembly.</span></span> <span data-ttu-id="7983c-114">Para obtener más información, vea [Versiones de los ensamblados](../../standard/assembly/versioning.md).</span><span class="sxs-lookup"><span data-stu-id="7983c-114">For more information, see [Assembly versioning](../../standard/assembly/versioning.md).</span></span>  
  
4. <span data-ttu-id="7983c-115">Agregue el ensamblado a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="7983c-115">Add your assembly to the global assembly cache.</span></span> <span data-ttu-id="7983c-116">Para obtener más información, vea [Cómo: Instalar un ensamblado en la caché global de ensamblados](install-assembly-into-gac.md).</span><span class="sxs-lookup"><span data-stu-id="7983c-116">For more information, see [How to: Install an assembly into the global assembly cache](install-assembly-into-gac.md).</span></span>  
  
5. <span data-ttu-id="7983c-117">Obtenga acceso a los tipos que contiene el ensamblado desde otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="7983c-117">Access the types contained in the assembly from other applications.</span></span> <span data-ttu-id="7983c-118">Para obtener más información, vea [Cómo: Hacer referencia a un ensamblado con nombre seguro](../../standard/assembly/reference-strong-named.md).</span><span class="sxs-lookup"><span data-stu-id="7983c-118">For more information, see [How to: Reference a strong-named assembly](../../standard/assembly/reference-strong-named.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7983c-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="7983c-119">See also</span></span>

- [<span data-ttu-id="7983c-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="7983c-120">C# programming guide</span></span>](../../../api/index.md)
- [<span data-ttu-id="7983c-121">Conceptos de programación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7983c-121">Programming concepts (Visual Basic)</span></span>](../../../api/index.md)
- [<span data-ttu-id="7983c-122">Programación con ensamblados</span><span class="sxs-lookup"><span data-stu-id="7983c-122">Program with assemblies</span></span>](../../standard/assembly/index.md)

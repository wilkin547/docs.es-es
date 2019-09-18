---
title: Procedimiento para compartir un ensamblado con otras aplicaciones
ms.date: 08/19/2019
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
ms.openlocfilehash: b1ef195458dd2de95eeb5e25089339e55d9e3fbb
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972886"
---
# <a name="how-to-share-an-assembly-with-other-applications"></a><span data-ttu-id="ab468-102">Procedimiento para compartir un ensamblado con otras aplicaciones</span><span class="sxs-lookup"><span data-stu-id="ab468-102">How to: Share an assembly with other applications</span></span>
<span data-ttu-id="ab468-103">Los ensamblados pueden ser privados o compartidos: de forma predeterminada, la mayoría de los programas sencillos constan de un ensamblado privado porque no se diseñaron para ser usados por otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="ab468-103">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  

<span data-ttu-id="ab468-104">Para compartir un ensamblado con otras aplicaciones, debe colocarse en la [caché global de ensamblados](gac.md).</span><span class="sxs-lookup"><span data-stu-id="ab468-104">In order to share an assembly with other applications, it must be placed in the [global assembly cache (GAC)](gac.md).</span></span>  
  
<span data-ttu-id="ab468-105">Para compartir un ensamblado:</span><span class="sxs-lookup"><span data-stu-id="ab468-105">To share an assembly:</span></span>
  
1. <span data-ttu-id="ab468-106">Cree el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ab468-106">Create your assembly.</span></span> <span data-ttu-id="ab468-107">Para obtener más información, vea [Creación de ensamblados](../../standard/assembly/create.md).</span><span class="sxs-lookup"><span data-stu-id="ab468-107">For more information, see [Create assemblies](../../standard/assembly/create.md).</span></span>  
  
2. <span data-ttu-id="ab468-108">Asigne un nombre seguro al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ab468-108">Assign a strong name to your assembly.</span></span> <span data-ttu-id="ab468-109">Para obtener más información, vea [Cómo: Firmar un ensamblado con un nombre seguro](../../standard/assembly/sign-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="ab468-109">For more information, see [How to: Sign an assembly with a strong name](../../standard/assembly/sign-strong-name.md).</span></span>  
  
3. <span data-ttu-id="ab468-110">Asigne la información de versión al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ab468-110">Assign version information to your assembly.</span></span> <span data-ttu-id="ab468-111">Para obtener más información, vea [Versiones de los ensamblados](../../standard/assembly/versioning.md).</span><span class="sxs-lookup"><span data-stu-id="ab468-111">For more information, see [Assembly versioning](../../standard/assembly/versioning.md).</span></span>  
  
4. <span data-ttu-id="ab468-112">Agregue el ensamblado a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="ab468-112">Add your assembly to the global assembly cache.</span></span> <span data-ttu-id="ab468-113">Para obtener más información, vea [Cómo: Instalar un ensamblado en la caché global de ensamblados](install-assembly-into-gac.md).</span><span class="sxs-lookup"><span data-stu-id="ab468-113">For more information, see [How to: Install an assembly into the global assembly cache](install-assembly-into-gac.md).</span></span>  
  
5. <span data-ttu-id="ab468-114">Obtenga acceso a los tipos que contiene el ensamblado desde otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="ab468-114">Access the types contained in the assembly from other applications.</span></span> <span data-ttu-id="ab468-115">Para obtener más información, vea [Cómo: Hacer referencia a un ensamblado con nombre seguro](../../standard/assembly/reference-strong-named.md).</span><span class="sxs-lookup"><span data-stu-id="ab468-115">For more information, see [How to: Reference a strong-named assembly](../../standard/assembly/reference-strong-named.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab468-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab468-116">See also</span></span>

- [<span data-ttu-id="ab468-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="ab468-117">C# programming guide</span></span>](../../../api/index.md)
- [<span data-ttu-id="ab468-118">Conceptos de programación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ab468-118">Programming concepts (Visual Basic)</span></span>](../../../api/index.md)
- [<span data-ttu-id="ab468-119">Programación con ensamblados</span><span class="sxs-lookup"><span data-stu-id="ab468-119">Program with assemblies</span></span>](../../standard/assembly/program.md)
